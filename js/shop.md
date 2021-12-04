---
description: Control the whole channel
---

# Shop

When you wish to control the console itself, you utilize `wiiShop`. It is an important (and necessary) object to instanciate, as it controls the flow of the channel - rebooting, errors, options - alongside handling localization.

```javascript
var wiiShop = new wiiShop();
```

## Members

| Member Name                           | Discussion                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `wiiShop.returnToUpdate()`            | Resets the system to the Wii System Update menu available in Settings.                                                                                                                                                                                                                                                                                    |
| `wiiShop.rebootSystem()`              | Resets the system - i.e. restarting the channel. On a Wii U, this appears to go to the Wii U Menu.                                                                                                                                                                                                                                                        |
| `wiiShop.returnToMenu()`              | Exits to the Wii System Menu.                                                                                                                                                                                                                                                                                                                             |
| `wiiShop.jumpToEULAViewer()`          | Resets the system to the EULA agreement channel.                                                                                                                                                                                                                                                                                                          |
| `wiiShop.jumpToManualChannel()`       | On a vWii, opens the [Wii Menu Electronic Manual](https://wiibrew.org/wiki/Wii\_Electronic\_Manual\_\(vWii\)). As this channel is not available by default on normal Wiis, it fails to launch and goes to the Wii System Menu.                                                                                                                            |
| `wiiShop.retry()`                     | <p>First, it checks the current error code, if any.</p><p>If the error is:</p><ul><li>209506</li><li>209509</li><li>209510</li><li>209528</li><li>209535</li><li>209538</li><li>209540</li><li>209546</li></ul><p>the channel simply goes to the previous page.</p><p></p><p>If not, the channel is reset.</p>                                            |
| `wiiShop.beginWaiting()`              | Shows the spinner UI over the currently loaded page.                                                                                                                                                                                                                                                                                                      |
| `wiiShop.endWaiting()`                | Hides the spinner UI for the currently loaded page.                                                                                                                                                                                                                                                                                                       |
| `wiiShop.setWallpaper(type)`          | <p>Changes the image displayed in the borders of the loaded webpage. There are four types, specified by <code>type</code>:</p><ul><li><code>0</code>: Dotted blue lines, default</li><li><code>1</code>: Pure black</li><li><code>2</code>: Pure white</li><li><code>3</code>: Blue vertical lines, as used within the health and safety manual</li></ul> |
| `wiiShop.disableHRP()`                | Disables the HOME menu.                                                                                                                                                                                                                                                                                                                                   |
| `wiiShop.enableHRP()`                 | Enables the HOME menu.                                                                                                                                                                                                                                                                                                                                    |
| `wiiShop.error(errorCode, errorType)` | <p>Displays an error page with <code>errorCode</code>.</p><p></p><p>TODO: Determine what types are available for this section. <code>0</code> and <code>1</code> are known.</p>                                                                                                                                                                           |
| `wiiShop.closeManual()`               | Apparently available to close the shop's manual, it simply returns to the Wii System Menu.                                                                                                                                                                                                                                                                |
| `wiiShop.jumpDataMng()`               | Opens Data Management within the Wii System Menu.                                                                                                                                                                                                                                                                                                         |
| `wiiShop.setSCARank(rank)`            | <p>Appears to adjust the color of Mario in the download screen? TODO: confirm</p><p></p><p>Rank <code>0</code> appears to be normal, <code>1</code> appears to be silver, <code>2</code> appears to be gold. Unclear what other values are.</p>                                                                                                           |

## Properties (Get)

| Property Name              | Discussion                                                                                                                                                                                                                                     |
| -------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `wiiShop.errMsg`           | <p>Returns a localized string for the current error message.</p><p></p><p>TODO: Determine how this is set, and why error code 209658 is handled differently.</p>                                                                               |
| `wiiShop.errCode`          | Returns the current error code registered as a string.                                                                                                                                                                                         |
| `wiiShop.title`            | Returns a localized string of the channel. In English, this is "Wii Shop Channel".                                                                                                                                                             |
| `wiiShop.retryBtn`         | Returns a localized string for the retry button, such as "Try Again" in English.                                                                                                                                                               |
| `wiiShop.menuBtn`          | <p>If launched normally, returns a localized string for "Wii Menu".</p><p></p><p>If launched as a manual viewer, returns a localized string for "Back" .</p>                                                                                   |
| `wiiShop.wiiUMenuBtn`      | Returns a localized string for "Wii U Menu".                                                                                                                                                                                                   |
| `wiiShop.eulaBtn`          | Returns a localized string for "Proceed".                                                                                                                                                                                                      |
| `wiiShop.eulaMsg`          | Returns a localized paragraph pleading for the user to agree to the Wii Network Services Agreement.                                                                                                                                            |
| `wiiShop.manualBtn`        | Returns a localized string for "Continue".                                                                                                                                                                                                     |
| `wiiShop.connecting`       | <p>Returns a localized string for "Connecting. Please wait..."</p><p></p><p>This string is extremely important and must be accessed on each page load. Please see <a href="shop.md#undefined">Connecting example</a> for more information.</p> |
| `wiiShop.isCompatibleMode` | <p>Appears to always return 0, as nothing accesses what it reads from at 0x803607f9.</p><p></p><p>TODO: Verify</p>                                                                                                                             |
| `wiiShop.launchCode`       | <p>Returns some variant of a launch code, which is also referenced to check if the channel was launched to be a manual viewer.</p><p></p><p>TODO: Determine possible codes</p>                                                                 |

### Connecting Example

It is important that `wiiShop.connecting` variable is accessed once per page load, as it stops an internal timer. It is additionally important that its value is set to a variable and not cast away, as it being accessed is what cancels the timer.

If the timer is not cancelled, error 209601 is displayed after 100 seconds.

The following code block provides an example of the bare minimum required to prevent an error thrown:

```javascript
var wiiShop = new wiiShop();
const unused = wiiShop.connecting;
```

## Properties (Set)

| Property Name                        | Discussion                                                                                                                                                                           |
| ------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `wiiShop.getLogUrl = stringVariable` | <p>Sets a log URL to the given string.</p><p></p><p>TODO: where and how is this used otherwise? It seemingly cannot be queried, and nothing accesses the URL throughout runtime.</p> |
| `wiiShop.fadeColor = integerValue;`  | <p>Sets a color to fade to when exiting from the Mario downloading animation.</p><p></p><p>TODO: Is this correct?</p>                                                                |

## Test Variables (Get/Set)

It's unclear on what these are used for: the channel never utilizes set values throughout operation, nor does the Nintendo-provided Wii Shop Channel. Their values persist unmodified throughout the current channel's launch, making them the numerical equivalent to a cookie, at best. One can assume that they were most likely included for testing purposes with the C++ <-> JS runtime bindings for Opera. Nonetheless, they are included.

| Property Name | Discussion                                                                                                               |
| ------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `wiiShop._a_` | General-purpose [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type. |
| `wiiShop._b_` | General-purpose [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type. |
| `wiiShop._c_` | General-purpose [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type. |
| `wiiShop._d_` | General-purpose [Number](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Number) type. |

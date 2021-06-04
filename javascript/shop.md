# Shop

To control all aspects of the Shop's operation, you use `wiiShop`. This class is nearly an essential for every page - controlling aspects of loading, page interaction, and operation.

## Functions

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>returnToUpdate()</code>
      </td>
      <td style="text-align:left">Opens the Wii Menu to the Wii System Update screen.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>rebootSystem()</code>
      </td>
      <td style="text-align:left">Internally calls the same function as the Reset button on a Wii would.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>returnToMenu()</code>
      </td>
      <td style="text-align:left">Opens the Wii Menu.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>jumpToEULAViewer()</code>
      </td>
      <td style="text-align:left">Opens the hidden EULA channel for this region.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>jumpToManualChannel()</code>
      </td>
      <td style="text-align:left">Opens the channel the shop was opened from via its operations guide.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>retry()</code>
      </td>
      <td style="text-align:left">Navigates to the previous page.
        <br />This function is intended to be called from error pages.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>beginWaiting()</code>
      </td>
      <td style="text-align:left">Starts the spinning ring on screen.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>endWaiting()</code>
      </td>
      <td style="text-align:left">Stops and removes the spinning ring on screen.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setWallpaper(wallpaper)</code>
      </td>
      <td style="text-align:left">
        <p>Sets the background of the channel for this page.</p>
        <p>There are four wallpaper types:</p>
        <ul>
          <li><code>0</code>, the default background with dots in its lower half</li>
          <li><code>1</code>, an entirely black background</li>
          <li><code>2</code>, an entirely white background</li>
          <li><code>3</code>, a white background with a blue stripe closest to content</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>disableHRP()</code>
      </td>
      <td style="text-align:left">Disables usage of the HOME Menu.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>enableHRP()</code>
      </td>
      <td style="text-align:left">Enables usage of the HOME Menu.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>error(code, type</code>)</td>
      <td style="text-align:left">Presents an error with code <code>code</code>. If <code>type</code> is 2
        and <code>error</code> is in range of a WC24 error code, presents with that
        template. Not to be confused with <code>dispError</code> from <a href="wiiconnect24.md">WiiConnect24</a>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>closeManual()</code>
      </td>
      <td style="text-align:left">Returns to the Wii Menu from a channel&apos;s manual.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>jumpDataMng()</code>
      </td>
      <td style="text-align:left">Opens the Wii Menu to the Data Management screen.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>setSCARank(rank)</code>
      </td>
      <td style="text-align:left"><code>rank</code> appears to be either 1 or 2. This value is set somewhere
        within the IPL loading screen global object. It&apos;s unknown how this
        value is used.</td>
    </tr>
  </tbody>
</table>

## Strings

<table>
  <thead>
    <tr>
      <th style="text-align:left">Variable name</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>errMsg</code>
      </td>
      <td style="text-align:left">The current error message localized.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>errCode</code>
      </td>
      <td style="text-align:left">The current error code.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>title</code>
      </td>
      <td style="text-align:left">The title of the running channel localized, such as <code>Wii Shop Channel</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>retryBtn</code>
      </td>
      <td style="text-align:left">The &quot;Try Again&quot; button&apos;s string localized.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>menuBtn</code>
      </td>
      <td style="text-align:left">The &quot;Wii Menu&quot; button&apos;s string localized.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>wiiUMenuBtn</code>
      </td>
      <td style="text-align:left">The &quot;Wii U Menu&quot; button&apos;s string localized.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>eulaBtn</code>
      </td>
      <td style="text-align:left">The &quot;User Agreements&quot; button&apos;s string localized.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>eulaMsg</code>
      </td>
      <td style="text-align:left">A monologue about how the user has not accepted the EULA to use this channel,
        localized.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>manualChannelBtn</code>
      </td>
      <td style="text-align:left">The &quot;Contine&quot; button in context of a manual, localized.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>connecting</code>
      </td>
      <td style="text-align:left">
        <p>The &quot;Connecting. Please wait...&quot; string, localized.</p>
        <p></p>
        <p>This string serves a special purpose - once accessed, it cancels an internal
          timer to validate the current page loaded properly. Without such, you receive
          error 209601.</p>
      </td>
    </tr>
  </tbody>
</table>

## Properties

| Property Name | Description |
| :--- | :--- |
| `_a_` | Hardcoded to return 0. |
| `_b_` | Hardcoded to return 0. |
| `_c_` | Hardcoded to return 0. |
| `_d_` | Hardcoded to return 0. |
| `isCompatibleMode` | Returns whether this device is a Wii U or not. |
| `launchCode` | Returns the launch code of this channel. |


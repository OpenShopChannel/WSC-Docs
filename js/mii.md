---
description: The best way to display user's Miis
---

# Mii

When you want to source Mii imagery from a user, you use a mixture of JavaScript and the `miip` protocol. This is useful for identifying various users to send letters to, with all of its 64x64px action.

```javascript
var mii = new wiiMii();
```

## Members

| Member Name              | Discussion                                                                                                        |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| `mii.getMiiNum()`        | Returns the amount of Miis this console has. Will not exceed 100.                                                 |
| `mii.isValidIcon(index)` | Returns a boolean if the Mii at number _index_ exists. This is helpful when looping to access via index from 100. |
| `mii.getMiiName(index)`  | Returns a string with the Mii at _index_'s name.                                                                  |

## Protocol

You have two ways of accessing Miis: via an index ([IDX](mii.md#method-idx)), or using the Mii's character ID ([CID](mii.md#method-cid)).

Regardless of what method, the `miip://` protocol accepts a basic format:

```
miip://METHOD/IDENTIFER.bmp?bgR=red&bgG=green&bgB=blue&width=64&height=64
```

You need to set a few params in order to use such a URL.

* `METHOD`  must be `IDX` or `CID`.
* `IDENTIFIER` is the value relating to what's mentioned above - be it an index of a Mii, or a friend's character ID.
* `bgR`, `bgG` and `bgB` are the background of the Mii image in integer values. Instead of 0xff in hexadecimal, you would write 255.
* `width` and `height` are the rendered size in pixels of this bmp.

### **IDX**

Nintendo imposes a max of 100 Miis. Due to this, you can iterate an index from 0-99 and call `wiiMii#isValidIcon(index)` to verify its validity.

For example, to show the images of all valid Miis and log names using the functions above:

```javascript
var mii = new wiiMii();

trace("Amount of Miis on console: " + mii.getMiiNum());
for (var i = 0; i < 100; i++) {
    if (!mii.isValidIcon(i)) {
        trace("Mii #" + i + " is not a valid Mii.");
    } else {
        trace("The Mii at index " + i + " has the name of " + mii.getMiiName(i) + ".");
        // Append a new image element for all Miis with a yellow background.
        var elem = document.createElement('img');
        elem.src = "miip://IDX/" + i + ".bmp?width=48&height=48&bgR=255&bgG=205&bgB=0";
        document.body.appendChild(elem);
    }
}
```

### **CID**

Every Mii has a unique ID (known as a Mii ID, character ID, or CID) derived from its creation timestamp and other data. (For more information, read the [WiiBrew article](https://wiibrew.org/wiki/Mii\_data#Mii\_format).)

When you utilize [NWC24](nwc24.md) to retrieve the user's friends list, you are able to query a friend's attached Mii and retrieve a usable CID. (For more in-depth information about the friends list, see its [available methods](nwc24.md#friends-list).) Internally, the CID is converted to a usable index.

For example, to iterate through all available friends and show their respective Miis:

```javascript
var nwc24 = new wiiNwc24();
var friendAmount = nwc24.getFriendNum();

trace("Amount of friends on console: " + friendAmount);

for (var i = 0; i < friendAmount; i++) {
    // Print information about the Mii for reference.
    var cid = nwc24.getFriendInfo(i, "miiImage")
    trace("The friend at index " + i + " has a CID of " + cid + ".");

    // Append a new image element for all Miis with a yellow background.
    var elem = document.createElement('img');
    elem.src = "miip://CID/" + cid + ".bmp?width=48&height=48&bgR=255&bgG=205&bgB=0";
    document.body.appendChild(elem);
}
```


# Mii

When you want to source Mii imagery from a user, you use a mixture of JavaScript and the `miip` protocol. This is useful for identifying various users to send letters to, with all of its 64x64px action.

```javascript
var mii = new wiiMii();
```

## Members

| Member Name            | Discussion                                                                                                      |
| ---------------------- | --------------------------------------------------------------------------------------------------------------- |
| `mii.getMiiNum()`      | Returns the amount of Miis this console has. Will not exceed 100.                                               |
| `mii.isValidIcon(num)` | Returns a boolean if the Mii at number _num_ exists. This is helpful when looping to access via index from 100. |
| `mii.getMiiName(num)`  | Returns a string with the Mii at _num_'s name.                                                                  |

## Protocol

You have two ways of accessing Miis: via an index ([IDX](mii.md#method-idx)), or using the Mii's console ID ([CID](mii.md#method-cid)).

Regardless of what method, the `miip://` protocol accepts a basic format:

```
miip://METHOD/IDENTIFER.bmp?bgR=red&bgG=green&bgB=blue&width=64&height=64
```

You need to set a few params in order to use such a URL.

* `METHOD`  must be `IDX` or `CID`.
* `IDENTIFIER`  is the value relating to what's mentioned above - be it the Mii at index 0, or a friend's console ID.
* `bgR`, `bgG` and `bgB` are the background of the Mii image's in integer values. Instead of ff, you would do 255.
* `width` and `height` are the rendered size in pixels of this bmp.

### **IDX**

Nintendo imposed a max of 100 Miis. Because of this, you can simply iterate an array from 0-99 and call `wiiMii#isValidIcon(num)` to verify its validity.

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

TODO

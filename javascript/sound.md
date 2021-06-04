# Sound

The best way to utilize the Shop's native sound effects is via `wiiSound`. You can use it to play sound effects across various parts of your website, or to play the widely praised background music.

```javascript
var sound = new wiiSound();
```

## Functions

`wiiSound` exists only to serve its name. As such, it only has two exposed functions.

| Method | Documentation |
| :--- | :--- |
| `sound.playSE(id)` | Plays the sound effect for the given ID. See [Sound Effects](sound.md#sound-effects) for usable sounds. |
| `sound.playBGM()` | Plays the default Wii Shop Channel background music. |

## Sound Effects

The following names are derived from Nintendo's official names for them in various places.

| ID | Sound Effect |
| :--- | :--- |
| 1 | Slide |
| 2 | Focus |
| 3 | Decide |
| 4 | Cancel |
| 5 | Choice |
| 6 | Error |
| 7 | Add Point |
| 8 | Copy Finished |
| 9 | Mario S Jump |
| 10 | Mario L Jump |
| 11 | Fire Ball |
| 12 | Coin |
| 13 | Hit Block |
| 14 | Mario Swim |
| 15 | Copying |
| 16 | Loading |


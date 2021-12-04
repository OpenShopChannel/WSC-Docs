# Sound

When you want to play sound effects or start background music, you do so via the `wiiSound` object.

```javascript
var sound = new wiiSound();
```

## Members

| Member Name            | Discussion                                                                                                |
| ---------------------- | --------------------------------------------------------------------------------------------------------- |
| `sound.playSE(effect)` | Plays the sound effect designated by `effect`. See [Effects](sound.md#undefined) for further information. |
| `sound.playBGM()`      | Plays the Wii Shop Channel's well-known theme.                                                            |

## Effects

There are 13 available sound effects to play. You specify an effect index as the `effect`.

The effect names are derived from their listing within `IplSound.brsar`, such as `WIPL_SE_CHAR_DELETE_ERROR`.

<table><thead><tr><th data-type="number">Index</th><th>Sound Effect</th><th>Discussion</th></tr></thead><tbody><tr><td>1</td><td>"Push"</td><td>Seemingly silent.</td></tr><tr><td>2</td><td>Hover/Target</td><td>The sound played when hovering over buttons.</td></tr><tr><td>3</td><td>"Decide"/Select</td><td>A success-like sound, played upon button selection.</td></tr><tr><td>4</td><td>Cancel</td><td>A sound played when pressing the Back button.</td></tr><tr><td>5</td><td>Choice Change</td><td>The sound played when selecting another option in a ratio menu.</td></tr><tr><td>6</td><td>Error</td><td>A short sound designating an error. Internally called <code>WIPL_SE_CHAR_DELETE_ERROR</code>, it appears to be the same effect from the Wii's keyboard.</td></tr><tr><td>7</td><td>Add Point</td><td>An effect played upon successful point addition.</td></tr><tr><td>8</td><td>Copy Finished</td><td>A success sound played upon download completion.</td></tr><tr><td>9</td><td>Small Mario Jump</td><td>A small jump effect.</td></tr><tr><td>10</td><td>Large Mario Jump</td><td>A larger jump sound effect.</td></tr><tr><td>11</td><td>Fire Ball</td><td>The expected fire ball effect.</td></tr><tr><td>12</td><td>Coin</td><td>A coin hit effect.</td></tr><tr><td>13</td><td>Hit Block</td><td>The hit block sound effect from various Mario games.</td></tr><tr><td>14</td><td>Copying</td><td>Something very close to the existing Mario jump sounds.</td></tr><tr><td>15</td><td>Loading</td><td>The loading sound displayed with the spinner.</td></tr></tbody></table>


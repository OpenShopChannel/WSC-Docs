---
description: Easily accessible title metadata
---

# ECTitleInfo

ECTitleInfo represents information available about a title in a JavaScript-accessible, read-only method. Some data is sourced from the TMD. Properties may only be retrieved, not set.

You most likely do not want to instantiate this object yourself. Instead, prefer querying one directly from [ECommerceInterface](../ecommerceinterface.md). For example:

```javascript
var info = ec.getTitleInfo('0000000100000002');
```

### Properties

| Property Name             | Discussion                                                                                                                                                                                          |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `info.titleId`            | The title ID this object represents.                                                                                                                                                                |
| `info.isOnDevice`         | <p>Whether this title is present on the console.<br><br>It is unclear on when this may ever be false, as attempting to query a title not present on the console will return <code>-4050</code>.</p> |
| `info.isTmdPresent`       | <p>Whether a TMD is available for this title.<br><br>This may be possible if the user has removed the title, but its ticket is still present - i.e. removed via the System Menu.</p>                |
| `info.version`            | The version of this title.                                                                                                                                                                          |
| `info.occupiedUserBlocks` | The amount of blocks this title uses.                                                                                                                                                               |
| `info.occupiedUserInodes` | The number of inodes taken up by this title.                                                                                                                                                        |
| `info.occupiedSysBlocks`  | The amount of system-reserved blocks this title utilizes.                                                                                                                                           |
| `info.occupiedSysInodes`  | The amount of system-reserved inodes used by this title.                                                                                                                                            |

## ECTitleInfos

`ECTitleInfos` manages multiple of a `ECTitleInfo`. It is intended to be immutable, and cannot be set in any fashion.

Similar to ECTitleInfo, it's undesirable to instantiate one yourself. ECommerceInterface similarly provides a way to acquire one yourself. For example, to acquire title info for all available titles on the console:

```javascript
var infos = ec.getTitleInfos();
```

### Properties

| Property Name      | Discussion                                                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `infos.length`     | The amount of titles within this array.                                                                                  |
| `infos.get(index)` | Returns the [ECTitleInfo](ectitleinfo.md) at the given index.                                                            |
| `infos.set`        | This array is considered immutable. Despite it existing, attempting to call or access this property results in an error. |

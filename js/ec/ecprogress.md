# ECProgress

`ECProgress` is an object describing an operation's state. You should not instantiate one yourself - instead, for all asynchronous operations, one will be returned by the function.

For example, you may encounter:

```javascript
var progress = ec.checkDeviceStatus();
```

## Properties

| Property Name                | Discussion                                                                                  |
| ---------------------------- | ------------------------------------------------------------------------------------------- |
| `progress.status`            | Integer regarding the internal EC value of operations. -4009 appears to mean "incomplete".  |
| `progress.operation`         | String of the current operation. For the example above, this could be `checkDeviceStatus` . |
| `progress.description`       | Description of the current operation. Typically empty. TODO: find how to set a description. |
| `progress.phase`             | Unknown, typically observed to be 17.                                                       |
| `progress.isCancelRequested` | Boolean regarding if this asyncronous operation should be cancelled.                        |
| `progress.downloadedSize`    | Size currently downloaded. Most useful for a title contents-related operation.              |
| `progress.totalSize`         | Size of the finished contents. Most useful for a title contents-related operation.          |
| `progress.errCode`           | Error code returned from operation.                                                         |
| `progress.errInfo`           | Information about the error. TODO: find how this is set                                     |

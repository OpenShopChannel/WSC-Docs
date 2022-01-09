# ECTransactionInfo

If you want to query transaction info, you utilize an ECTransactionInfo object. You likely do not want to instantiate one yourself, instead retrieving transactions from the server via [ECommerceInterface](../ecommerceinterface.md):

```javascript
var infos = ec.getTransactionInfos();

// Ensure you check infos.length. In this example, we do not.
var info = infos.get(0);
```

### Properties

This array is considered immutable, and cannot be modified. Properties may only be retrieved.

| Property Name | Discussion                                                                                                                                                                          |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `info.id`     | The ID of this transaction.                                                                                                                                                         |
| `info.date`   | A UNIX timestamp representing when this transaction occurred.                                                                                                                       |
| `info.type`   | <p>A string representing its type, such as <code>PURCHGAME</code>.<br><br>It is unknown what types are available, as the client and frontend do not appear to check this field.</p> |

## ECTransactionInfos

`ECTransactionInfos` manages multiple of an `ECTransactionInfo`. It is regarded as immutable.

```javascript
var infos = ec.getTransactionInfos();
```

### Properties

| Property Name      | Discussion                                                                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| `infos.length`     | Returns the amount of available transactions in this array.                                                              |
| `infos.get(index)` | Retrieves the [ECTransactionInfo](ectransactioninfo.md) at the given index.                                              |
| `infos.set`        | This array is considered immutable. Despite it existing, attempting to call or access this property results in an error. |

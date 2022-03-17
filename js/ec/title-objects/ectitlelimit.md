---
description: Easily accessible title limits
---

# ECTitleLimit

If title limits are available on a ticket, it's possible to query them. For example, to retrieve the first limit for the System Menu:

```javascript
var ticket = ec.getTicketInfos("0000000100000002").get(0);
var limit = ticket.limits(0);
```

It is also possible to instantiate one yourself.

```javascript
var limit = new ECTitleLimit(code, limit, consumed);
```

### Properties

| Property Name | Discussion                                                    |
| ------------- | ------------------------------------------------------------- |
| `code`        | A [Limit Type](ectitlelimit.md#limit-types) name as a string. |
| `limit`       | The amount for this limit type.                               |
| `consumed`    | Unknown.                                                      |

### Limit Types

| Limit Name | Limit Value | Description  |
| ---------- | ----------- | ------------ |
| `PR`       | 0           | Permanent    |
| `TR`       | 1           | Trial        |
| `DR`       | 2           | Demo         |
| `SR`       | 3           | Subscription |
| `LR`       | 4           | Service(?)   |
| `AT`       | 100         | ?            |

## ECTitleLimits

`ECTitleLimits` manages multiple of an `ECTitleLimit`.

You have the ability instantiate one yourself, or have one provided to you via existing metadata.

```javascript
// Instantiation
var limits = new ECTitleLimits(/* up to 8 limits */);
```

```javascript
// Existing metadata
var ticket = ec.getTicketInfos("0000000100000002").get(0);
var limits = ticket.limits;
```

### Properties

| Property Name                    | Discussion                                                                                                         |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `limits.length`                  | <p>Returns the length of this limits array.<br><br>You may also set a new length for this array, resizing it.</p>  |
| `limits.get(index)`              | <p>Returns the <a href="ectitlelimit.md">ECTitleLimit</a> for this index.<br><br>This property may not be set.</p> |
| `limits.set(index, code, limit`) | <p>Sets the limit at the given index to have a new code and limit.<br><br>This property may not be retrieved.</p>  |

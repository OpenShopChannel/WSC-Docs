---
description: Easily accessible ticket information
---

# ECTicketInfo

ECTicketInfo handles representing a ticket for a given title ID. It provides usable data about the status of the title on the Wii.

You do not want to instantiate this object yourself. Instead, obtain one via `ec.getTicketInfos(titleId)` and iterate through all [ECTicketInfos](ecticketinfo.md#ecticketinfos) until you find what is desired. This will populate all ECTicketInfo available with usable data.

For example:

```javascript
// Obtains tickets for the System Menu
var infos = ec.getTicketInfos("0000000100000002");

// Ensure you check infos.length. In this example, we do not.
var ticket = infos.get(0);
```

### Properties

| Property Name          | Discussion                                                                                |
| ---------------------- | ----------------------------------------------------------------------------------------- |
| `ticket.ticketId`      | The ticket ID of the retrieved ticket.                                                    |
| `ticket.titleId`       | The title ID this ticket is intended for.                                                 |
| `ticket.nLimits`       | The number of limits available for this ticket.                                           |
| `ticket.limits`        | Returns an [ECTitleLimits](ectitlelimit.md#ectitlelimits) object for the current ticket.  |
| `ticket.version`       | The file version of this ticket, which should be 0.                                       |
| `ticket.deviceId`      | The device ID this ticket is specified for.                                               |
| `ticket.ticketVersion` | The version of this title.                                                                |
| `ticket.licenseType`   | <p>The type of license this ticket represents.<br><br>TODO: determine possible values</p> |
| `ticket.cidxMask`      | <p>A base64-encoded field of some field within the ticket.<br><br>TODO: determine</p>     |
| `ticket.reserved`      | <p>A base64-encoded field of some field within the ticket.<br><br>TODO: determine</p>     |

## ECTicketInfos

`ECTicketInfos` manages multiple of an `ECTicketInfo`. It is intended to be an immutable array, and its values only be retrived, not set.

### Properties

| Property Name       | Discussion                                                                                                               |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| `ticket.length`     | Returns the length of the tracked array.                                                                                 |
| `ticket.get(index)` | Returns the [ECTicketInfo](ecticketinfo.md) at the given index.                                                          |
| `ticket.set`        | This array is considered immutable. Despite it existing, attempting to call or access this property results in an error. |


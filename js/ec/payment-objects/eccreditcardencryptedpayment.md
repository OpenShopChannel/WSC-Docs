# ECCreditCardEncryptedPayment

If you wish to represent part of a user's credit card number - for example, one already present on the server - you can use ECCreditCardEncryptedPayment. This object only stores the card's last four digits, and represents it as "encrypted" on the server.

For example, assuming an example credit card number ending in `8431`:

```javascript
var payment = new ECCreditCardEncryptedPayment('8431');
```

### Properties

| Property Name            | Discussion                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------- |
| `payment.lastFourDigits` | The last four digits set during instantiation. Can be retrieved, or set to another set of digits. |

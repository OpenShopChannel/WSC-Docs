# ECECardPayment

If you wish to represent a gift card to the server as a payment type, you utilize ECECardPayment. If the idea sounds familiar, it may be because Nintendo used them - ECards are officially Wii Points Cards.

For example, assuming every ECard is 16 digits long:

```javascript
var payment = new ECECardPayment('001122334455667788');
```

### Properties

| Property Name    | Discussion                                                                                                      |
| ---------------- | --------------------------------------------------------------------------------------------------------------- |
| `payment.number` | The typically 16 digit card number set during instantiation. Can be retrieved, or set to another set of digits. |

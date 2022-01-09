# ECCreditCardPayment

If you wish to represent a user's credit card whilst purchasing a title, you use ECCreditCardPayment. For example, utilizing an [example credit card number](https://www.paypalobjects.com/en\_AU/vhelp/paypalmanager\_help/credit\_card\_numbers.htm):

```javascript
var payment = new ECCreditCardPayment('4012888888881881');
```

### Properties

| Property Name    | Discussion                                                                       |
| ---------------- | -------------------------------------------------------------------------------- |
| `payment.number` | The number set during instantiation. Can be retrieved, or set to another number. |

# ECAccountPayment

If you have a balance already available on account - say, Points - you can utilize ECAccountPayment. This allows specification of account information, or utilizes the registered copy on device.

### Constructors

If no constructors are specified, payment will be sourced from the device's configured account ID and device token within `ec.cfg`.

```javascript
var payment = new ECAccountPayment();
```

You may also specify the account ID and token, overriding the device's values:

```javascript
var payment = new ECAccountPayment('123456789', 'aphei7au1ceu8Wei2eec0');
```

Lastly, you may also only specify the account ID. However, this will authenticate with an empty device token, and purchases should be expected to fail.

### Properties

All properties may be retrieved and set. However, if not specified from the constructor, these values will be empty. Population of the configured account ID and token will only take place while formulating SOAP requests.

| Property Name      | Discussion                   |
| ------------------ | ---------------------------- |
| `payment.id`       | The account ID to utilize.   |
| `payment.password` | The device token to utilize. |

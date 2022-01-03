---
description: A way to describe pricing data
---

# ECPrice

If you want to relay pricing data to the server, you instantiate `ECPrice`.  For example, when you purchase a title via `ec.purchaseTitle` on [ECommerceInterface](../ecommerceinterface.md), you're expected to present a price as a parameter.

## Constructor

ECPrice expects exactly two parameters for its single constructor: `amount`, and `currency`.

```javascript
var price = new ECPrice(amount, currency);
```

For example, let's assume you wish to instanciate a price representing 4.99 USD. Both the amount and the currency are strings.

```javascript
var price = new ECPrice('4.99', 'USD');
```

## Properties

| Property Name | Discussion                                                                                                                                      |
| ------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `amount`      | The amount that this ECPrice object represents, as a string. It is not converted to a numerical type for usage.                                 |
| `currency`    | The currency this ECPrice object represents, as a string. There is no defined list of currencies checked against, so any value may be utilized. |


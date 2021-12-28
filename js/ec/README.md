---
description: A family of objects for interacting with titles and servers
---

# EC

EC, short for ECommerce, is understandably the most crucial part of the Wii Shop Channel. As such, its family of functions and objects comprise most of the JS API and binary within, separated across many separate mechanics. Each object available is listed below.

While every object can be instantiated by itself, data available populated within the majority objects - such as [ECDeviceInfo](ecdeviceinfo.md) or [ECProgress](ecprogress.md) - will only be present when returned from a function in [ECommerceInterface](ecommerceinterface.md). Ensure you read the object's respective documentation for the correct way to utilize one.

## Objects

### Common

These objects provide general functionality for all of the EC interface.

* [ECommerceInterface](ecommerceinterface.md)
* [ECDeviceInfo](ecdeviceinfo.md)
* [ECProgress](ecprogress.md)

### Payment

Payment-related objects provide multiple source of payments - via credit cards, "ECards" (known as a Wii Points Card officially) or the existing account balance. It's additionally possible to work with information about an existing transaction.

* [ECCreditCardPayment](payment-objects/eccreditcardpayment.md)
* [ECCreditCardEncryptedPayment](payment-objects/eccreditcardencryptedpayment.md)
* [ECECardPayment](payment-objects/ececardpayment.md)
* [ECAccountPayment](payment-objects/ecaccountpayment.md)
* [ECPrice](payment-objects/ecprice.md)
* [ECTransactionInfo](payment-objects/ectransactioninfo.md), and [ECTransactionInfos](payment-objects/ectransactioninfo.md#ectransactioninfo).

### Title

Title-related objects provide functionality for querying title information, ticket information, and title limit information.

* [ECTitleLimit](title-objects/ectitlelimit.md), and [ECTitleLimits](title-objects/ectitlelimit.md#ectitlelimits)
* [ECTitleInfo](title-objects/ectitleinfo.md), and [ECTitleInfos](title-objects/ectitleinfo.md#ectitleinfos)
* [ECTicketInfo](title-objects/ecticketinfo.md), and [ECTicketInfos](title-objects/ecticketinfo.md#ecticketinfos)


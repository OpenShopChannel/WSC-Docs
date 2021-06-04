# ECommerceInterface

You use the ECommerce set of classes when you want to deal with the underlying EC APIs. With EC, you handle things such as title management and payment information. And you also have the option to handle components such as ECTitleLimit, a way to handle demo-respecting information for the System Menu.

For every page, you'll want to initialize the `ECommerceInterface` type.

```javascript
var ec = new ECommerceInterface();
```

This special type inherits from `ECGenericObject`, an internal C++ type that many others use as a parent. You should only create this specific object type once per page load in JS, as it calls `EC_Init` internally.

Inside of EC, there is a JS "test mode" that allows modification of objects that are normally not modifiable via JS. This must be enabled at compile time, or with a patch to the binary.

## Functions

| Method | Requires HTTPS? | Documentation |
| :--- | :--- | :--- |
| `ec.getVersion()` |  | Returns the EC library's version number. As of the Wii Shop Channel v21, this is `264192`. |
| `ec.setParameter(name, value)` |  | Sets multiple internal EC library values.  Known names are:  -`TIN`  \(unknown, accepts 0/1\)  -`AppId`  \(the current running title ID\)  - `PCPW`  \(related to the Parental Control pin/password\)  - `USE_NCRS` \(unknown, accepts 0/1\)  - `SPACE_CHECK_POLICY`  \(with value of `SPACE_CHECK_USER_ONLY`  or `SPACE_CHECK_ENTIRE_FS` \) |
| `ec.getSessionValue(name)` |  | For the current EC object, get a value from an internally maintained type. |
| `ec.setSessionValue(name, value)` |  | Sets a key named `name`  to a value. |
| `ec.getPersistentValue(name)` |  | Obtains a value by name from `ec.cfg`. |
| `ec.setPersistentValue(name, value)` |  | Sets a key by name to a value in `ec.cfg`. |
| `ec.getProgress()`, `ec.getProgress(id)` |  | Obtain a value on the state of the given operation, or the most recent operation. Returns -4007 if no operation is ongoing. |
| `ec.cancelOperation()` |  | Cancels the current operation. |
| `ec.purchaseTitle()` | ✅ |  |
| `ec.purchaseGiftTitle()` | ✅ |  |
| `ec.acceptGiftTitle()` | ✅ |  |
| `ec.unregister()` | ✅ |  |
| `ec.deleteOwnership()` | ✅ |  |
| `ec.syncTickets()` |  |  |
| `ec.checkDeviceStatus()` |  |  |
| `ec.refreshCachedBalance()` |  |  |
| `ec.getCachedBalance()` |  |  |
| `ec.getPurchaseInfo()` |  |  |
| `ec.getTransactionInfos()` |  |  |
| `ec.purchasePoints()` | ✅ |  |
| `ec.downloadTitle()` |  |  |
| `ec.checkFirmware()` |  |  |
| `ec.generateKeyPair()` | ✅ | Returns -4002 - possibly not implemented? |
| `ec.confirmKeyPair()` | ✅ | Returns -4002 - possibly not implemented? |
| `ec.checkRegistration()` |  | Makes a request via ECS for the `CheckRegistration` type. |
| `ec.register()` | ✅ |  |
| `ec.transfer()` | ✅ |  |
| `ec.syncRegistration()` | ✅ |  |
| `ec.sendChallengeReq()` | ✅ |  |
| `ec.getChallengeResp()` | ✅ |  |
| `ec.reportCSS()` | ✅ |  |
| `ec.confirmCSS()` | ✅ |  |
|  |  |  |
| `ec.getCSSConfirmation()` |  |  |
| `ec.getTitleInfo()` |  |  |
| `ec.getTitleInfos()` |  |  |
| `ec.getTicketInfos()` |  |  |
| `ec.getDeviceInfo()` |  | Returns an object you can use to access information with. See its dedicated page, [ECDeviceInfo](ecdeviceinfo.md), for more information. |
| `ec.setWebSvcUrls(ecs)`, `ec.setWebSvcUrls(ecs, ias)` or `ec.setWebSvcUrls(ecs, ias, cas)` |  | Sets endpoints for usage. `ecs`  is the ECommerceSOAP endpoint, `ias`  is the IdentityAuthenticationSOAP endpoint, and `cas` is the CatalogingSOAP endpoint. CAS is not used within the Wii Shop Channel - used in other ECDK-utilizing titles, such as for DLC content. |
| `ec.setContentUrls(ccs)` or `ec.setContentUrls(ccs, ucs)` |  | `ccs` appears to be an `http` URL by default, presumably meaning "cached contents". `ucs` may mean "uncached contents", using an `https` URL. |
| `ec.checkParentalControlPassword(pin)` |  | Validates the given Parental Control PIN/password as a long. If this is disabled, it returns -0xfeb/-4075. |
| `ec.launchTitle(titleId, ticketId)` |  | Launches the passed title with the given ticket. |
| `ec.request(requestString)` |  | Requests something, with a callback. \*\*TODO\*\* |
| `ec.getWeakToken()` | ✅ |  |
| `ec.setOption()` | Most likely. | Sets an option within EC. |
| `ec.startLog()` | ✅ | Creates a new logging buffer. |
| `ec.stopLog()` | ✅ | Destroys the present logging buffer. |
| `ec.getLog()` | ✅ | Returns a string with the internal held log from buffer. |

## JS Test Mode Operations

These following functions **do not function** without the JS test mode being enabled via binary patching. They will log such if called. Do not expect them to work.

| Method | Documentation |
| :--- | :--- |
| `ec.setLanguage()` | Overrides the configured language for this EC object. |
| `ec.setCountry()` | Overrides the configured country for this EC object. |
| `ec.setRegion()` | Overrides the configured region for this EC object. |
| `ec.setAge()` | Overrides the configured age for this EC object. |
| `ec.setAccountId()` | Overrides the configured account ID for this EC object. |
| `ec.deleteTitleContent()` |  |
| `ec.deleteTitle()` |  |
| `ec.pubKeyEncrypt()` |  |
| `ec.runTests()` |  |


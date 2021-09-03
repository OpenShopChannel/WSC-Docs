# ECommerceInterface

You use the ECommerce set of classes when you want to deal with the underlying EC APIs. With EC, you handle things such as title management and payment information. And you also have the option to handle components such as ECTitleLimit, a way to handle demo-respecting information for the System Menu.

For every page, you'll want to initialize the `ECommerceInterface` type.

```javascript
var ec = new ECommerceInterface();
```

This special type inherits from `ECGenericObject`, an internal C++ type that many others use as a parent. You should only create this specific object type once per page load in JS, as it calls `EC_Init` internally.

Inside of EC, there is a JS "test mode" that allows modification of objects that are normally not modifiable via JS. This must be enabled at compile time, or with a patch to the binary.

## Functions

<table>
  <thead>
    <tr>
      <th style="text-align:left">Method</th>
      <th style="text-align:left">Requires HTTPS?</th>
      <th style="text-align:left">Documentation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>ec.getVersion()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Returns the EC library&apos;s version number. As of the Wii Shop Channel
        v21, this is <code>264192</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.setParameter(name, value)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>Sets multiple internal EC library values.
          <br />
          <br />Known names are:
          <br />- <code>TIN</code>: a unique title number within games.
          <br />-<code>AppId</code>: the current running title ID.
          <br />-<code>PCPW</code>: Parental Control pin/password.
          <br />-<code>USE_NCRS</code>: (unknown, accepts 0/1)
          <br />-<code>SPACE_CHECK_POLICY</code>:with a value of <code>SPACE_CHECK_USER_ONLY</code> or <code>SPACE_CHECK_ENTIRE_FS</code>.</p>
        <p></p>
        <p>This calls <code>EC_SetParameter</code> internally. The Wii Shop Channel
          does not set a TIN as many games might.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getSessionValue(name)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">For the current EC object, get a value from an internally maintained type.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.setSessionValue(name, value)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Sets a key named <code>name</code> to a value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getPersistentValue(name)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Obtains a value by name from <code>ec.cfg</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.setPersistentValue(name, value)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Sets a key by name to a value in <code>ec.cfg</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getProgress()</code>, <code>ec.getProgress(id)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Obtain a value on the state of the given operation, or the most recent
        operation. Returns -4007 if no operation is ongoing.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.cancelOperation()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Cancels the current operation.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.purchaseTitle()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.purchaseGiftTitle()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.acceptGiftTitle()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.unregister()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.deleteOwnership()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.syncTickets()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.checkDeviceStatus()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.refreshCachedBalance()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getCachedBalance()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getPurchaseInfo()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getTransactionInfos()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.purchasePoints()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.downloadTitle()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.checkFirmware()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.generateKeyPair()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left">Returns -4002 - possibly not implemented?</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.confirmKeyPair()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left">Returns -4002 - possibly not implemented?</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.checkRegistration()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Makes a request via ECS for the <code>CheckRegistration</code> type.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.register()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.transfer()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.syncRegistration()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.sendChallengeReq()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getChallengeResp()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.reportCSS()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.confirmCSS()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getCSSConfirmation()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getTitleInfo()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getTitleInfos()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getTicketInfos()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getDeviceInfo()</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Returns an object you can use to access information with. See its dedicated
        page, [[ecdeviceinfo]], for more information.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.setWebSvcUrls(ecs)</code>, <code>ec.setWebSvcUrls(ecs, ias)</code> or <code>ec.setWebSvcUrls(ecs, ias, cas)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Sets endpoints for usage. <code>ecs</code> is the ECommerceSOAP endpoint, <code>ias</code> is
        the IdentityAuthenticationSOAP endpoint, and <code>cas</code> is the CatalogingSOAP
        endpoint. CAS is not used within the Wii Shop Channel - used in other ECDK-utilizing
        titles, such as for DLC content.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.setContentUrls(ccs)</code> or <code>ec.setContentUrls(ccs, ucs)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left"><code>ccs</code> appears to be an <code>http</code> URL by default, presumably
        meaning &quot;cached contents&quot;. <code>ucs</code> may mean &quot;uncached
        contents&quot;, using an <code>https</code> URL.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.checkParentalControlPassword(pin)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Validates the given Parental Control PIN/password as a long. If this is
        disabled, it returns -0xfeb/-4075.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.launchTitle(titleId, ticketId)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Launches the passed title with the given ticket.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.request(requestString)</code>
      </td>
      <td style="text-align:left"></td>
      <td style="text-align:left">Requests something, with a callback. **TODO**</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getWeakToken()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.setOption()</code>
      </td>
      <td style="text-align:left">Most likely.</td>
      <td style="text-align:left">Sets an option within EC.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.startLog()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left">Creates a new logging buffer.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.stopLog()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left">Destroys the present logging buffer.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ec.getLog()</code>
      </td>
      <td style="text-align:left">&#x2705;</td>
      <td style="text-align:left">Returns a string with the internal held log from buffer.</td>
    </tr>
  </tbody>
</table>

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


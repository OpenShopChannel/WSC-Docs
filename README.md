## Introduction

The Wii Shop Channel was an online software store made for the Wii. Since this service will be shutting down during January 2019, we've now chosen to do our best to make our own documentation in hopes that this service could possibly be revived.

### SOAP

The WSC's SOAP services were Cataloging SOAP (CAS), Identity Authentication SOAP (IAS) and ECommerce SOAP (ECS).
You can view the SOAP templates [here](https://github.com/OpenShopChannel/Open-Shop-SOAP/).

```xml
<!--
	OSC Note:
		This SOAP template is for NotifyETicketsSynced.
		Sensitive information such as the account holder's data was censored.
-->

<!-- Request -->
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
                   xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/"
                   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                   xmlns:xsd="http://www.w3.org/2001/XMLSchema"
                   xmlns:ecs="urn:ecs.wsapi.broadon.com">
<SOAP-ENV:Body>
<ecs:NotifyETicketsSynced xsi:type="ecs:NotifyETicketsSyncedRequestType">
  <ecs:Version>2.0</ecs:Version>
  <ecs:MessageId>ECSHOP-$DeviceId-$MessageId</ecs:MessageId>
  <ecs:DeviceId>$DeviceId</ecs:DeviceId>
  <ecs:DeviceToken>$DeviceToken</ecs:DeviceToken>
  <ecs:AccountId>$AccountId</ecs:AccountId>
  <ecs:Region>$Region</ecs:Region>
  <ecs:Country>$Country</ecs:Country>
  <ecs:Language>$Language</ecs:Language>
  <ecs:SerialNo>$SerialNo</ecs:SerialNo>
  <ecs:ForceSyncTime>0</ecs:ForceSyncTime>
  <ecs:ExtTicketTime>$ExtTicketTime</ecs:ExtTicketTime>
  <ecs:SyncTime>$SyncTime</ecs:SyncTime>
</ecs:NotifyETicketsSynced>
</SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### JS

WSC has it's own JS API binded to the store app itself, so we are also documenting that content. The JS can be viewed in the ["js"](https://github.com/OpenShopChannel/ShopChannel/tree/master/public_html/js/) folder of our main repo.

### Improving this documentation

This documentation is beyond incomplete, we'll need to go into more detail about the JS part, as well is include other components that WSC may use.

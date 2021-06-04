# Introduction

The Wii Shop Channel was an online software store made for the Wii. As this service shut down most functionality during January 2019, we’ve now chosen to do our best to make our own documentation in hopes that this service could possibly be revived.

## Soap

The WSC’s SOAP services were Cataloging SOAP \(CAS\), Identity Authentication SOAP \(IAS\) and ECommerce SOAP \(ECS\). You can view collected SOAP templates [here](https://github.com/OpenShopChannel/Open-Shop-SOAP/).

```markup
<!--
  OSC Note:
    This SOAP template is for NotifyETicketsSynced.
    Sensitive information such as the account holder's data was censored.
-->

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

## JavaScript

WSC has its own JS API implemented within the store app itself, so we are also documenting that content.

## Opera

The browser used in the Wii Shop Channel is powered by Opera. The browser is limited to HTML 4.1 and does not support flash. It only takes a 4:3 space in the middle of the screen - or the entire screen if on a 4:3 monitor / TV.

## Improving this documentation

This documentation is beyond incomplete. We’ll need to go into more detail about the JS part, as well as including other components that WSC may use.


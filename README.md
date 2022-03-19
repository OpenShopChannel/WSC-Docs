---
is_index: true
permalink: index.html
---

# Introduction

The Wii Shop Channel was an online software store made for the Wii. As this service shut down most functionality during January 2019, we've chosen to do our best to make our own documentation in hopes that this service could possibly be revived.

## JavaScript

The Wii Shop Channel has several JavaScript APIs exposed to Opera. This allows a webpage to more easily interact with the console, primarily via underlying SDKs.

There are 8 major components of this integration:

* [DL Tasks](js/dl-tasks.md)
* [EC](js/ec/)
* [Keyboard](js/keyboard.md)
* [Mii](js/mii.md)
* [NWC24](js/nwc24.md)
* [Shop](js/shop.md)
* [SD Card](js/sd-card.md)
* [Sound](js/sound.md)

## SOAP

EC, short for ECommerce, is a library that assists the console with title management and authentication. Many exposed functions via JavaScript interact with a corresponding EC library function to accomplish their task.

When contacting the configured server, the ECommerce library communicates via SOAP, a [protocol utilizing XML](https://en.wikipedia.org/wiki/SOAP).

There are three separate SOAP services, each handling a separate task:

* [Cataloging SOAP](soap/cas/), abbreviated as CAS
* [Identity Authentication SOAP](soap/ias/), abbreviated as IAS
* [ECommerce SOAP](soap/ecs/), abbreviated as ECS

The majority of requests within the Wii Shop Channel are IAS or ECS. CAS is most heavily used for titles handling DLCs, or video on demand services. As such, documentation for this service type should not be considered as exhaustive.

An example of a [NotifyETicketsSynced](soap/ecs/notifyeticketssynced.md) request is as follows. See [Base Format](soap/base-format.md) for more information about these values.

```xml
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

## Opera

The browser used in the Wii Shop Channel is powered by Opera. The browser is limited to HTML 4.1 and does not support flash. It only takes a 4:3 space in the middle of the screen - or the entire screen if on a 4:3 monitor / TV.

## Improving this documentation

This documentation is beyond incomplete. We'll need to go into more detail about the JS part, as well as include other components that WSC may use.

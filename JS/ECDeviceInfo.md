# ECDeviceInfo

When you need information about the user's device, you call `ECommerceInterface#getDeviceInfo()`. This ranges from storage information to device identifiers.

```javascript
var info = ec.getDeviceInfo();
```

| Method                           | Documentation                                                                                                                                                           |
| :------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `info.isKeyPairConfirmed`        | It's rather unclear on what this is to mean. There's logic elsewhere regarding keypair generation, though it's yet to been figured out.                                 |
| `info.deviceId`                  | Sourced from `ec.cfg` .                                                                                                                                                 |
| `info.serial`                    | The device's serial number, as sourced from `/title/0000001/0000002/data/setting.txt` .                                                                                 |
| `info.accountId`                 | A value returned from the server. TODO: research.                                                                                                                       |
| `info.registrationStatus`        | TODO: research. Most likely set once `ec.checkRegistration()`  is called.                                                                                               |
| `info.originalSerial`            | Blank by default. Nintendo can change the Wii's serial number when it checks registration.                                                                              |
| `info.extAccountId`              | Unknown.                                                                                                                                                                |
| `info.region`                    | The device's region, such as USA.                                                                                                                                       |
| `info.language`                  | The device's language, such as en.                                                                                                                                      |
| `info.country`                   | The device's country, such as US.                                                                                                                                       |
| `info.accountCountry`            | The account's country, such as US.                                                                                                                                      |
| `info.blockSize`                 | How many bytes a block is. This should always be 16 KiB, or 16,384 bytes.                                                                                               |
| `info.usedBlocks`                | The amount of used blocks on the device.                                                                                                                                |
| `info.totalBlocks`               | The total amount of blocks on the device.                                                                                                                               |
| `info.usedSysBlocks`             | The amount of blocks used up by system data.                                                                                                                            |
| `info.totalSysBlocks`            | The amount of blocks allocated for use to the system.                                                                                                                   |
| `info.usedUserInodes`            | The amount of Inodes available to user data.                                                                                                                            |
| `info.maxUserInodes`             | The cap on Inodes available to the user.                                                                                                                                |
| `info.usedSysInodes`             | The amount of used Inodes by the system.                                                                                                                                |
| `info.maxSysInodes`              | The cap of Inodes available to the system.                                                                                                                              |
| `info.netContentRestrictions`    | Returns an integer, with flags regarding content restriction. TODO: investigate                                                                                         |
| `info.userAge`                   | User age as defined by parental controls.                                                                                                                               |
| `info.parentalControlFlags`      | Flags regarding restrictions set via parental controls. See also: <https://wiibrew.org/wiki//shared2/sys/SYSCONF#IPL.PC>                                                |
| `info.parentalControlOgn`        | Unknown.                                                                                                                                                                |
| `info.isParentalControlEnabled`  | Boolean on whether parental controls are enabled.                                                                                                                       |
| `info.isNeedTicketSync`          | Boolean value on whether the device needs to sync tickets.                                                                                                              |
| `info.lastTicketSyncTime`        | Timestamp of some sort. A returned value was 1322524844000,                                                                                                             |
| `info.wirelessMACAddr`           | The MAC address for wireless, returned as a string (format XX:XX:XX:XX:XX:XX).                                                                                          |
| `info.bluetoothMACAddr`          | Same format and purpose as above, but for bluetooth.                                                                                                                    |
| `info.titleId`                   | The app's current title ID. For the Wii Shop Channel, that is "0001000248414241" (as a string).                                                                         |
| `info.freeChannelAppCount`       | The amount of channels currently free the Wii Menu. As each page is 4 columns with 3 rows, and there are 4 pages, there's a potential maximum of 48 channels available. |
| `info.deviceCode`                | Friend code of the device as a string.                                                                                                                                  |
| `info.accountDeviceCode`         | Same as above.                                                                                                                                                          |
| `info.isNeedTicketSyncImportAll` | Whether the device needs to import all tickets from a sync. TBD.                                                                                                        |

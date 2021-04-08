# cptc-badge-2021
## Known Issues
* Page blank or broken when trying to select SSID
** Badge ram out of ram, Please refresh page a few times, or issue this direct curl command, replacing $SSID and $PSK with your SSID and Password urlencoded.
```
curl 'http://172.217.28.1/_ac/connect' -H 'Content-Type: application/x-www-form-urlencoded' --data-raw 'SSID=$SSID&Passphrase=$PSK&dhcp=en&apply=Apply'
```
* Badge is not starting Access Point or wont connect, or is frozen or in reboot loop
** Reflash the firmware, There is a reset URL at /mqtt_clear that will wipe wifi settings as well

* There are no serial commands, only debug output.


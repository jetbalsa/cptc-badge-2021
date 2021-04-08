# cptc-badge-2021
## Known Issues
- Page blank or broken when trying to select SSID
  - Badge is out of ram, Please refresh page a few times 
  - If you don't see the submit button, its still broken. 
  - You can also try this direct curl command, replacing $SSID and $PSK with your SSID and Password urlencoded.
```
curl 'http://172.217.28.1/_ac/connect' -H 'Content-Type: application/x-www-form-urlencoded' --data-raw 'SSID=$SSID&Passphrase=$PSK&dhcp=en&apply=Apply'
```

- Badge is not starting Access Point or wont connect, or is frozen or in reboot loop
  - Reflash the firmware, There is a reset URL at /mqtt_clear that will wipe wifi settings as well

- Battery won't fit
  - Flip it! the notch goes down you should be able to see the pin cut outs. 

- How do I make the meter go up?
  - Did you know that LEDs can act like Photo Resistors? Well you do now!

-There are no serial commands, only debug output.




# cptc-badge-2021
## Security Issues
Please submit all found security issues as a Github Issue, Make sure to use the Security Issues Template for more details. you will need to include steps to reproduce the issue. If you are the first to submit a issue your name/names/team/universitys to be put on the main Security Issue Writeup forever!

Your writeup will be reviewed, if it is lacking info or overall poor on details that a newbie cannot reproduce the issue or exploit, your issue will get rejected. 
JRWR reserves the right to reject issues and is overall the keeper of the board.

## Spoilers are contained under the spoilers folder
- This includes full source code to things if you wish to do a whitebox assessment. For the most fun and training, never look in this folder!

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

- There are no serial commands, only debug output.

## How to Reflash the device
Easy! 
``` 
pip install esptool
esptool.py --chip esp8266 --port COM11 --baud 115200 erase_flash
esptool.py --chip esp8266 --port COM11 --baud 115200 --before default_reset --after hard_reset write_flash 0x0 cptc-ngpew-1.ino.nodemcu.bin 
```
Don't forget to replace COM11 with your serial port and point to the location of the frimware.


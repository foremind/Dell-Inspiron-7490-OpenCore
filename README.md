# Dell-Inspiron-7490-OpenCore

This repository documents my effort to install (unmodified) Ubuntu Linux and OpenCore Hackintosh onto a Dell Inspiron 7490 notebook.

Please check out the Fix-BIOS-Settings directory as the 7490 requires a critical change to the BIOS related to AHCI before one can install OpenCore or unmodified Ubuntu Linux on it.

I have a 95% working 7490 running Big Sur 11.6.3. using OpenCore 0.7.7.

Working

1. Graphics (with full acceleration)
2. WiFi (seems to have trouble connecting to 5Ghz signals, need further tests, could be my WiFi signal's fault)
3. Bluetooth
4. Sound (with volume control using hot keys)
5. HDMI - external only or together with notebook screen (I only tested a cheap 1920 x 1080 (HDMI 1.4?) monitor)
6. USB2 and USB3 (need rhub.asl initially to do USBMap mapping, other the internal Bluetooth and touchpad interfaces won't show up)

Mostly Working

1. Touchpad - fully functional using VoodooI2CHID

Sometimes after powering on the touchpad may disappear, another (1 or 2) reboots usually will fix that, likely some problems with Voodoo drivers and perhaps even a race condition?

Not Working

1. Screen brigtness using hot keys

The software slider under display preferences works though.

2. Sleep

System will wake up after at most 30 seconds, likely some USB problems. Disabling Bluetooth via the preferences panel doesn't seem to help. But disabling it by USBMap seems to at least stop the screen from waking up. I am not sure the machine is truly sleeping though as I am able to SSH into it all the time while the screen is off (machine supposely sleeping).

I will upload my config.plist and OpenCore directories in a moment. I hope other 7490 owners can help me get the rest of the features working.

Btw, installing Ubuntu is a lot easier (once the BIOS is in AHCI mode) and the system works 100%.


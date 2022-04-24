# Dell-Inspiron-7490-OpenCore

*** Uploaded files for Monterey 12.3.1. Nothing changed, whatever that were working still work, and things with occasional problems still do. Sleep is still broken. ***

This repository documents my effort to install (unmodified) Ubuntu Linux and OpenCore Hackintosh onto a Dell Inspiron 7490 notebook.

Please check out the Fix-BIOS-Settings directory as the 7490 requires a critical change to a BIOS setting related to AHCI before one can install OpenCore or unmodified Ubuntu Linux on it.

I have a 95% working 7490 running Big Sur 11.6.3 using OpenCore 0.7.7.

Working

1. Graphics (with full acceleration)
2. WiFi (seems to have trouble connecting to 5Ghz signals, need further tests, could be my WiFi signal's fault)
3. Bluetooth
4. Sound (with volume control using hot keys)
5. HDMI - external only or multi-screen with built-in display (I only tested with a cheap 1920 x 1080 (HDMI 1.4?) monitor)
6. USB2 and USB3 (need rhub.asl initially to create the USBMap mapping, otherwise the internal Bluetooth and touchpad interfaces won't show up)

Mostly Working

1. Touchpad - fully functional using VoodooI2CHID

Sometimes after powering on the touchpad (and therefore your built-in mosue!) may disappear, another (2 or 3) hot reboots will usually fix that, but you will either need an external mouse or hold the power button to shut it down. Likely some problems with Voodoo drivers and perhaps even a race condition?

Not Working

1. Screen brightness using hot keys

The software slider under display preferences works though so it's not a showstopper.

2. Sleep

System will wake up after at most 30 seconds, likely some USB problems. Disabling Bluetooth via the preferences panel doesn't seem to help. But disabling it by USBMap seems to at least stop the screen from waking up. I am not sure the machine is truly sleeping though as I am able to SSH into it all the time while the screen is off (machine supposely sleeping).

I will upload my config.plist and OpenCore directories soon. I hope other 7490 owners can help me get the rest of the features working.

Btw, installing Ubuntu is a lot easier (once the BIOS is in AHCI mode) and the system works well except the fan comes on quite often.


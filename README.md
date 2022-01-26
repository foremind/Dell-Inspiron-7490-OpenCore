# Dell-Inspiron-7490-OpenCore

Before anything else, please go to the Fix-BIOS-Settings directory and patch your BIOS.

I have a 95% working Dell Inspiron 7490 running Big Sur 11.6.2. using OpenCore 0.7.7.

Working

1. Graphics (with full acceleration)
2. WiFi (seems to have trouble connecting to 5Ghz signals, but need further tests, could be my WiFi signal's fault)
3. Bluetooth
4. Sound (with volume control using hot keys)
5. External HDMI only or together with notebook screen (I only tested a cheap 1920 x 1080 (HDMI 1.4?) monitor)
6. USB2 and USB3 (after USBMap)

Mostly Working

1. Touchpad - full functions using VoodooI2CHID (sometimes after powering on the touchpad may disappear, another (1 or 2) reboots usually will fix that)

Not Working

1. Screen brigtness using hot keys (the software slider under display preferences works though)
2. Sleep (will wake up after at most 30 seconds, likely some USB problems, disabling Bluetooth using USBMap seems to fix that, but I want my Bluetooth!)

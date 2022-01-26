The following information is accurate as of BIOS 1.11.0 (released Jan 13, 2022). If you have a different BIOS version, DO NOT carry out the setup_var operations without further investigation as the offets may change between BIOS releases. Patching the wrong offsets may brick your computer.

The BIOS of Dell Inspiron 7490 locks the disk interface into Intel RAID mode, but both macOS and (most) Linux distributions expect AHCI mode. Without AHCI the installation of macOS / Linux will go nowhere. On the Inspiron 7490 there is no user selectable settings in the BIOS screen to change that.

The BIOS also locks the DVMT pre-allocated video memory to 32M, again there is no user selectable settings in the BIOS screen to change that. Changing this setting to 64M will save us lots of macOS graphics troubles later on.

macOS also requires the CFG_LOCK flag of the CPU be disabled. While OpenCore can handle this issue in the configuration file, we may as well do it in the BIOS.

Luckily we can change the relevant BIOS settings manually.

1. Create a FAT32 format USB stick
2. Copy the BOOT directory onto the top level of the USB stick
3. Boot the Inspiron 7490 from the USB stick and issue the following commands:

setup_var PchSetup 0x44 0

setup_var SaSetup 0xF5 2

setup_var CpuSetup 0x3E 0


The 1st setup_var command puts the disk interface into AHCI mode.
The 2nd setup_var command sets the DVMT pre-allocated video memory to 64M.
The 3rd setup_var command unlocks the CFG_LOCK setting.

Power down the computer and proceed to normal OpenCore / Linux installation.

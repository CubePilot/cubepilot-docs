# SB\_0000010 Mandatory Here4 Bootloader Update before Further Flight

**For the latest updates, refer to the following link:**\
[SB\_0000010 Mandatory Here4 bootloader update before further flight](https://discuss.cubepilot.org/t/sb-0000010-mandatory-here4-bootloader-update-before-further-flight/15630)

## BEFORE FURTHER FLIGHT

### Urgent Bootloader Update needed on Here4 If your Here4 doesn’t breath blue on boot, then you MUST do this bootloader update <a href="#p-42708-urgent-bootloader-update-needed-on-here4-if-your-here4-doesnt-breath-blue-on-boot-then-you-m" id="p-42708-urgent-bootloader-update-needed-on-here4-if-your-here4-doesnt-breath-blue-on-boot-then-you-m"></a>

All Here4 users need to update the bootloader on their Here4 units BEFORE FURTHER FLIGHT.

#### For units NOT showing blue breathing at boot <a href="#p-42708-for-units-not-showing-blue-breathing-at-boot-3" id="p-42708-for-units-not-showing-blue-breathing-at-boot-3"></a>

The process for doing this update is as follows:

* Follow the steps here to update the firmware [https://docs.cubepilot.org/user-guides/here-4/here-4-manual#id-3.-firmware-update](https://docs.cubepilot.org/user-guides/here-4/here-4-manual#id-3.-firmware-update)
* Once the Update is done, set parameter on Here4 FLASH\_BOOTLOADER to 1 wait for either Bootloader Flash OK or Bootloader Unchanged message
* An updated bootloader boots with Blue Breathing at boot. It will breathe purple if CAN1 on here4(blue/white cable) is not connected or Cube is still booting, so to check best to unplug and plug Here4 without power cycling the Cube itself.
* Use the Blue/white Can cable on the here 4 to CAN 1 or 2 on the Cube carrier board

#### For units already showing solid White LED (NOT breathing) <a href="#p-42708-for-units-already-showing-solid-white-led-not-breathing-4" id="p-42708-for-units-already-showing-solid-white-led-not-breathing-4"></a>

If you have appropriate SWD connector (6pin JST SUR) to Here4 available, and are capable of doing a bootloader update. Follow the following steps:

**For STLink:**

* Use this [bootloader file](https://github.com/CubePilot/GNSSPeriph-release/raw/refs/heads/release/bootloaders/Here4_bl.bin) and flash at address 0x08000000

**For JLink:**

* Use this [bootloader file](https://github.com/CubePilot/GNSSPeriph-release/raw/refs/heads/release/bootloaders/Here4_bl.hex) use JFlashLite to flash.

**Important: For users that are not capable of opening Here4 unit and updating using JST SUR and Debug probe to fix solid white LED, please contact your Reseller for further support. For units that are still healthy make sure to follow primary bootloader update method.**

Additional Resources:

* [Batch Update Tool](https://github.com/CubePilot/DroneCAN-Batch-Updater/blob/v0.0.1/Here4%20Batch%20Update%20User%20Manual.md)
* [Here4 FW Release 1.15.0](https://github.com/CubePilot/GNSSPeriph-release/releases/tag/v1.15.0)

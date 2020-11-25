---
description: The following article shows how to  update the firmware of Herelink Units
---

# How To Update Firmware

Herelink can be updated on PC, Mac and Linux as per the below process. Newer firmware versions allow you to update the Herelink remote via wifi from with-in the settings app, this is only available if you have the Solex TX app installed.

## Flashing Firmware Ground Station

1. Connect the Herelink Remote unit to your PC via USB.
2. Put the Herelink Remote Unit into Fastboot by pressing **Power** and **D** button simultaneously while turning on.
3. Download [flasher\_win.zip](https://herelinkfw.cubepilot.org/flasher_win.zip) [flasher\_mac.zip](https://herelinkfw.cubepilot.org/flasher_mac.zip) or [flasher\_linux.zip](https://herelinkfw.cubepilot.org/flasher_linux.zip).
4. Extract and Run the application packaged inside the zip file.
5. After Remote Unit upgrade is complete the Unit will automatically restart once finished.
6. Herelink Remote Unit will boot up with Activation window, follow the steps below to continue.

{% hint style="info" %}
In some Windows systems it's been found that due to incorrect Driver setup, Herelink units fail to be detected. In such cases please power up by pressing Power+D button until "Fastboot" screen shows up. Install driver from here [https://developer.android.com/studio/run/win-usb](https://developer.android.com/studio/run/win-usb). In cases where driver was already installed, Uninstall Device from Device manager \(Ensure to check the "also uninstall driver" option\), and then reconnect and install the correct driver from Google.
{% endhint %}

## Flashing Firmware Air End

**Important: Before proceeding the air unit must be connected to a suitable power supply and antennas must be connected at all times.**

The air end update process is the same as the ground station above apart from there is not requirement to place the unit in Fastboot as per step 2 before starting.

### VIDEO TUTORIAL \(Step by step\)

{% embed url="https://youtu.be/2lGEtJCBovY" caption="" %}

## Herelink Activation

After upgrading the Herelink firmware you may be required to activate your device, you will be presented with the 'Update Device' Screen

**Note: Herelink must be connected to an internet connection via WiFi to activate.**

* Connect Herelink to your WiFi connection from the settings menu

![](../../.gitbook/assets/activation1.jpg)

* Select your region then click 'Proceed'

![](../../.gitbook/assets/activation3.jpg)

* You will then be prompted to input your 16 digit software activation key. 

**Note:On later Herelink versions your key will be located on the box, for earlier Herelink versions you should contact your original reseller to obtain a valid licence key.**

![](../../.gitbook/assets/activation2.jpg)

![](../../.gitbook/assets/activation4.jpg)

* Once input click 'done' the 'Register' and your device will then download the latest software and update itself. 

## Herelink Remote Update Via Wifi

If your Herelink has Solex TX installed you can now update your ground station via the built in update feature.

**Note: The air end will still need to be updated via the above process.**

* Make sure you Herelink is connected to wifi and has an internet connection available
* Pull down from the top and select the settings cog in the top corner 

![](../../.gitbook/assets/settings-1.jpg)

* Scroll to the bottom and click the 'About phone' option

![](../../.gitbook/assets/settings.jpg)

* Select 'System Update' 

![](../../.gitbook/assets/system-update.jpg)

* Select 'CHECK FOR UPDATE' in the bottom corner 

![](../../.gitbook/assets/update.jpg)

* The system will now check for an update and install it automatically

![](../../.gitbook/assets/updating.png)

## Herelink Remote Update Update Error

There are 3 things the need to be checked if you receive an error

1. You are connected to stable wifi 
2. The device time is correct
3. You entered the correct Key


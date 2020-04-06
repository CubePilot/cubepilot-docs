---
description: The following article shows how to  update the firmware of Herelink Units
---

# How To Update Firmware

Herelink can be updated on PC,Mac and Linux as per the below process. Newer firmware versions allow you to update the Herelink remote via wifi from with-in the settings app, this is only available if you have the Solex TX app installed. 

The Air end is updated via the same process as the remote via PC,Mac and Linux only.  

## PC,Mac and Linux Update 

### Android Tools

Install Android Tools

Download and Install latest Android SDK Platform tools from [here](https://developer.android.com/studio/releases/platform-tools) per the system you are using.

### Download Firmware

Download the latest image from [Firmware Releases](firmware-releases.md) section.

## Flashing Firmware

### Windows

1. Connect the Herelink or Air unit to you PC via USB
2. Download the firmware file and run the executable file, windows may try to block the file from running!  click 'More Info' and then select 'Run Anyway' to allow the update to start. 
3. The batch script will start executing, wait for script to complete.
4. After Remote Unit upgrade is complete, you can connect Air Unit and repeat the process from 1-3.
5. The Units will automatically restart and will retain user settings from previous update

### Mac

1. Connect the Herelink or Air unit to you Mac via USB
2. Download the Mac firmware file and run the executable file, OSX may try to block the file from running! You may need to click allow  from your security and privicy settings. 
3. The batch script will start executing, wait for script to complete.
4. After Remote Unit upgrade is complete, you can connect Air Unit and repeat the process from 1-3.
5. The Units will automatically restart and will retain user settings from previous update


### Linux

Open Terminal and Execute following commands \(Replace RemoteUnit\_x\_x\_x with AirUnit\_x\_x\_x when trying to upgrade Air Unit\). Following commands will work if the files are present in the Downloads Directory, please modify the path in case you are using different directories.

```bash
cd ~/Downloads                        #navigate to the platform tool archive
unzip platform-tools_rx.x.x.zip       #decompress platform archive
export PATH=$HOME/Downloads/platform-tools:$PATH
tar -xvjf RemoteUnit_x_x_x.tar.gz     #extract the archive
cd ~/Downloads/RemoteUnit_x_x_x       #navigate to decompressed folder
adb reboot bootloader                 #reboot into bootloader
chmod +x flash_all_except_data.sh     #make script to be executable
./flash_all_except_data.sh            #run the script
```

{% hint style="info" %}
Please Note that using **`flash_all_except_data_storage`** script will retain previous user settings. In case the unit hasn't been upgraded for a long time and/or you are updating Beta1 hardware for the first time. It is advisable to use **`flash_all`** script to update your hardware and follow the [One Time Setup](one-time-setup.md).
{% endhint %}

{% hint style="info" %}
If you don't see any activity immediately after running the script, please disconnect and reconnect the Unit, and rerun the script. Also make sure that Air Unit is powered up separately when updating.
{% endhint %}



## Herelink Activation

After upgrading the Herelink firmware you may be required to activate your device, you will be presented with the 'Update Device' Screen

![](../.gitbook/assets/activation1.jpg)

* You must first connect your Herelink to a internet connection via WiFi

* Once connected click 'Proceed'

* You will be prompted to select your country and then register your device. To do this you must input your 16 digit software key, on later versions this will be located on you box, for earlyier Herelink models you should contact your reseller to obtain a key. 

* Click 'Register' and you device will then download the latest software and update and be ready to use. 



### VIDEO TUTORIAL \(Step by step\)

{% embed url="https://www.youtube.com/watch?v=tKAkAtZOPvc" caption="" %}



## Herelink Remote Update Via Wifi

If your Herelink has Solex TX installed you can now update your ground station via the built in update feature. 

**Note: The air end will still need to be updated via the above process.** 

* Make sure you Herelink is connected to wifi and has an internet connection available
* Pull down from the top and select the settings cog in the top corner 

![](../.gitbook/assets/settings-1.jpg)

* Scroll to the bottom and click the 'About phone' option

![](../.gitbook/assets/settings.jpg)

* Select 'System Update' 

![](../.gitbook/assets/system-update.jpg)

* Select 'CHECK FOR UPDATE' in the bottom corner 

![](../.gitbook/assets/update.jpg)

* The system will now check for an update and install it automatically

![](../.gitbook/assets/updating.png)

* After updating you may be promoted to activate your device again see the above steps to complete this. 


 


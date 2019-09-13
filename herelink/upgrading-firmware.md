---
description: >-
  The following article shows how to manually update the firmware of Herelink
  Units
---

# Upgrading Firmware

## Install Android Tools

Download and Install latest Android SDK Platform tools from [here](https://developer.android.com/studio/releases/platform-tools) per the system you are using.

## Download Firmware

Download the latest image from [Firmware Releases](firmware-releases.md) section.

## Flashing Firmware

### Windows

1. Download both the Platform tools and the latest Firmware file
2. Extract the downloaded archives using an Archive Tools like 7-zip.
3. Place the platform tools files inside the firmware folder. So that `adb.exe` is along side `flash_all_except_data_storage.bat`  
4. Connect Remote Unit/Air Unit \(only connect one at any one time\) via USB Micro Cable.
5. Open the Command Prompt and run `[your extracted SDK folder]\adb reboot bootloader` from the prompt.
6. Navigate to the extracted folder relating to the specific unit and double click `flash_all_except_data_storage.bat` 
7. The batch script will start executing, wait for script to complete.
8. After Remote Unit upgrade is complete, you can connect Air Unit and repeat the process from 3-5.
9. The Units will automatically restart and will retain user settings from previous update

### Mac/Linux

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

### VIDEO TUTORIAL \(Step by step\)

{% embed url="https://www.youtube.com/watch?v=tKAkAtZOPvc" caption="" %}


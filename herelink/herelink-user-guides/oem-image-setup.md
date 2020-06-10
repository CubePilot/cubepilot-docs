---
description: >-
  This article shows how OEMs can create images including custom applications
  and settings
---

# OEM Image Setup

The OEM changes are constant changes made by OEMs of Herelink that will be untouched by Over the Air updates provided to herelink systems. The changes include Boot Animation changes, System configurations, Android Applications, Android properties.

## Linux

### Prerequisites

* [android-tools](https://developer.android.com/studio/releases/platform-tools)

### Steps

* Download and unzip following files:
  * [simg2img](https://herelinkfw.cubepilot.org/tools/simg2img_linux.zip)
  * [img2simg](https://herelinkfw.cubepilot.org/tools/img2simg_linux.zip)
  * Remote Unit: [oem\_ru\_base.img](https://herelinkfw.cubepilot.org/tools/oem_ru_base.img)
  * Air Unit: [oem\_au\_base.img](https://herelinkfw.cubepilot.org/tools/oem_au_base.img)
* Ensure that you select the base image depending upon which unit you are modifying.
* Download and extract zips into same directory.
* Now to generate ext4fs image from the sparse image \(.img\) downloaded above do `./simg2img_mac oem_au_base.img raw_oem_au_base.img`
* Create a mount point directory using `mkdir oem`
* Mount the image using `mount raw_oem_au_base.img oem`
* Now you should be able to modify files inside the mount directory.
* You need to use `sudo` to be able to do any writes the files inside the mount point.
* Once you have made your changes, you need to unmount your drive using command `sudo umount oem`
* Afterwards convert the ext4fs image back to android sparse image using command `./img2simg raw_oem_au_base.img oem_au.img`
* Now you may flash this image into Herelink Air Unit, by putting it under bootloader using command `adb reboot bootloader`
* And finally to flash to image run command `fastboot flash oem oem_au.img`
* Check example below for a sample modification.

## MacOS

### Prerequisites

* [Homebrew](https://brew.sh/)
* [android-tools](https://developer.android.com/studio/releases/platform-tools)

### Steps

* Setup osxfuse in your system using `brew cask install osxfuse`, this will require rebooting your system proceed and do that.
* Follow the steps [here](https://github.com/alperakcan/fuse-ext2#macos) to install fuse-ext2. This will allow you to mount ext4fs we will be generating.
* Download and unzip following files:
  * [simg2img](https://herelinkfw.cubepilot.org/tools/simg2img_mac.zip)
  * [img2simg](https://herelinkfw.cubepilot.org/tools/img2simg_mac.zip)
  * Remote Unit: [oem\_ru\_base.img](https://herelinkfw.cubepilot.org/tools/oem_ru_base.img)
  * Air Unit: [oem\_au\_base.img](https://herelinkfw.cubepilot.org/tools/oem_au_base.img)
* Ensure that you select the base image depending upon which unit you are modifying.
* Download and extract zips into same directory.
* Now to generate ext4fs image from the sparse image \(.img\) downloaded above do `./simg2img_mac oem_au_base.img raw_oem_au_base.img`
* Create a mount point directory using `mkdir oem`
* Mount the image using `fuse-ext2 raw_oem_au_base.img oem -o rw+`
* Now you should be able to modify files inside the mount directory.
* You need to use `sudo` to be able to do any writes the files inside the mount point.
* Once you have made your changes, you need to unmount your drive using command `sudo umount oem`
* Afterwards convert the ext4fs image back to android sparse image using command `./img2simg raw_oem_au_base.img oem_au.img`
* Now you may flash this image into Herelink Air Unit, by putting it under bootloader using command `adb reboot bootloader`
* And finally to flash to image run command `fastboot flash oem oem_au.img`

### Example Config Change

* In the following example we change the system\_id used by herelink air unit for board specific messages.
* Most config files are located in you unit at `/system/etc`in the following example we will pull config using command `adb pull /system/etc/system-control.telepathy-air.conf`
* Once pulled the file will contain information like bellow:

```bash
# module on/off
board_control_enabled = true
d2d_tracker_enabled = true
camera_control_enabled = true

# board control
board_system_id = 42

# camera control
video_stream_ip_address = 192.168.0.10
camera_system_id = 42
support_multiple_camera = true
support_camera_capture = false
```

* You can change the value of `board_system_id` and `camera_system_id` fields as per your requirement in your favourite editor.
* Once done save this file and exit editor.
* Create a folder inside oem image called `etc` using command `sudo mkdir oem/etc`
* Copy file using command `sudo cp system-control.telepathy-air.conf oem/etc/`
* Continue to unmount the image and flashing into the unit as described in above steps.

### Example App Change

* In the following example we override the installed QGroundcontrol App.
* A new OEM app can be installed under /oem/app/&lt;AppName&gt;/&lt;AppName&gt;.apk
* For installing your custom version of QGroundcontrol, ensure that you started with [https://github.com/cubepilot/qgroundcontrol-herelink](https://github.com/cubepilot/qgroundcontrol-herelink) as your base.
* After building the project, create a folder `QgroundControl`
* Copy .apk file `cp -r build-qgroundcontrol-Android_for_armeabi_v7a_Clang_Qt_5_11_0_for_Android_armv72_fd6ff4-Debug/android-build/build/outputs/apk/android-build-debug.apk QGroundControl/QGroundControl.apk`
* Also create a lib directory `QGroundControl/lib`
* Copy libraries `cp -r build-qgroundcontrol-Android_for_armeabi_v7a_Clang_Qt_5_11_0_for_Android_armv72_fd6ff4-Debug/android-build/libs/armeabi-v7a/ QGroundControl/lib/arm/`
* Finally move QgroundControl directory to oem image `sudo cp -r QGroundControl oem/app/QGroundControl`
* Do ensure you have already created app directory inside oem image if not already done `sudo mkdir oem/app`
* Continue to unmount the image and flashing into the unit as described in above steps.

### Extra OEM Files

* On boot several files are setup for use, and you can override these files
* These files can exist in \(searched in this order\)
  * /data/oem/etc - user default - wiped on factory reset
  * /oem/etc - oem default
  * /system/etc - system default
* files that can be overridden \(optimus is the internal GCS name, telepathy-air is the air unit \(ro.product.device\)\)
  * lampsignal-telepathy-air.json
  * rc\_service\_config\_optimus.ini
  * mavlink-router.optimus.conf
  * system-control.optimus.conf


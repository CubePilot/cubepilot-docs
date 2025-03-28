---
description: "Herelink \bFAQ Resources"
---

# Herelink FAQ

## Herelink - Register Failure

**-Wi-Fi**\
&#xNAN;_&#x35;.8GHz_ \
&#xNAN;**-IP Address**\
&#xNAN;_&#x4E;ot in range 192.168.0.x_\
&#xNAN;**-Region**\
&#xNAN;_&#x53;elect the correct region and within 5mins difference_\
\
_\*_ Please check and fulfil three requirements, otherwise register failure as a result

## Herelink - Solex as Autostarting App

[**Solex as autostarting app**](https://discuss.cubepilot.org/t/solex-as-autostarting-app/3893)

## Herelink - Screenshot

[**Open-Source Scrcpy To Control Android Via Windows & macOS**](https://discuss.cubepilot.org/t/herelink-screenshot/3881)

## Herelink - Video / Camera&#x20;

#### [Herelink - Compatible camera list](https://discuss.cubepilot.org/t/herelink-compatible-camera-list/1922)&#x20;

\*Latest update please check the URL above, thank you!

Below the list of the cameras which have been tested and reported working or not working with the Herelink\
Any help to grow the list is welcome. If there is any specific settings to use, please tell it.

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* Working \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

Canon EOS M3\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
GoPro 3\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
GoPro 4\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
GoPro 5\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
GoPro 7\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
GoPro 8\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings (with its Media Module)\
ZCam E1\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Foxeer Box2\_\_\_\_\_\_\_\_\_\_\_Specific settings (search for [@UlrichC](https://discuss.cubepilot.org/u/ulrichc) message for full infos)\
Flir Duo Pro\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony AS200V\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony NEX-3N\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony a5100\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony A6000\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony A6300\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony A7R\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony A7Rii\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony RX1Rii\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony RX0 mki\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony RX100VI\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Sony HX50\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
SONY HDR-CX450\_\_\_\_\_\_\_Stock/out of the box settings\
SONY HDR-PJ620\_\_\_\_\_\_\_Stock/out of the box settings\
SONY HDR-CX440\_\_\_\_\_\_\_Stock/out of the box settings\
Foxeer HS1223\_\_\_\_\_\_\_\_\_\_Set resolution to 1080p 30fps with Foxeer app\
Foxtech Seeker 30 max\_\_\_Stock/out of the box settings\
Waltter move 500\_\_\_\_\_\_\_\_Stock/out of the box settings\
Hawkeye Firefly split 4k\_\_\_Stock/out of the box settings (firmware 20190926 works better than others)\
Firefly Q6\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Optris PI-Series\_\_\_\_\_\_\_\_\_Stock/out of the box settings (via companion computer with MS Windows)\
EKEN H9R\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings\
Black Magic micro cinema\_Stock/out of the box settings\
NextVision cameras with TRIP2 accessory\_Stock/out of the box settings\
Workswell Wiris Mini\
Workswell Wiris and Wiris 2nd Generation

\*\*\*\*\*\*\*\*\*\*\*\* Not Working \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\
Xiaomi Yi

## Herelink - Connection

#### [Flight mode turn off to maintain connection stability ](https://discuss.cubepilot.org/t/disconnection-bug/3845)

Airplane mode is designed for manually disconnect the air unit and controller. Connection breaks when you turn it on.

## Herelink - Antenna

#### [Herelink controller antenna plug](https://discuss.cubepilot.org/t/name-of-herelink-antenna-on-the-remote/3864/3)

Mini BNC

## Herelink - Calibration

[**Refer to - Herelink User Guides - Pairing, RC Calibration & Setup**](herelink-user-guides/one-time-setup.md)

## Herelink - Encryption

#### [Herelink encryption](https://discuss.cubepilot.org/t/support-for-encryption/1370)

Herelink encrypt over the air uses aes-128-ctr&#x20;

## Herelink - Ethernet

[**Herelink Ethernet**](https://discuss.cubepilot.org/t/herelink-ethernet/4369) \
\
I’m trying to get ethernet passthrough working. I’m running on the Beta Channel, SRU01200616 on the ground unit and the corresponding version on the airside.

I understand an ethernet adapter with a R8152/8153 chip is required, I have an ANKER A7610011 and a Cable Matters 202023-BLK for testing. Both use the correct chip according to the Amazon comments, although it's very hard to get the information directly from the manufactures.

On the ground side, I have a generic OTG adapter and have tested it with a USB stick. On the airside I have an OTG charging passthrough cable, this allows to power the adapter (and the airside, and cube, I’m not sure if that is a good idea).

I understand with an adapter on both ends it should be a transparent link but I can't seem to get it working.

It does have to be said that I am a complete beginner with regard to networking stuff such as this.

**The next trick is getting ADB access to confirm (GCS)**\
\
Here is a new bootimage for the GCS unit to make the R8152/53 detect. [https://drive.google.com/file/d/1MGFAqC1zXrdnO2yEGhaigW-xktIx2cHj/view?usp=sharing 2](https://drive.google.com/file/d/1MGFAqC1zXrdnO2yEGhaigW-xktIx2cHj/view?usp=sharing) (GCS unit bootimage with R8152)\
the stock image includes\
AX8817X\
AX88179\_178A\
NET1080

to update the boot image via USB (i assume you have ADB access already/developer mode)

> adb reboot bootloader\
> fastboot flash boot boot.img\
> fastboot reboot

Next, we enable ADB via TCPIP, but first, we need to enable this via USB

> adb shell\
> setprop persist.adb.tcp.port 5555\
> reboot

then after the reboot, get the IP of the GCS unit (eg 10.0.0.99)

> adb connect 10.0.0.99\
> adb shell

you should get the shell again\
do a

> ifconfig

and check if eth0 exists

Now verify we can ADB into the air unit\
once you have ADB to the GCS unit, power on the air unit and do a

> adb shell (gets you into the gcs unit)\
> adb connect 192.168.0.10\
> adb -s 192.168.0.10:5555 shell

this should now get you into the air unit.

Next\
try running a

> /bin/busybox brctl show

under interfaces, you should see vxlan1 and eth0

> optimus:/ $ /bin/busybox brctl show\
> bridge name bridge id STP enabled interfaces\
> br-vxlan 8000.00e04c360345 no vxlan1\
> eth0

also, run

> ping 192.168.144.10\
> ping 192.168.144.11

these are the bridge endpoint IP’s

during testing, make sure the screen stays on there GCS unit, otherwise, power-saving features limit background data flow (A most likely setting I have not found yet)

I've just confirmed that this is working ok. one possible caveat. if your home network is using 192.168.0.x, things may not work.



## Herelink - Power output

The power outputs by selecting region are :

* USA : 23dB      = 200mW
* Europe : 20dB = 100mW
* China : 20dB    = 100mW
* Japan : 20dB   = 100mW

## Herelink airunit fan installation

When using Dual Streaming mode, the Herelink can get quite warm, for best results, please install a fan on the top using the provided screws, rubber rings, washers and nuts in the installation pack.

\*Fan is not provided The fan showing in the video obtained from Digi-Key URL: [https://www.digikey.hk/product-detail/en/mechatronics-fan-group/MR3010E12B-RSR/1570-1346-ND/7606131](https://www.digikey.hk/product-detail/en/mechatronics-fan-group/MR3010E12B-RSR/1570-1346-ND/7606131)

\*Please prepare a pair of tweezers and a M1.6 nut driver for installation.

{% embed url="https://www.youtube.com/watch?v=n-0xik3lVfE" %}

## Herelink flasher update error

Q: When connecting the Herelink to computer to update it with flasher, the following message pops up:

_Looking for DeviceTraceback (most recent call last):_ \
_File "flasher.py", line 260, in_  \
_File "flasher.py", line 142, in detectuntilfound_ \
_File "flasher.py", line 238, in detectunit_ \
_File "site-packages\adb-1.3.0-py3.8.egg\adb\adbcommands.py", line 138, in ConnectDevice_ \
_File "site-packages\adb-1.3.0-py3.8.egg\adb\common.py", line 221, in FindAndOpen_ \
_File "site-packages\adb-1.3.0-py3.8.egg\adb\common.py", line 117, in Open_ \
_File "site-packages\usb1\_init\_.py", line 2168, in open_ \
_File "site-packages\usb1\_\_init.py", line 133, in mayRaiseUSBError_ \
_File "site-packages\usb1\_\_init.py", line 125, in raiseUSBError_ \
_usb1.USBErrorAccess: LIBUSB\_ERROR\_ACCESS \[-3]_ \
_\[11936] Failed to execute script flasher_

A: The error message tells that the adb is running already. It can be fixed with the following command: \
**adb kill-server**

## Herelink Dual Video Instruction

**\*\*\*Enabling this feature will get Herelink very hot. Please install \***[**cooling fan**](https://docs.cubepilot.org/user-guides/herelink/herelink-faq#herelink-airunit-fan-installation)**\* on Herelink otherwise it will be overheated soon.\*\*\***

#### Prerequisite

1. Install ADB and Google drivers
2. Then Setting-up the device for ADB

Steps are same as step 1 and 2 in `Generate a bug report` instruction:

{% embed url="https://docs.cubepilot.org/user-guides/herelink/herelink-user-guides/generate-a-bug-report" %}

#### Enable Multiple Video Stream via ADB

Connect controller unit to computer via ADB and run

> adb shell setprop persist.multiple.videostream true\
> \
> adb reboot

Then repeat on air unit. Both of them need the setprop set.

The video stream will be available at these 2 addresses

> rtsp://(wifiIPongcs):8554/fpv\_stream\
> rtsp://(wifiIPongcs):8554/fpv\_stream1

#### Notice

1. Ensure something valid is connected to HDMI1 also, otherwise HDMI2 will not work.
2. Ensure [cooling fan](https://docs.cubepilot.org/user-guides/herelink/herelink-faq#herelink-airunit-fan-installation) is connected, else the air unit will be overheated.

#### Disable Multiple Video Stream

To disable and restore the setting, connect the unit to computer via ADB and run

> adb shell setprop persist.multiple.videostream false\
> \
> adb reboot


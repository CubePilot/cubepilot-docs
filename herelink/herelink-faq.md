---
description: "Herelink \bFAQ Resources"
---

# Herelink FAQ

## Herelink - Register Failure

**-Wi-Fi**  
_5.8GHz_   
**-IP Address**  
_Not in range 192.168.0.x_  
**-Region**  
_Select the correct region and within 5mins difference  
  
\*_ Please check and fulfil three requirements, otherwise register failure as a result

## Herelink - Solex as Autostarting App

[**Solex as autostarting app**](https://discuss.cubepilot.org/t/solex-as-autostarting-app/3893)\*\*\*\*

## Herelink - Screenshot

[**Open-Source Scrcpy To Control Android Via Windows & macOS**](https://discuss.cubepilot.org/t/herelink-screenshot/3881)\*\*\*\*

## Herelink - Video / Camera 

#### [Herelink - Compatible camera list](https://discuss.cubepilot.org/t/herelink-compatible-camera-list/1922) 

Below the list of the cameras, which have been tested and reported working or not working with the Herelink  
Any help to grow the list is welcome. If there is any specific settings to use, please tell it.

\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* Working \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

GoPro 3\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
GoPro 4\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
GoPro 5\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
GoPro 7\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
GoPro 8\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings \(with its Media Module\)  
ZCam E1\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Foxeer Box2\_\_\_\_\_\_\_\_\_\_\_Specific settings \(search for [@UlrichC](https://discuss.cubepilot.org/u/ulrichc) message for full infos\)  
Flir Duo Pro\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony AS200V\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony a5100\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony A6000\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony A6300\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony A7R\_\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony A7Rii\_\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony RX1Rii\_\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony RX0 mki\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Sony RX100VI\_\_\_\_\_\_\_\_\_\_\_Stock/out of the box settings  
Foxeer HS1223\_\_\_\_\_\_\_\_\_\_Set resolution to 1080p 30fps with Foxeer app  
Foxtech Seeker 30 max\_\_\_Stock/out of the box settings  
Waltter move 500\_\_\_\_\_\_\_\_Stock/out of the box settings  
Hawkeye Firefly split 4k\_\_\_Stock/out of the box settings  
Optris PI-Series\_\_\_\_\_\_\_\_\_Stock/out of the box settings \(via companion computer with MS Windows\)

\*\*\*\*\*\*\*\*\*\*\*\* Not Working \*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*

Workswell Wiris Mini  
Workswell Wiris and Wiris 2nd Generation  
Xiaomi Yi

## Herelink - Connection

#### [Flight mode turn off to maintain connection stability ](https://discuss.cubepilot.org/t/disconnection-bug/3845)

Airplane mode is designed for manually disconnect the air unit and controller. Connection breaks when you turn it on.

## Herelink - Antenna

#### [Herelink controller antenna plug](https://discuss.cubepilot.org/t/name-of-herelink-antenna-on-the-remote/3864/3)

Mini BNC

## Herelink - Calibration

[**Refer to - Herelink User Guides - Pairing, RC Calibration & Setup**](herelink-user-guides/one-time-setup.md)\*\*\*\*

## Herelink - Encryption

#### [Herelink encryption](https://discuss.cubepilot.org/t/support-for-encryption/1370)

Herelink encrypt over the air uses aes-128-ctr 

## Herelink - Ethernet

[**Herelink Ethernet**](https://discuss.cubepilot.org/t/herelink-ethernet/4369)   
  
****I’m trying to get ethernet passthrough working. I’m running on the Beta Channel, SRU01200616 on the ground unit and the corresponding version on the airside.

I understand an ethernet adapter with a R8152/8153 chip is required, I have an ANKER A7610011 and a Cable Matters 202023-BLK for testing. Both use the correct chip according to the Amazon comments, although it's very hard to get the information directly from the manufactures.

On the ground side, I have a generic OTG adapter and have tested it with a USB stick. On the airside I have an OTG charging passthrough cable, this allows to power the adapter \(and the airside, and cube, I’m not sure if that is a good idea\).

I understand with an adapter on both ends it should be a transparent link but I can't seem to get it working.

It does have to be said that I am a complete beginner with regard to networking stuff such as this.

**The next trick is getting ADB access to confirm \(GCS\)**  
  
Here is a new bootimage for the GCS unit to make the R8152/53 detect. [https://drive.google.com/file/d/1MGFAqC1zXrdnO2yEGhaigW-xktIx2cHj/view?usp=sharing 2](https://drive.google.com/file/d/1MGFAqC1zXrdnO2yEGhaigW-xktIx2cHj/view?usp=sharing) \(GCS unit bootimage with R8152\)  
the stock image includes  
AX8817X  
AX88179\_178A  
NET1080

to update the boot image via USB \(i assume you have ADB access already/developer mode\)

> adb reboot bootloader  
> fastboot flash boot boot.img  
> fastboot reboot

Next, we enable ADB via TCPIP, but first, we need to enable this via USB

> adb shell  
> setprop persist.adb.tcp.port 5555  
> reboot

then after the reboot, get the IP of the GCS unit \(eg 10.0.0.99\)

> adb connect 10.0.0.99  
> adb shell

you should get the shell again  
do a

> ifconfig

and check if eth0 exists

Now verify we can ADB into the air unit  
once you have ADB to the GCS unit, power on the air unit and do a

> adb shell \(gets you into the gcs unit\)  
> adb connect 192.168.0.10  
> adb -s 192.168.0.10:5555 shell

this should now get you into the air unit.

Next  
try running a

> /bin/busybox brctl show

under interfaces, you should see vxlan1 and eth0

> optimus:/ $ /bin/busybox brctl show  
> bridge name bridge id STP enabled interfaces  
> br-vxlan 8000.00e04c360345 no vxlan1  
> eth0

also, run

> ping 192.168.144.10  
> ping 192.168.144.11

these are the bridge endpoint IP’s

during testing, make sure the screen stays on there GCS unit, otherwise, power-saving features limit background data flow \(A most likely setting I have not found yet\)

I've just confirmed that this is working ok. one possible caveat. if your home network is using 192.168.0.x, things may not work.



#### 

#### 


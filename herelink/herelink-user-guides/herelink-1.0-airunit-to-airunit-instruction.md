---
description: AirUnit HDMI + GroundUnit Ethernet
---

# Herelink 1.0 AirUnit to AirUnit instruction

Device required:\
-Airunit x 2 (**\*firmware minimum 20211229 and above**)\
-Ethernet adapter\
-Installing a fan on both airunits to achieve better performance\
[https://docs.cubepilot.org/user-guides/herelink/herelink-faq#herelink-airunit-fan-installation](https://docs.cubepilot.org/user-guides/herelink/herelink-faq#herelink-airunit-fan-installation)\
\- usb otg+power cable if ethernet adapter doesn't include a method to power it

![](<../../.gitbook/assets/USB OTA+power cable.png>)

GroundUnit video out can be accessed via ethernet and MavLink is available as well. Compatible ethernet adapters are shown below:

AX88772 - Ground (not tested Airside)\
[PLUGABLE](https://plugable.com/products/usb2-otge100/) - directly connect to OTG. Nice for the ground side.

AX88179 - Ground and Air\
[UGREEN Ethernet Adapter for Chromecast](https://www.amazon.co.uk/UGREEN-Ethernet-Adaptor-Chromecast-Network/dp/B01N1X28F1/ref=asc_df_B01N1X28F1/?tag=googshopuk-21\&linkCode=df0\&hvadid=309964054975\&hvpos=\&hvnetw=g\&hvrand=13338390534555592071\&hvpone=\&hvptwo=\&hvqmt=\&hvdev=c\&hvdvcmdl=\&hvlocint=\&hvlocphy=9045387\&hvtargid=pla-303357944812\&psc=1) has an additional standard USB to power on airside, cables are quite long however.

R8152 / R8153 - Airside only\
[Cable Matters](https://www.amazon.co.uk/gp/product/B00ET4KHJ2/ref=ppx_yo_dt_b_asin_title_o04_s01?ie=UTF8\&psc=1)

[Anker USB 3.0](https://www.amazon.co.uk/gp/product/B00NPJP33M/ref=ppx_yo_dt_b_asin_title_o04_s00?ie=UTF8\&psc=1) - no blinky lights on the Ethernet port, maybe annoying for debugging

**Note：**\
**-Upgrade both units to the latest firmware before toggling the switches.**\
&#xNAN;**-Toggle switches both down position as default AirUnit function, firmware only can be upgraded when switches both at down position.**

## 1. GroundUnit and AirUnit Setup

### 1A GroundUnit setup

1. Upgrade AirUnits to the latest firmware.(Make sure toggle both switches at down position)
2. Power off the GroundUnit by disconnecting the power cable (7v-12v).
3. Remove the screws from the chassis.
4. Herelink AirUnit v1.0 (without ethernet port) Toggle the switches as shown below to activate GroundUnit. (1 up, 2 down) \
   **Note: For Herelink AirUnit v1.1 (with ethernet port) GroundUnit activated by toggle switch (1 down, 2up)**
5. Power on GroundUnit by reconnecting the power cable (7v-12v).

![](<../../.gitbook/assets/1A GoundUnit and AirUnit Setup.png>)

### **1B AirUnit setup**

Upgrade AirUnits to latest firmware.(Make sure toggle both switches down position)

## **2. Pairing**

Press and hold the pairing button for 3s on both AirUnit and GroundUnit within 30s&#x20;

\*Once pairing is completed LED will turn solid GREEN.

<div align="center"><img src="../../.gitbook/assets/AirUnit 1.0 Switches - 1 and 2.jpg" alt="1＝Pairing button
2＝Indicator Led"></div>

## 3. AirUnit HDMI functionality

Once AirUnit and GroundUnit are paired, connect the 1080p/720p video source to AirUnit.&#x20;

There are only 1 HDMI port available for communication between AirUnit and GroundUnit, it is marked #3 in the picture below.

![](<../../.gitbook/assets/3. AirUnit HDMI functionality.png>)

## 4. PC setup

1\. Please switch off PC’s WIFI

2\. Go to control panel > Network & Internet > Network connection

3\. Right click and choose properties

4\. Choose “internet (TCP/IPv4)”,then click properties

5\. Click “use the following IP address” and enter 192.168.144.3”

6\. Click “Subnet mask” and it will give you a Subnet mask.

![](<../../.gitbook/assets/4 PC setup.png>)

## 5. PC video setup

AirUnit video stream can be obtained through VLC, MissionPlanner or QGC

### 5A VLC setup

Go to Media > Open Steaming > Communication Protocol

Copy and paste : “rtsp://192.168.144.10:8554/H264Video”

Click “Play”.Click “Play”.

![](<../../.gitbook/assets/5A VLC setup.png>)

### 5B Mission Planner

**Video**

1. Right click the HUD
2. Select ‘Video’
3. Select ‘Set GStreamer Source’
4. Enter “rtspsrc location=rtsp://192.168.144.10:8554/H264Video latency=1 udp-reconnect=1 timeout=0 do-retransmission=false ! application/x-rtp ! decodebin3 ! queue max-size-buffers=1 leaky=2 ! videoconvert ! video/x-raw,format=BGRx ! appsink name=outsink”
5. Press OK

\
&#x20;**Mavlink**

1. Open Mission Planner
2. Set the port to 'UDPCL' (top right)
3. Click 'Connect'
4. Enter the IP 192.168.144.11
5. Enter port '14552'

### **5C QGC**

Setup(QGC icon at the top-left corner) > Application Settings > General > Fly View > Video Settings > Source > RTSP Video Stream

RTSP URL “rtsp://192.168.144.10:8554/H264Video”

Go back to the main screen and video input will come out.

![](<../../.gitbook/assets/5C QGC.png>)

## 6. VLC Video Latency Setup

\
VLC latency can be adjusted via below:

Media > Open Network Stream > Network > Click “Show more options” > adjust “caching” time

![](<../../.gitbook/assets/6. VLC Video Latency Setup-1.png>)

Tool > Preferences > Input / Codecs > Network > Default caching policy > select “Lowest latency”

![](<../../.gitbook/assets/6. VLC Video Latency Setup-2.png>)

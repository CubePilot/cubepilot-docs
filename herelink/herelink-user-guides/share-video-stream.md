# Share video Stream

## 1. Enable the video stream on Herelink

* Slide down the Notification Drawer and tap the Herelink Settings tab

![](../../.gitbook/assets/settings-app%20%281%29%20%281%29%20%281%29.jpg)

* Scroll down in Radio Settings and Enable the Video Sharing

![](../../.gitbook/assets/video-sharing.jpg)

{% hint style="info" %}
Please note that video stream isn't available until a GCS app enables it, so ensure atleast one GCS app is running in the background with correct stream selected.
{% endhint %}

## 2. Connect over Wifi Tethering

* Pull down the Notification Drawer and enable Hotspot.

![](../../.gitbook/assets/device-2020-02-14-143024.png)

* To configure press and hold hotspot logo, and you should see following screen.

![](../../.gitbook/assets/device-2020-02-14-143404.png)

* Then under Set up Wifi hotspot configure name and password for the hotspot.

![](../../.gitbook/assets/password%20%281%29.png)

* The video stream will be available at `rtsp://192.168.43.1:8554/fpv_stream`to connected devices.

## 3. Connect over USB tethering

* Press and hold the Hotspot button under notification logo.

![](../../.gitbook/assets/device-2020-02-14-143024.png)

* Under `Tethering & portable hotspot` find `USB tethering`, turn it on.

![](../../.gitbook/assets/device-2020-02-14-143404.png)

* The video stream will be available to connected devices over USB via `rtsp://192.168.42.129:8554/fpv_stream`

## 4. Connect via Wifi Connection

* If Herelink is connected over wifi, you can get video stream using IP of Herelink on the network.
* Press and hold Wifi option in Notification drawer and select settings.

![](../../.gitbook/assets/device-2020-02-14-144314.png)

* Scroll down to find the IP Address

![](../../.gitbook/assets/device-2020-02-14-144436.png)

* The video stream will be available to connected devices over USB via `rtsp://<ipaddress>:8554/fpv_stream`

## 3. Display the video stream

In this example we use VLC media player

* Open VLC and go to File &gt;&gt; Open network
* Type the url address provided on the HereLink stream menu and click "Open" 

![](../../.gitbook/assets/vlc-stream.png)

* The video stream window will automatically opens, if not, you can force it by clicking right on the video stream link &gt;&gt; Play

![](../../.gitbook/assets/vlc_2.png)


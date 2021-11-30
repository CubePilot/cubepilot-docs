# Share Video Stream

## Enable The Video Stream

Slide down the Notification Drawer and tap the HereLink Blue Settings tab

![](../../../../.gitbook/assets/91.png)

Scroll down in Radio Settings and Enable the Video Sharing

![](<../../../../.gitbook/assets/Screen Shot 2021-02-14 at 12.33.23 PM.png>)

## Connect Over Wifi Tethering

Pull down the Notification Drawer and enable Hotspot.

![](<../../../../.gitbook/assets/Screen Shot 2021-02-14 at 12.35.35 PM.png>)

To configure press and hold hotspot logo, and you should see following screen.

![](<../../../../.gitbook/assets/image (10).png>)

Then under Set up Wifi hotspot configure name and password for the hotspot.

![](<../../../../.gitbook/assets/image (12) (2).png>)

The video stream will be available at `rtsp://192.168.43.1:8554/fpv_stream`to connected devices.

## Connect Over USB Tethering

Press and hold the Hotspot button under notification logo.

![](<../../../../.gitbook/assets/Screen Shot 2021-02-14 at 12.35.35 PM (1).png>)

Under `Tethering & portable hotspot` find `USB tethering`, turn it on.

![](<../../../../.gitbook/assets/image (13).png>)

![](<../../../../.gitbook/assets/Screen Shot 2021-02-14 at 12.41.01 PM.png>)

The video stream will be available to connected devices over USB via `rtsp://192.168.42.129:8554/fpv_stream`

## Connect Over Wifi Connection

If the DataLink is connected over wifi, you can get video stream using IP of the HereLink Blue on the network.

Press and hold Wifi option in Notification drawer and select settings.

![](<../../../../.gitbook/assets/image (14).png>)

Scroll down to find the IP Address

![](<../../../../.gitbook/assets/image (15).png>)

The video stream will be available to connected devices over USB via `rtsp://<ipaddress>:8554/fpv_stream`

## Display The Video Stream

In this example we use VLC media player

Open VLC and go to File >> Open network

Type the url address provided on the HereLink Blue stream menu and click `Open`&#x20;

![](<../../../../.gitbook/assets/image (16).png>)

The video stream window will automatically opens, if not, you can force it by clicking right on the video stream link >> Play

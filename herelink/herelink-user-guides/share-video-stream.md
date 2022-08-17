# Video and Data Sharing

## 1. Switch between video stream

### **Solex dual video switch**

Click the icon in the red circle below to select Camera 1 and Camera 2, and click OK to switch.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 6.02.32 PM.jpg>)

### **QGroundControl dual video switch**

Click the icon in the red circle below to select Stream1 or Stream2 to switch video stream.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 6.04.30 PM.jpg>)

Stream 1 is HDMI 1 ,Stream 2 is HDMI 2.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 6.05.14 PM.jpg>)

## 2.Share Video Stream

**Enable video sharing on Herelink**

* From App Launcher slide down the notification drawer from the top,click “ herelink Settings”.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 10.31.19 AM.jpg>)

* Enable “Video Sharing”

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 10.31.50 AM.jpg>)

Note that the video stream is not available until the GCS application is enabled, so make sure that at least one GCS application is running in the background and that the correct video stream is selected.

### **Share with USB OTG**

Go to Settings > Developer Options > OPEN USB debugging, use USB to HDMI conversion cable (with power supply) connection to achieve wired screen projection, connect to use.

### **Connect over WIFI Hot spot**

* From App Launcher slide down the notification drawer from the top.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 10.33.19 AM.jpg>)

* Press and hold Wifi option in Notification drawer and select settings.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 10.34.36 AM.jpg>)

* Then under Set up Wifi hotspot configure name and password for the hotspot.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 10.36.19 AM.jpg>)

* The video stream will be available at rtsp://192.168.43.1:8554/fpv\_stream to connected devices.

> Can be played through a player that supports playing video streams

* Connect PC to HereLink hotspot，then open Mission planner. Normally , it will connect automatically after open GSC，if not ,please process following step.
* Set port to“UDP”.
* Click “Connect”
* Enter Local port “14550” .

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 10.37.09 AM.jpg>)

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 11.14.21 AM.jpg>)

* Right click on HUD screen to enter Video menu,choose HereLink Video then a IP input window will pop up.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 11.15.59 AM.jpg>)

* Enter 192.168.43.1 , then the video will be showed on HUD screen.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 11.17.15 AM.jpg>)

> First use of HereLink Video may require to download components

### Connect with QGroundControl

* Connect PC to HereLink hotspot, it will connect automatically after open QGC.
* Click Application Settings

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 11.18.35 AM.jpg>)

* In Video Settings changes Source to RTSP Video Stream and enter "RTSP URL" which mentioned above to get video stream.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 11.20.33 AM.jpg>)

### **Connect over USB tethering:**

* **Press and hold the Hotspot button under notification logo.**

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.39.58 PM.jpg>)

Press and hold the Hotspot button under notification logo, turn it on.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.40.13 PM (1).jpg>)

* The video stream will be available to connected devices over USB via `rtsp://192.168.42.129:8554/fpv_stream`

Connect with Mission Planner

* Connect PC to HereLink USB，then open Mission planner.
* Set port to“UDPCL”.
* Click "connect"
* Enter Herelink IP address ： 192.168.42.129
* Enter Local port “14552”.
* Click "connect"

Now，Mission Planner able to use mavlink telemetry data.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.42.02 PM.jpg>)

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.43.32 PM (1).jpg>)

* Right click on HUD screen to enter Video menu,choose HereLink Video then a IP input window will pop up.
* Enter 192.168.42.129 , then the video will be showed on HUD screen.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.46.34 PM.jpg>)

> First use of HereLink Video may require to download components

Connect with QGroundControl

* Connect PC and HereLink with USB cable.then it will connect automatically after open QGC.
* Click Application Settings

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.47.44 PM.jpg>)

* In Video Settings changes Source to RTSP Video Stream and enter "RTSP URL" which mentioned above to get video stream.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.55.27 PM.jpg>)

### **Connect via Wifi Connection：**

* Herelink can obtain video stream vis 5G wifi.
* From App Launcher slide down the notification drawer from the top. Press and hold Wifi option in Notification drawer and select settings.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.56.47 PM.jpg>)

* Slide down till find IP address.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.56.59 PM.jpg>)

* video stream sharing is : rtsp://<"enter herelink wifi ip adddress">:8554/fpv\_stream
* Connect with Mission Planner
* Connect the computer network to HereLink's LAN and open Mission planner.
* Set port to“UDPCL”.
* Click "connect"
* Enter the IP address obtained in the previous step
* Enter Local port “14552”.
* Click "connect"

Now，Mission Planner able to use mavlink telemetry data.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.58.27 PM (1).jpg>)

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 12.58.41 PM (2) (1).jpg>)

* Right click on HUD screen to enter Vedio menu,choose HereLink Video then a IP input window will pop up.
* Enter the IP address obtained in the previous step，then the vedio will be showed on HUD screen.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.03.54 PM.jpg>)

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.04.05 PM.jpg>)

> First use of HereLink Video may require to download components

Connect with QGroundControl

* Connect PC to HereLink Wifi will connect automatically after open QGC.
* Click Application Setting
* In Video Settings changes Source to RTSP Video Stream and enter "RTSP URL" which mentioned above to get video stream.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.07.23 PM.jpg>)

## 3.Play video stream

In this example, we use VLC player

* Open VLC player and click Media>>Open network stream
* Enter IP address provide by HereLink，Then click “Play”&#x20;

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.07.08 PM.jpg>)

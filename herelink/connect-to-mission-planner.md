# Connecting to Mission Planner

## Connecting to Mission Planner

{% hint style="info" %}
For enabling video stream in Herelink settings please refer [Share video Stream](share-video-stream.md)
{% endhint %}

## You are now connected to the Herelink HotSpot Wifi.

### **Mavlink**

* Open Mission Planner
* Set the port to 'UDP' \(top right\)
* Click 'Connect'
* Enter port '14550'

![](../.gitbook/assets/screen-udp-copie-min.jpg)

![](../.gitbook/assets/mission-planner-2.png)

## You are now connected to the same wifi network as the Herelink is.

Mavlink

* Open Mission Planner
* Set the port to 'UDPCL' \(top right\)
* Click 'Connect'
* Enter the IP of the herelink controler [Find your IP](https://ccm.net/faq/33725-how-to-check-your-android-ip-address)
* Enter port '14552'

You will now have mavlink working into Mission Planner

### To view live Herelink video in Mission Planner

**Note: Video requires Mission Planner 1.3.70 beta or above**

* Start Solex or QGC to ensure your video is working \(this is required to start the streaming process\)
* Right click the HUD
* Select 'Video' 
* Select 'Herelink Video'
* The first time you do this Mission Planner may need to download the files required to play the video. Your device will require and internet connection to be able to do this, you may need to disconnect from the Herelink hotspot to perform this step
* A popup window will open, enter the same IP as you did in the mavlink step and click OK

![](../.gitbook/assets/herelink-video.jpg)

![](../.gitbook/assets/herelink-video-ip.jpg)


# Connecting to Mission Planner

{% hint style="info" %}
For enabling video stream in Herelink settings please refer [Share video Stream](share-video-stream.md)
{% endhint %}

‌**You are now connected to the Herelink Wifi.**

### **Mavlink**

* Open Mission Planner
* Set the port to 'UDP' \(top right\)
* Click 'Connect'
* Enter the IP of the Herelink controller  [Find your IP](https://ccm.net/faq/33725-how-to-check-your-android-ip-address) 
* Enter port '14552'

![](../.gitbook/assets/screen-udp-copie-min.jpg)

![](../.gitbook/assets/mission-planner-2.png)

### To view live Herelink video in Mission Planner 

**Note: Video requires Mission Planner 1.3.70 beta or above**

* Right click on the HUD
*  Select 'Video' 
* Select 'Herelink Video'
* The first time you do this Mission Planner may need to download the files required to play the video. Your device will require and internet connection to be able to do this, you may need to disconnect from the Herelink hotspot to perform this step
* A popup window will open, enter the same IP as you did in the mavlink step and click OK

![](../.gitbook/assets/herelink-video.jpg)

![](../.gitbook/assets/herelink-video-ip.jpg)


# Connecting to Mission Planner

## M**avlink in Mission Planner**

Open Mission Planner

Set the port to `UDP` (top right)

Click `Connect`&#x20;

Enter the IP of the HereLink Blue controller

Enter port `14550`&#x20;

![](<../../../../.gitbook/assets/image (13).jpeg>)

![](<../../../../.gitbook/assets/image (19).png>)

You will now have Mavlink working into Mission Planner

_\*This configuration applies when we connect using USB TETHER or any other interface that is not WIFI. The Mavlink traffic being Broadcast from the WIFI Access Point by default, when connecting with USB or Ethernet, it is necessary to specify IP address of HereLink station so it can access the UDP port 14552._

## View DataLink Video in Mission Planner

**Note: Video requires Mission Planner 1.3.70 beta or above**

Start UR/Solex TX to ensure your video is working (this is required to start the streaming process)

Right click the HUD in Mission Planner

Select `Video`&#x20;

Select `HereLink Video`

The first time you do this, Mission Planner may need to download the files required to play the video. Your device will require an internet connection to be able to do this, you may need to disconnect from the DataLink hotspot to perform this step

A popup window will open, enter the same IP as you did in the mavlink step and click `OK`&#x20;

![](<../../../../.gitbook/assets/image (14).jpeg>)

![](<../../../../.gitbook/assets/image (15).jpeg>)


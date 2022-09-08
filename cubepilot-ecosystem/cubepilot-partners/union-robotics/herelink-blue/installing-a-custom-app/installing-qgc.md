# Installing QGC

## Installing SDK Platform-Tools

Ensure you have latest [platform-tools](https://developer.android.com/studio/releases/platform-tools) installed on your computer system.

If you do not have the SDK "platform-tools" installed on your computer, download it from this link and keep track where the the "platform-tools" folder is located:

{% embed url="https://developer.android.com/studio/releases/platform-tools" %}

## Connect the HereLink Blue to a computer

Enable "Developer Mode" on the HereLink Blue by navigating to `Settings`->`About Phone`->`Build Number` and tap at least 7 times on "Build Number."

![Swipe down on the screen and click the "gear" icon for settings](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.07.56 PM.png>)

![Click "About Phone" in the settings window ](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.09.10 PM (2) (1).png>)

![Click on the Build Number at least 7 times until the "Developer Mode" screen message is displayed](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.10.10 PM.png>)

Enable `Settings`->`Developer options`->`USB debugging`

![Click "Developer Options" in settings](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.11.47 PM.png>)

![Toggle USB debugging to "On"](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.13.17 PM.png>)

Using a USB to Micro USB cable, plug the DataLink into a computer and open the computer's terminal command line

![](../../../../../.gitbook/assets/herelink-computer.jpeg)

## Open the Terminal <a href="#open-the-terminal" id="open-the-terminal"></a>

For Windows, navigate to the "platform-tools" folder. In this folder, hold **down Shift and then right-click**. From the menu select the “**Open Command window here**” option. If the option to open the command window is not available, then click on the "open PowerShell window here".\


![Windows](<../../../../../.gitbook/assets/Click-on-the-“Open-PowerShell-window-here”-1024x731-1 (1).png>)

For Mac, navigate to the "platform-tools" folder. **Right Click** the folder and select  `Services`->`New Terminal at Folder`

![Mac](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.14.36 AM.png>)

## Check if the unit is connected

Using the computer's terminal, check it the device is connected via the adb command protocol:

Mac:

```
adb devices

```

![Mac](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.42.10 AM.png>)

Windows:

```
.\adb devices

```

![Windows](../../../../../.gitbook/assets/In-the-command-windowPowerShell-window-type-the-following-code.png)

## Download QGC APK

Click the link below to download the Android 64 bit QGC .apk to your computer:&#x20;

{% embed url="https://qgroundcontrol.s3-us-west-2.amazonaws.com/latest/QGroundControl64.apk" %}

Move the .apk file to the SDK "platform-tools" folder on your computer

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.19.47 AM.jpg>)

## Installing QGC to the DataLink

Install QGroundControl using `adb install QGroundControl64.apk` in your computers terminal

Mac:

```
adb install QGroundControl64.apk

```

![Mac adb install](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.17.43 AM.png>)

Windows:

```
.\adb install QGroundControl64.apk
```

![Windows .\adb install](../../../../../.gitbook/assets/Capture.png)

QGC should now appear in the app launcher's list.

![](../../../../../.gitbook/assets/110.png)

![](../../../../../.gitbook/assets/111.png)

# Installing a Custom App

## Installing SDK Platform-Tools

Ensure you have latest [platform-tools](https://developer.android.com/studio/releases/platform-tools) installed on your computer system.

If you do not have the SDK "platform-tools" installed on your computer, download it from this link and keep track where the the "platform-tools" folder is located:

{% embed url="https://developer.android.com/studio/releases/platform-tools" %}

## Connect the HereLink Blue to a computer

Enable "Developer Mode" on the DataLink by navigating to `Settings`->`About Phone`->`Build Number` and tap at least 7 times on "Build Number."

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.07.56 PM.png>)

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.09.10 PM.png>)

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.10.10 PM.png>)

Enable `Settings`->`Developer options`->`USB debugging`

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.11.47 PM.png>)

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-14 at 1.13.17 PM.png>)

Using a USB to Micro USB cable, plug the HereLink Blue into a computer and open the computer's terminal command line

![](../../../../../.gitbook/assets/herelink-computer.jpeg)

## Open the Terminal <a href="#open-the-terminal" id="open-the-terminal"></a>

For Windows, navigate to the "platform-tools" folder. In this folder, hold **down Shift and then right-click**. From the menu select the “**Open Command window here**” option. If the option to open the command window is not available, then click on the "open PowerShell window here".<br>

![](https://docs.union-robotics.com/~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MTS1Xx6Kx3fwJFjqpWk%2F-MUUbr0dnuRHkGpp73qV%2F-MUUkDY9A-6Upvid92Q7%2FClick-on-the-%E2%80%9COpen-PowerShell-window-here%E2%80%9D-1024x731-1.png?alt=media\&token=28273723-a0ed-48ce-9f01-9c486bfe446d)

For Mac, navigate to the "platform-tools" folder. **Right Click** the folder and select  `Services`->`New Terminal at Folder`

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.14.36 AM.png>)

## Check if the unit is connected

Using the computer's terminal, check it the device is connected via the adb command protocol:

Mac:

```
adb devices

```

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.42.10 AM.png>)

Windows:

```
.\adb devices

```

![](../../../../../.gitbook/assets/In-the-command-windowPowerShell-window-type-the-following-code.png)

## Installing .apk using adb

Move the .apk file to the SDK "platform-tools" folder on your computer

![](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.19.47 AM.jpg>)

##

Install the .apk using `adb install <app_name>.apk` in your computers terminal

Mac:

```
adb install <app_name>.apk

```

![Mac adb install](<../../../../../.gitbook/assets/Screen Shot 2021-02-26 at 11.17.43 AM.png>)

Windows:

```
.\adb install <app_name>.apk

```

![Windows .\adb install](../../../../../.gitbook/assets/Capture.png)

The new app should now appear in the app launcher's list.

![](../../../../../.gitbook/assets/110.png)

![](../../../../../.gitbook/assets/111.png)

## Uninstall an app using adb

To remove the app use `adb remove org.myorg.appname`

```
$ adb remove org.myorg.appname
Success
```

# System setting

### System setting

## 1. Language setting

Click the icon in the bottom right corner to enter the secondary menu

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.26.36 PM.jpg>)

Click "Settings" to enter system setting.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.27.07 PM.jpg>)

Enter "Settings" the slide down to "Languages & input "

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.27.57 PM.jpg>)

Click "Languages" to enter language setting.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.29.14 PM.jpg>)

Click **Add a Language** to Add more languages and scroll down to select the language you want

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.30.10 PM.jpg>)

After the addition, move the required language up through the icon on the right to set it as the system language

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.30.50 PM.jpg>)

## 2. Screen brightness adjustment

Controller screen brightness does not support automatic adjustment, you need to enter the Settings to adjust

Enter "Settings" ，slide down to "Display"

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.32.51 PM.jpg>)

Tun off Adaptive brightness，click Brightness level will show brightness window,drag to adjust brightness

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.34.47 PM.jpg>)

## 3. Network port setting

Before using network port device,you need to change its IP address to 192.168.144.X.(because Airunit and Controller occupy the address "192.168.144.10" and "192.168.144.11" ,so the IP address can not be changed to these 2 )

## 4. Install a custom application

**Make sure you have the latest platform tools installed**

https://developer.android.com/studio/releases/platform-tools

* Enable Developer Mode by tapping Settings->About Phone->Build Number multiple times.
* Enable Settings->Developer options->USB debugging
* Check if the unit is connected

`$ adb devices` `List of devices attached` `66c4bfea device`

* Install app using adb install \<app\_name>.apk

`$ adb install myapp.apk` `Performing Streamed Install` `Success`

* Your app should show up in the app launcher's list.

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.39.09 PM.jpg>)

* To remove the app do： `adb remove org.myorg.appname`

`$ adb remove org.myorg.appname` `Success`

####

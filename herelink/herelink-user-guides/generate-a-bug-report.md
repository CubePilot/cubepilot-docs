# Generate a bug report

**Install ADB and Google driver**

**Download SDK Platform Tools and Google USB Drivers：**

SDK Platform Tools ：[https://developer.android.com/studio/releases/platform-tools](https://developer.android.com/studio/releases/platform-tools)

Google USB Drivers ：[https://developer.android.com/studio/run/win-usb](https://developer.android.com/studio/run/win-usb)

#### **2. Set up the device for ADB：**

**Enable the Developper option on the Herelink device**

1.From the main screen, tap on the Android app menu to open it (bottom right of the screen).

![](<../../.gitbook/assets/Screenshot 2022-07-08 at 1.48.25 PM.jpg>)

1. Go to "Settings" > "About Phone" >> "Build Number"
2. Tap seven times on the "Build Number" case, it will activate the developper mode. A pop-up message will confirm that the device is now in developper mode.
3. Go back by tapping on the triangle (black colomn on the left) >> Go into "developer options" >> then activate " USB debugging"
4. The device is now ready to generate the bug report

**Generate the bug report**

1. Connect the Herelink remote to your computer with an USB cable.
2. Open the terminal of you computer then enter the command : `adb bugreport` > press enter The above command will generate the bureport and save zip file on the device, the path will be mentioned in the output of command (copy the path to use it in step 3)
3. Send the zip file to you computer by using the command : `adb pull <filepath_of_zip_file_on_the_device> <filepath_of_your_computer_desktop>`
4. Contact your reseller or CubePilot to send the bug report zip file. The bug report must be accompanied by detailed information on what happened: which application is causing the problem, the description of the issue, under which conditions, specific settings you made, video, photos, etc...., and all informations that could help staff to reproduce or understand the issue.

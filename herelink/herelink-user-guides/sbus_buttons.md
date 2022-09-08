# Configure Sbus Buttons & Wheel

Herelink is fitted with six programmable buttons and one hardware wheel. These can be configured to control sbus channel outputs from the Rover Unit's dual sbus connector and to send Mavlink commands to the autopilot via UR/Solex TX.

Autopilot mode selection must not be programmed to sbus channels. Mode selection should be configured to Mavlink commands within Solex or QGC to ensure predictable behavior in the event of signal loss or system reboot.

**Important Note:** Ardupilot sets Sbus channel 5 to flight mode selection as default, this should be disabled with Herelink by setting the parameter **FLTMODE\_CH:** to 0.

**Sbus Output：** The Herelink settings allows you to program buttons A,B,C,D,Cam & Wheel to control sbus outputs on the air unit. HereLink has dual independent sbus outputs on bus 1 and bus 2. Buttons can be configured on channels 5 - 16 on bus 1 and channels 1-16 on bus 2.

Channels 1-4 on Sbus 1 are reserved for RC control.

Each button can be programmed in one of 3 modes with long press and short press actions in Toggle and Multi modes.

### **Button Modes**

* Toggle (T) = Output latches between two pwm values with a short or long press option.
* Momenty (M)= Output changes to active value when pressed and held, returns to default when released.
* Multi = Sends command for channel to go to preset pwm value. Multi buttons can be stacked on both short and long press as well as multiple buttons configurations to allow channel outputs to range in values.

To select the mode either press T for Toggle, M for Momantry, when neither T or M is selected the button is in Multi mode

### **Sbus Button Configuration**

You can set Sbus button configuration in **Herelink Settings**>**button**

![](../../.gitbook/assets/Sbusbuttons\_1.png)

* Click NEW and type name for your new profile and press OK.

![](../../.gitbook/assets/Sbusbuttons\_Profile.png)

* Select the first button you want to configure from the drop down menu then click ADD .

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 1.24.23 PM.jpg>)

* Select desired button mode by tapping the letter, ie: Toggle, Maintain or leave blank for Multi

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 1.25.22 PM.jpg>)

* Tip: To move to the top end of the range you can scroll backwards, also ‘Flicking’ the numbers will scroll faster though the range.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 1.26.02 PM.jpg>)

* If setting a Multi mode button set desired active pwm output.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 1.27.24 PM.jpg>)

* Set sbus channel output and bus.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 1.28.33 PM.jpg>)

* Once configured you must click SAVE to store settings.
* Next continue to add more buttons via the above process.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 1.29.09 PM.jpg>)

* To remove a button config simply click the bin icon next to the name.

### **Multi Buttons**

* Multi button config allows you to set short and long press options as well as other buttons to set stages outputs on a sbus channel, below is an example of two buttons changing a channel to 4 different pwm values.
* When setting up Multi mode buttons at least one on each channel must be selected as default value, this sets the default output pwm the system will default to on power on.

![](<../../.gitbook/assets/Screenshot 2022-07-07 at 1.30.14 PM.jpg>)

**The Cube User Manual  V1.1**

[TOC]



# Preparation for The Cube



### Introduction

------

After the assembly of your unmanned vehicle, you may install The Cube as described in the following instructions.

The "flight controller" in the following content refers to The Cube.



### Mounting

------

Using the 3M double layer tape or screw from the package, mount The Cube as close as possible to the centre of gravity of your vehicle. Please ensure that the arrow on the flight controller is pointing to the front of your vehicle.

> According to the actual requirement, The Cube can also be mounted reversely or upside-down. This can be done by editing the parameter, referring to: [**Alternative orientations**](http://ardupilot.org/copter/docs/common-mounting-the-flight-controller.html?highlight=ahrs_orientation)
>

![Pixhawk2.1 Installation Guide_en_edited](../assets/Pixhawk2.1 Installation Guide_en_edited.svg)



If screw is needed for mounting, there are screws attached in the package. They are designed for 1.8mm boards. Length of customized M2.5 screws should be around 6 mm to 7.55 mm to fit The Cube. Please select the correct screw carefully according to the actual situation.

The Cube is not waterproof. Please apply external protection if the working environment is rainy or humid.



### Peripheral Connection

------

According to the type, size, dynamic structure, and load, installation of hardware and parameter setting can be diverse. However, the connection of electronic devices are similar. The following contents will guide you to connect your peripheral to Pixhawk2.1 (The Cube). Please follow these steps before your first flight.

> Remark: Please connect the GPS, sensors, telemetry, etc to The Cube according to the pinout. Information in [**The Cube Module Overview**]( https://docs.cubepilot.org/user-guides/autopilot/the-cube-module-overview ) described the pinout of the connectors. Please check the wiring order carefully because most of the peripheral malfunctioning are due to incorrect wiring. Since there are limitation on every interface on The Cube, please connect your high-power peripheral to external BEC.



Install SD Card

------

Dataflash logs are stored on microSD Card, which is plugged in the left of The Cube. MicroSD Card with Class 4 or higher is recommended. (SD card has been installed in factory)

> Remark: The Cube cannot arm the vehicle without SD card. A tone alarm with 1 high tune and 2 low tune will be played when trying to arm.



![](../assets/The Cube plug-in SD card.svg)



**Power Supply**

------

The Cube supports triple power source, which are power module, servo rail, and USB cable.

When more than 1 power source is connected, power will be drawn from the highest-priority source with a valid input voltage. When power source is below or over the limited, the system will stop drawing any power (no longer operable).

| Power Sources      | Priority | Regular Range | Limit          |
| ------------------ | -------- | ------------- | -------------- |
| Power Module Input | High     | 4.8 V - 5.4 V | 4.1 V - 5.7 V  |
| Servo Rail Input   | Medium   | 4.8 V - 5.4 V | 4.1 V - 10.5 V |
| USB Cable Input    | Low      | 4.8 V - 5.4 V | 4.1 V - 5.7 V  |

> Servo rail supports up to 10 V for manual override. If power module input is absent, servo rail will stop powering above 10.5V input. FMU and peripherals will NOT accept power from the servo rail.



**Power Module Connection**

------

Connect the power module to the `POWER1` port via POWER cable. If there are second battery monitor, please connect it to `POWER2` port. The Cube will be turned on immediately after battery is connected. Connect the XT60 on the other side of power module to the female connector for motor system and loads. Setup of the module can be found here: [Power Module Calibration](#Power Module Calibration)



![FMU Power Supply_en](../assets/FMU Power Supply_en.svg)



#### Connect ESCs and Motors

------

Connect the signal cables of the ESC or servo to the PWM signal output port according to the frame type.

> ESC malfunctioning are due to incorrect wiring in most of the case. Signal and ground should always be connected. Please check your ESC model to ensure that the +5 V cable is connected correctly. On APM2.x, ground pin of power supply can be used as APM feedback signal. For The Cube, signal pin and ground pin must be connected to operate the ESC.



**ESC Connection**

------

According to the order of motors and frame type, connect the 3 Pin signal cable from ESC to the corresponding port on `MAIN OUT`. The diagrams below show motor order for each frame type. The numbers indicate which output pin from the flight controller should be connected to each ESC. The propeller direction is shown in green (clockwise, CW) or blue (counter-clockwise, CCW). [More frames in ArduPilot](http://ardupilot.org/copter/docs/connect-escs-and-motors.html#connect-escs-and-motors).

<img src="../assets/quad_frames.png" alt="quad_frames"  />

 <img src="../assets/quad_and_tri_frames.png" alt="quad_and_tri_frames"  />

<img src="../assets/hex_and_y6_frames.png" alt="hex_and_y6_frames" style="zoom:;" />

<img src="../assets/y6_frames.png" alt="y6_frames"  />

<img src="../assets/oct_frames.png" alt="oct_frames" style="zoom:;" />

<img src="../assets/oct_quad_frames.png" alt="oct_quad_frames"  />

<img src="../assets/dodeca_frames.png" alt="dodeca_frames"  />



**Servo Connection**

------

The servo rail is not powered by the flight controller. Therefore an external BEC should be used if servo is needed.

Control channels for servos can be set in "Initial Setup > Mandatory Hardware > Servo Output" in Mission Planner.



**Sensors Connection**

------

The flight controller supports multiple sensor protocols including CAN, I2C, and ADC.

Parameter setting of specific sensor can be found here: [List of supported sensors in ArduPilot](http://ardupilot.org/copter/docs/common-optional-hardware.html)



**GPS Connection**

------

GPS module should be operated under good condition:

- Place the module on the outside of your vehicle (in an elevated position if appropriate) with a clear view of the sky, as far as possible from the motors and ESCs, with the arrow facing forward.
- Distance the module from DC power wiring and the batteries by at least 10cm. Use of a GPS mast is highly recommended.
- Twist power and ground wires where possible.

GPS working in outdoor environment with sufficient sky coverage can obtain better satellite signal, which significantly improve the safety for autonomous missions.

> Some high power wireless devices may interfere with compass and GPS signal. Please relocate those high power wireless devices as far as possible to GPS.



**GPS Modes**

------

**Single GPS**

Connect GPS to `GPS1` port with its 8-pin DF13 connector. Most of the GPS modules are plug-and-play. Some of the GPS module is equipped with compass and it may need calibration.

**GPS Blending (aka Dual GPS)**

Connection supports CAN mode and I2C mode.

Details will be mentioned in later session: **[Dual GPS Setting](# Optional Hardware)**



**R/C Wireless System Connection**

------

The Cube supports the following signal receivers. Different type of signals has their corresponding port on carrier board.



PWM/PPM/Futaba S.bus Receiver

------

- PWM Receiver: The Cube cannot directly process PWM signal. A PPM encoder is needed to encode multi-channel PWM to single-channel PPM signal. Then, connect it to `RCIN` port on The Cube.
- PPM RC Receiver / Futaba S.Bus Receiver can be directly plugged into the `RCIN` port.

> Some signal receivers can switch to different modes (eg: multi-channel PWM, single-channel S.Bus). Please refer to the user manual of the signal receiver to set it to S.Bus mode.



**Spektrum DSM/DSM2/DSM-X Satellite Receiver**

------

For a **Spektrum DSM**, **DSM2**, or **DSM-X Satellite** receiver, connect to the `SPKT` port on The Cube.



**Telemetry Connection**

------

The main purpose of wireless telemetry is for two-way communication between autopilot and ground control station, so that the real-time data can be displayed and UAV can be controlled by ground control station.

> Requirement of telemetry: mavlink protocol, passthrough protocol, or TTL serial interface.

Please ensure that the pin assignment of the cable matches the pinout of `TELEM1` on The Cube. Otherwise, please modify it.

After confirming, the telemetry can be connected to `TELEM1` or `TELEM2` port. Connect it by selecting the corresponding COM port and baud rate (typically 57600) in ground control station.

> Please be noticed the default baud rate of `TELEM1` port is 57600. This must match to the baud rate of telemetry.



## Setup Ground Control Station



The following session will tell how to select the appropriate ground control station for your setup and use it to setup and monitor your unmanned vehicle.



**Select the Appropriate Ground Control Station**

------



A ground station is typically a software application, running on a ground-based computer, that communicates with your UAV via wireless telemetry. It displays real-time data on the UAVs performance and position and can serve as a “virtual cockpit”, showing many of the same instruments that you would have if you were flying a real plane. A GCS can also be used to control a UAV in flight, uploading new mission commands and setting parameters. It is often also used to monitor the live video streams from a UAV’s cameras.

The mostly used and popular ground control station are Mission Planner and QGroundControl. For ArduPilot firmware, you may select Mission Planner. For PX4 firmware, QGroundControl is your first choice.

Different GCS can be selected according to your devices and working environment. They are usually compatible with different functions,such as obtaining real-time data, mission planning, device calibration, parameter setting, etc. Features and user interface are diverse among different GCSs.



### Install Firmware on The Cube

------



The Cube supports ArduPilot and PX4 firmware. Firmware can be uploaded from ground control stations. Upload procedures on both Mission Planner and QGroundControl will be mentioned.

If you are a developer, you may directly compile and upload the firmware to The Cube:

```
cd ardupilot                            
./waf configure --board CubeBlack           
./waf --targets bin/arducopter --upload  
```

The example above compiled arducopter firmware into The Cube Black. For other Cubes, board parameter in configuration should be CubeOrange, CubeYellow, CubeGreen, CubeBlue, or CubePurple.

[More details](http://ardupilot.org/dev/index.html)

> The example above compiled ArduCopter firmware into The Cube. Please refer [https://github.com/ArduPilot/ardupilot/blob/master/BUILD.md](https://github.com/ArduPilot/ardupilot/blob/master/BUILD.md) for more details.
>
> Remark: Hardware of The Cube is CubeBlack, so custom firmware should be compiled as CubeBlack as well.



### Mission Planner User Manual

------



**Download Mission Planner**

------

Before installing firmware to The Cube, please download latest version of Mission Planner from ArduPilot website. Download [Mission Planner](http://firmware.ardupilot.org/Tools/MissionPlanner/) according to your need.

- Using Windows 10 as example, download the `.msi` installation file and run it as administrator. During the installation process, some drivers will be installed together. Click "yes" if any dialog box pop up.



**Download QGroundControl**

------

For the user manual, please refer to [QGroundControl User Manual](https://docs.qgroundcontrol.com/en/)

Download link: [stable](https://docs.qgroundcontrol.com/en/getting_started/download_and_install.html)、[beta](https://docs.qgroundcontrol.com/en/releases/daily_builds.html) 

> **Remark: **It is recommended to download the stable version. Beta version is recommended for loading firmware only.



**Loading Firmware to The Cube**

------

The Cube has **no firmware** by default in factory setting. Before loading firmware, select the COM port drop-down on the upper-right corner of the screen (near the "Connect" button). Select "AUTO" or the specific port for your board. Set the Baud rate to `115200` as shown. Don’t hit "Connect " yet.

If there is no internet connection, you may upload firmware by click "load custom firmware". [Download link of firmware for copter](http://firmware.ardupilot.org/Copter/stable/CubeBlack/arducopter.apj)

![28](../assets/cube_user_manual_28.png)

Once entering the Install Firmware page under Initial Setup, ground control station will look for new firmware **on internet**. Wait for the system obtain the list of firmware. After the version number of firmware, check the corresponding frame type and follow the instruction and messages to install firmware.

![1](../assets/cube_user_manual_1.png)

After firmware download, the following message will appear. Disconnect the USB and click "OK".

After reconnecting the USB, loading bar at the bottom should start running and firmware loading should start.

![2](../assets/cube_user_manual_2.png)

When the following message appeared and the musical tone rang, firmware install has been completed. You may still try to connect even if the musical tone did not ring. If connection is successful, the firmware has been installed successfully.

After connection, please confirm the firmware version matches the desired version.

![4](../assets/cube_user_manual_4.png)



**Connect Mission Planner to The Cube**

------

To establish a connection you must first choose the communication method/channel you want to use, and then set up the physical hardware and Windows device drivers. You can connect the PC and autopilot using USB cables, Telemetry Radios, Bluetooth, IP connections etc.

- Using USB Cable: Connect the USB cable to the USB port at the left or The Cube. Use a direct USB port on your computer (not a USB hub). Select the corresponding COM port from the dropdown list at the top-right corner in Mission Planner. Then select the baud rate as `115200`。
- Using Telemetry: For USB telemetry, select the corresponding COM port and set baud rate as `57600`. For WIFI or Bluetooth telemetry, select the corresponding device from the device list and input the IP address of telemetry. Please refer to the user manual of your telemetry for more details on parameter setting.

 

#### Basic Hardware Calibration and Parameter Setting

------



##### Frame Class and Type Configuration

------

------

> Connect to Mission Planner. On the "Initial Setup > Mandatory Hardware > Frame Type" screen select the frame type of your vehicle such as Plus frame or X frame.



![15](../assets/cube_user_manual_15.png)

##### Accelerometer Calibration

------

> For more details on minimize magnetic interference and improve compass performance, please refer to [ArduPilot offical website](http://ardupilot.org/copter/docs/common-magnetic-interference.html#common-magnetic-interference).

Calibration steps

Go to "Initial Setup > Mandatory Hardware > Accel Calibration". Click **Calibrate Accel** to start the calibration. Pointing the nose of your vehicle to LEVEL, LEFT, RIGHT, NOSEDOWN, NOSEUP, and BACK according to the message below. "Calibration successful" will be shown after calibration completed successfully.

1. Place the vehicle LEVEL then press "Click when Done".

![16](../assets/cube_user_manual_16.png)

![Level](../assets/cube_user_manual_level.png)

2. Place the vehicle nose to front and left-hand-side to the ground then press "Click when Done".

![17](../assets/cube_user_manual_17.png)

![Left](../assets/cube_user_manual_left.png)

3. Place the vehicle nose to front and right-hand-side to the ground then press "Click when Done".

![18](../assets/cube_user_manual_18.png)

![Right](../assets/cube_user_manual_right.png)

4. Place the vehicle nose to the ground then press "Click when Done".

![19](../assets/cube_user_manual_19.png)

![Nosedown](../assets/cube_user_manual_nosedown.png)

5. Place the vehicle nose to upward then press "Click when Done".

![21](../assets/cube_user_manual_21.png)

![Noseup](../assets/cube_user_manual_noseup.png)

6. Place the vehicle upside-down then press "Click when Done".

![22](../assets/cube_user_manual_22.png)

![Back](../assets/cube_user_manual_back.png)

"Calibration successful" will be shown after calibration completed successfully.

![23](../assets/cube_user_manual_23.png)

> Level Calibration

Place the vehicle horizontally and click "Calibrate Level". The text in button will become "Completed" after calibration successful.

![24](../assets/cube_user_manual_24.png)

##### Compass Calibration

------

Ensure the compass has been enabled.

1. Select "Enable Compasses" and "Compass1"

2. Select all 3 compass (only 2 if no external GPS module is connect). Select "External mounted" for Compass #1 if there is an external GPS module connected. Otherwise, all 2 compasses are internal compass inside The Cube.
3. Click "Start" to calibrate compasses. hold the vehicle in the air and rotate it so that each side (front, back, left, right, top and bottom) points down towards the earth for a few seconds in turn. As the vehicle is rotated the green bars should extend further and further to the right until the calibration completes.

![6](../assets/cube_user_manual_6.png)

The window below will show success. For 3 compasses, "success" will be shown 3 times.

![7](../assets/cube_user_manual_7.png)

upon successful completion three rising tones will be emitted and a “Please reboot the autopilot” window will appear and you will need to reboot the autopilot before it is possible to arm the vehicle.

![8](../assets/cube_user_manual_8.png)

If, after multiple attempts, you are unable to calibrate the compass, Press the “Cancel” button and change the “Fitness” drop-down to a more relaxed setting and try again.

![9](../assets/cube_user_manual_9.png)

##### Radio Control Calibration

------

> Radio Control Calibration

Connect the RC receiver to The Cube via `RCIN` and turn on your RC transmitter.

Open the "INITIAL SETUP > Mandatory Hardware > Radio Calibration" screen. If your RC receiver (Rx) and transmitter (Tx) are bound, you should see the green bars move when you move the transmitter sticks.

Toggle the switches to move the red line of every channels to their upper limit and lower limit. After the completion of calibrating red line of all channels, click the button to finish.

If the green bars do not move as you move the sticks, verify that the transmitter is bound to the receiver (the receiver displays a solid green light) and that it is set to use the correct model for your vehicle.

Error message may appear after RC calibration: rc(x)_mini\max xxx. Please modify the parameter `rc(x) _trim` to 1500.

![13](../assets/cube_user_manual_13.png)

![14](../assets/cube_user_manual_14.png)



##### Electronic Speed Controller (ESC) Calibration

------



> **Safety Check!**
>
> Before calibrating ESCs, please ensure that your copter has NO PROPS on it and that The Cube is NOT CONNECTED to your computer via USB and the Lipo battery is disconnected.

![ESC_Cal](../assets/ESC_Cal.png)

**All at once calibration Method 1:**

1. Turn on your transmitter and put the throttle stick at maximum.

![1_TurnOnRC_MaxThrottle](../assets/TurnOnRC_MaxThrottle.png)

2. Connect the Lipo battery. The autopilot’s red, blue and yellow LEDs will light up in a cyclical pattern. This means the it’s ready to go into ESC calibration mode the next time you plug it in.

![2_ConnectBattery_FCU_RedBlueYellow_Loop](../assets/ConnectBattery_FCU_RedBlueYellow_Loop.png)

3. With the transmitter throttle stick still high, disconnect and reconnect the battery.

![3_HoldMaxThrottle_Reboot](../assets/HoldMaxThrottle_Reboot.png)

4. Press and hold the safety button until it displays solid red.

5. The autopilot is now in ESC calibration mode. You may notice the green, red ,and blue LEDs blinking alternatively on and off.

6. Wait for your ESCs to emit the musical tone, the regular number of beeps indicating your battery’s cell count (i.e. 3 for 3S, 4 for 4S) and then an additional two beeps to indicate that the maximum throttle has been captured.

7. Pull the transmitter’s throttle stick down to its minimum position.

![HoldSwitch_LongBeep_MinThrottle](../assets/HoldSwitch_LongBeep_MinThrottle.png)

8. The ESCs should then emit a long tone indicating that the minimum throttle has been captured and the calibration is complete.

9. If the long tone indicating successful calibration was heard, the ESCs are “live” now and if you raise the throttle a bit they should spin. Test that the motors spin by raising the throttle a bit and then lowering it again.

10. Set the throttle to minimum and disconnect the battery to exit ESC-calibration mode.
11. Verify the direction and speed of motors after calibration complete.

**All at once calibration Method 2:**

1. Connect the flight controller. Go to "Config/Tuning > Full Parameter List" screen and modify the parameter `ESC_CALIBRATION` to 3 /"Start-up and automatically calibrate ESCs".

2. Disconnect and reconnect the battery.

![3_HoldMaxThrottle_Reboot](../assets/HoldMaxThrottle_Reboot.png)

3. The autopilot is now in ESC calibration mode. You may notice the green, red ,and blue LEDs blinking alternatively on and off.

4. Press the safety button until it goes solid red. Wait for the flight control conduct auto calibration.

5. Verify the direction and speed of motors after calibration complete.

##### Flight Modes

------

**Flight modes configuration**

The flight mode channel is the input radio channel that ArduPilot monitors for mode changes. On Copter this is always channel 5 (can be changed in parameter `FLTMODE-CH`).

Toggle the corresponding button to the desired position. As you move your transmitter’s flight mode switch the green highlight bar will move to a different position. When finished press the `Save Modes` button.

> You can enable up to 6 autopilot control/flight modes to be set from your RC transmitter.
>
> **Remark:** Verify the flight modes before taking off. Switching to an incorrect mode during the flight may crash the vehicle. 

![11](../assets/cube_user_manual_11.png)

![10](../assets/cube_user_manual_10.png)

1. Stabilize ([Stabilize Mode](http://ardupilot.org/copter/docs/stabilize-mode.html)) 

   Stabilize mode allows you to fly your vehicle manually, but self-levels the roll and pitch axis. Takeoff and landing should be operated under this mode. If you’re learning to fly, try Alt Hold or Loiter instead of Stabilize. You’ll have fewer crashes if you don’t need to concentrate on too many controls at once. Stabilize mode is also the optimal mode for FPV flight.

   Make sure you have assigned a button which can easily switch to Stabilize mode. This is critical for taking back the control during emergency scenario!

2. AltHold（[Altitude Hold Mode](http://ardupilot.org/copter/docs/altholdmode.html) )

   You may try this mode after your first flight. GPS is not required in this mode. The flight controller uses a barometer which measures air pressure as the primary means for determining altitude. 

   When altitude hold mode (aka AltHold) is selected, the throttle is automatically controlled to maintain the current altitude.

   Position is not controlled under this mode, therefore it may drift. You may use the controller to move or hold the position.
   
   AC3.1 and later allow arming and disarming in altitude hold mode. When disarming, the copter may need to rest in the landing position for a few seconds to allow the “landing checker” to verify that the copter has landed before you are able to disarm.

   When switching into AltHold from a manual flight mode (like Stabilize) on a copter, make sure the throttle stick in the mid position. Otherwise, the copter may suddenly descend or climb.

3. Loiter（[Loiter Mode](http://ardupilot.org/copter/docs/loiter-mode.html))

   Loiter Mode automatically attempts to maintain the current location, heading and altitude. The vehicle can be armed in Loiter mode but only once the GPS has 3D lock and the HDOP has dropped below 2.0. Confirm your GPS is operating in good condition to minimize the chance of GPS Glitch during the flight. This mode is basically similar to AltHold mode.

4. Simple Mode（[Simple Mode](http://ardupilot.org/copter/docs/simpleandsuper-simple-modes.html))

   Simple mode allow the pilot to control the movement of the copter from the pilot’s point of view regardless of which way the copter is facing. This is useful for new pilots who have not mastered adjusting their roll and pitch inputs depending upon which way the vehicle is facing and for cases when the copter is far enough away that it’s heading is not apparent.

5. RTL ([RTL Mode](http://ardupilot.org/copter/docs/rtl-mode.html))

   RTL mode requires a reliable position estimate to work properly, most commonly provided by GPS and compass. 

   If you get GPS lock and then ARM your copter, the home position is the location the copter was in when it was armed. This means if you execute an RTL in Copter, it will return to the location where it was armed.

   If you get GPS no fix before ARMing, the first GPS lock position in the air will be the home position.

   When RTL mode is selected, the copter will return to the home location. The copter will first rise to RTL_ALT (default 15m) before returning home or maintain the current altitude if the current altitude is higher than RTL_ALT. 

   You may also adjust parameters to set automatically landing, and loitering timeout before landing.

6. Circle ([Circle Mode](http://ardupilot.org/copter/docs/circle-mode.html) )

   Circle will orbit a point located CIRCLE_RADIUS centimeters in front of the vehicle with the nose of the vehicle pointed at the center. The pilot can control the yaw of the copter, the autopilot will not retake control of the yaw until circle mode is re-engaged.

   The pilot does not have any control over the roll and pitch but can change the altitude with the throttle stick as in AltHold or Loiter mode. The copter cannot land in this mode. 

   - The speed of the vehicle (in deg/second) can be modified by changing the `CIRCLE_RATE` parameter. Positive value refer to Clockwise, vice versa. If the acceleration speed exceeded value defined in `WPNAV_ACCEL`, the vehicle may not be able to reach its maximum speed.
   - Circling will not stop until another mode is selected
   - Centre of circle is defined by GPS coordination and cannot be changed

7.  Guided（[Guided Mode](http://ardupilot.org/copter/docs/ac2_guidedmode.html#ac2-guidedmode)) 

   This mode requires communication between Ground Control Station (such as Mission Planner) and flight controller. In the Mission Planner Flight Data screen map, try right-clicking on a nearby spot and select “Fly to Here”. You will be asked for a guided mode altitude. Enter an above home altitude in meters.

8. Follow Me ([Follow Me Mode](http://ardupilot.org/copter/docs/ac2_followme.html#ac2-followme))

   You will need a laptop (or a phone/tablet) with an integrated GPS available to the GCS. Once the flight controller is connected to the GCS, the GCS will read the GPS data from your device and send it to your Copter as “fly to here” commands every two seconds. Such that the vehicle will follow the pilot when he is walking around.

   This mode may requires additional device.

9. Auto（[Auto Mode](http://ardupilot.org/copter/docs/auto-mode.html))

   In Auto mode the copter will follow a pre-programmed mission script stored in the Mission Planner, which is made up of navigation commands (i.e. waypoints) and “do” commands (i.e. commands that do not affect the location of the copter including triggering a camera shutter). 

   An independent chapter will further explain this mode.

10.  PosHold ([Poshold Mode](http://ardupilot.org/copter/docs/poshold-mode.html))

    Poshold Mode is the combination of GPS loitering mode and AltHold mode. GPS lock should be done before takeoff, to avoid GPS glitch during the flight. The control and reaction is similar to AltHold mode: When the pilot releases the sticks the copter will lean back to bring the vehicle to a stop. When no control input, it performs same with Loiter mode. 
    
    The maximum brake-angle can be set with the `PHLD_BRAKE_ANGLE` parameter (i.e. 3000 = the vehicle will lean back up to 30degrees)
    
    The speed the vehicle rotates back to the maximum angle can be set with the `PHLD_BRAKE_RATE` parameter (i.e. 8 = rotates back at 8 degrees per second)

11. Land ([LAND Mode](http://ardupilot.org/copter/docs/land-mode.html))

    LAND Mode attempts to bring the copter straight down. The flight controller uses barometer for determining altitude. If the vehicle has GPS lock the landing controller will attempt to control it’s horizontal position but the pilot can adjust the target horizontal position just as in Loiter mode.

12. Acro（ [Acro Mode](http://ardupilot.org/copter/docs/acro-mode.html))

    Acro mode (Rate mode) uses the RC sticks to control the angular velocity of the copter. The throttle is completely manual with no compensation for tilt angle of the vehicle. Not recommended for new pilots.

    Parameter `ACRO_TRAINER` can be modified to:

     0 = disabled. This means the pilot operates in full Rate control with no automatic leveling nor angle-limiting performed by the autopilot. 
     1 = automatic leveling. The vehicle will automatically return to the level when the pilot releases the sticks. The aggressiveness with which it returns to level can be controlled with the `ACRO_BAL_ROLL` and `ACRO_BAL_PITCH` parameters. The default of 1.0 will cause it to return to level at up to 30deg/sec. Higher values will make it return more quickly. 
     2 (Default) = automatic leveling and lean angle limited. Includes the automatic leveling as option #1 but in addition the vehicle will not lean more than 45 degrees (this angle can be configured with the `ANGLE_MAX` parameter). 

13. Drift（[Drift Mode](http://ardupilot.org/copter/docs/drift-mode.html))

    Drift Mode allows the user to fly a multi-copter as if it were a plane with built in automatic coordinated turns. 
    The user has direct control of Yaw and Pitch, but Roll is controlled by the autopilot. This allows the copter to be controlled very intuitively with a single control stick if using a Mode 2 transmitter 
    The user has completely manual control over the throttle as in Stabilize mode. 

14. Flip ([Flip Mode](http://ardupilot.org/copter/docs/flip-mode.html))

    Vehicle will flip on its roll or pitch axis depending upon the pilot’s roll and pitch stick position. Vehicle will rise for 1 second and then rapidly flip. The vehicle will not flip again until the switch is brought low and back to high. Give yourself at least 10m of altitude before trying flip for the first time! 
    
    Not recommended for new pilots.
    
15. ZigZag（[ZigZag Mode](http://ardupilot.org/copter/docs/zigzag-mode.html))

    ZigZag mode is a semi-autonomous mode designed to make it easier for a pilot to fly a vehicle back and forth across a field which can be useful for crop spraying 

    See also: [**More Flight Modes**](http://ardupilot.org/copter/docs/flight-modes.html)

    

##### Power Module Calibration

------

The power module inside The Cube package supports up to 8S voltage, 30 A continuous current and 100 A burst current. If higher load is needed, please replace it for another power module with higher current limit.



**Connecting the Power Module**

Connect the XT60 male connector to the battery (female on the other side for motors or ESC) and JST connector to the `POWER1` port on The Cube. 

Dual input redundant power is also supported. You may connect the second battery to `POWER2` to monitor  2 batteries at the same time.



**Battery Monitor Calibration**

Connect The Cube to power module and turn it on. Connect The Cube to Mission Planner via telemetry or USB cable. Battery measurement is primarily set up in the "Initial Setup > Optional Hardware > Battery Monitor" screen. 

Enter the properties your module can measure, the type of module, the type of flight controller, and the battery capacity:

![25](../assets/cube_user_manual_25.png)

> Monitor `Analog Voltage and Current`; Current monitor is currently not supported
>
> Sensor `0.Other`;
>
> APM Ver `4.The Cube or Pixhawk`.



Default parameter may return inaccurate voltage. Edit `Voltage divider` according to the following formula to fix it.



 <center>**Voltage Divider Value * Actual Battery Voltage / Voltage Measured by Power Module = Correct Voltage Divider Value**</center>
Enter the new Voltage Divider according to your calculation and reboot the flight controller. Measured voltage should be accurate now.



**Battery Monitor 2 Calibration **

Battery Monitor 2 corresponds to `POWER2` port. Set the monitor ,sensor, and APM ver value as shown below. Voltage divider value shall be modified with the same formula as Battery Monitor 1 do.

Settings:

![26](../assets/cube_user_manual_26.png)

> Monitor  `Analog Voltage Only`;
>
> Volt Pin `Pixhawk/Pixracer/Navio2`；
>
> Current Pin `Pixhawk/Pixracer/Navio2`.



**Display Battery Monitor 2 Voltage on HUD**

On the HUD right click and select "User Items" will open the "Display this" window. Select `battery-voltage2` and modify the display header. Battery Monitor 2 Voltage will be displayed on the HUD after clicking "OK".

![27](../assets/cube_user_manual_27.png)

##### Motor Test

------

![43](../assets/cube_user_manual_43.png)

**Ensure that the propellers are removed from motors**

Connect the flight controller to ground control station. The English characters order correspond to the connector motors, as shown in the following diagrams. Using quadcopter as example, clicking `Test motor A`, B, C, and D will activate motor A, B, C, and D respectively. The activated motor will rotate for 2 seconds. If the motor did not rotate, rise `Throttle %` to 10% and retry. If it still did not work, try to rise it to 15% or higher.

<img src="../assets/cube_user_manual_42.png" alt="cube_user_manual_42"  />



### Preparations before takeoff

------



**Pre-Arm Safety Check**

------

The autopilot includes a suite of Pre-arm Safety Checks which will prevent the vehicle from arming if any of a fairly large number of issues are discovered before take-off including missed calibration, configuration or bad sensor data. These checks help prevent crashes and fly-aways but they can also be disabled if necessary.

> In normal situation LED will blink blue or green. The LED will be flashing yellow if the flight controller notice a pre-arm check failure.

- If it is blinking yellow, please try to disarm. The failure messages will be shown in the HUD window. Solve the error according to the failure message shown.

  Detailed failure messages and solutions can be found on the Ardupilot official website: http://ardupilot.org/copter/docs/prearm_safety_check.html

- If it is blinking blue or green, you may disarm. A low pitch tone will be emited from the buzzer. You will see the motors start to rotate and ready to take off.

**LED Meanings:**

> Flashing red and blue: Initializing sensors. Place the vehicle still and level while it initializes the sensors.
>
> Flashing blue: Disarmed, no GPS lock. Auto-mission, loiter and return-to-launch flight modes require GPS lock
>
> Solid blue: Armed with no GPS lock
>
> Flashing green: Disarmed (ready to arm), GPS lock acquired. Quick double tone when disarming from the armed state.
>
> Fast Flashing green: Same as above but GPS is using SBAS (so should have better position estimate)
>
> Solid green: with single long tone at time of arming: Armed, GPS lock acquired. Ready to fly!
>
> Double flashing yellow: Failing pre-arm checks (system refuses to arm)
>
> Single Flashing yellow: Radio failsafe activated
>
> Flashing yellow - with quick beeping tone: Battery failsafe activated
>
> Flashing yellow and blue- with high-high-high-low tone sequence (dah-dah-dah-doh): GPS glitch or GPS failsafe activated
>
> Flashing red and yellow: EKF or Inertial Nav failure
>
> Flashing purple and yellow: Barometer glitch
>
> Solid Red: Error，usually due to the SD card（re-plug or place the SD card to solve）,MTD or IMU，you may check the SD card and have a look at BOOT.txt for boot message analysis
>
> Solid red with SOS tone sequence: SD card missing or SD card bad format
>
> No light when power on: No firmware，firmware lost，SD card missing or bad format（ac3.4 or higher version）

**Arming**

------

The flight controller can be armed by GCS or remote controller.

> - By controller: holding the throttle down, and rudder right for 3 seconds. Do not hold the rudder right for too long (>15 seconds) or you will begin the AutoTrim feature
> - By GCS: Connect the flight controller to GCS. There should be a "Action" tab under the HUD. Click the button `Arm / Disarm` to arm the vehicle.

**Tips For New Pilots**

------

> Note: UAV is not a toy and it may cause injuries. Make sure there is no people or obstacles 50m around.

It is recommended to use Stabilize mode in your first flight. The throttle in Stabilize mode is linear so that the sensitivity is relatively low.

After flying in Stabilize mode for a while, keep altitude above 1m. Assuming that all is fine so far, you’re ready for more advanced modes. Switch to AltHold, Loiter, and other modes to practise them. The control logic of AltHold, Loiter are different from Stabilize. Releasing the throttle stick will keep the vehicle at the current altitude. Climb when pushing up and descend when pushing down.

> Note: Please read and understand the characteristic of flight modes before actually using it.



### Common Problems

------

**Flipped and crashed right after takeoff:**

|            Possible Problem            |                           Solution                           |
| :------------------------------------: | :----------------------------------------------------------: |
|        Incorrect frame selected        | Go to "Initial Setup > Mandatory Hardware > Frame Type" and select the correct frame type. |
|          Incorrect ESC order           | [Connect ESC in correct order](#Connect ESCs and Motors) and verify with [Motor Test](#Motor Test) |
|       Incorrect motor direction        | Verify by arming the vehicle or using [Motor Test](#Motor Test) |
|     Incorrect propeller direction      | Verify whether air is pushing down when propellers are rotating |
| Inconsistent accelerometer calibration |   [Accelerometer Calibration](#Accelerometer Calibration)    |
|     ESC and throttle inconsistent      |                   Calibrate throttle range                   |

**Motors are rotating but cannot takeoff:**

Verify whether there is enough power. Check if motor parameters are appropriate to propeller size and battery.

**Motors do not rotate after arming:**

Verify whether ESC signal cables are correctly connected. **Remove the propellers** and conduct motor test. If the motors rotate, calibrate throttle range.

**Motors keep beeping**

Verify whether throttle range has finished.

**Commanding fly forward but copter flew backward; commanding fly to left but copter flew to right:**
The control channel of controller is flipped. Modify the controller in its configuration menu to reverse the channels back to normal.

In the full parameter list in ground control station, modify the `REVERSED` parameter for specific RC channel. `0` for default and `1` for reversed. Write param after finished.

**No RC signal received:**

Verify the signal cable is correctly connected. Verify whether the RC receiver is connected. Verify whether the RC receiver output is normal, and whether it is PPM or SBUS protocol.

**No telemetry connection:**

Verify the wiring order of the telemetry. Check if the the baud rate is correctly selected.

### Failsafe Mechanism

------

**Battery/Radio Failsafe**

![41](../assets/cube_user_manual_41.png)

Once entered failsafe mode, it will **not** automatically return to the flight mode that was active before the failsafe was triggered. If the pilot wished to re-take control, he/she would need to manually toggle the flight mode switch to another position. 

> **The yellow box indicates Battery failsafe**

Low Battery:

Using 3S battery as example, set it to 10.5V which is 3.5 * 3. You may also set the specific voltage according to your battery.

Reserved MAH:

Set to 0, which disable the capacity based trigger.

Failsafe action:

Land - the vehicle will switch to [Land](http://ardupilot.org/copter/docs/land-mode.html#land-mode) mode.

RTL - the vehicle will switch to [Return-to-Launch](http://ardupilot.org/copter/docs/rtl-mode.html#rtl-mode) mode if possible but if not possible (because of no good position estimate) the vehicle will [Land](http://ardupilot.org/copter/docs/land-mode.html#land-mode).

SmartRTL or RTL - the vehicle will switch to [SmartRTL](http://ardupilot.org/copter/docs/smartrtl-mode.html#smartrtl-mode) mode if possible, if not possible (because SmartRTL’s position buffer is full) the vehicle will switch to [RTL](http://ardupilot.org/copter/docs/rtl-mode.html#rtl-mode). If RTL is also not possible (because of no good position estimate) the vehicle will switch to [Land](http://ardupilot.org/copter/docs/land-mode.html#land-mode).

SmartRTL or Land - the vehicle will switch to [SmartRTL](http://ardupilot.org/copter/docs/smartrtl-mode.html#smartrtl-mode) mode if possible, if not possible (because SmartRTL’s position buffer is full) the vehicle will switch to [Land](http://ardupilot.org/copter/docs/land-mode.html#land-mode).

Terminate - the vehicle will disarm the motors. This is a dangerous option that should not be used in most cases.

> **The red box indicates radio failsafe**

Failsafe action:

Enabled Always RTL - switch the copter to RTL Mode. If the GPS position is not usable, the copter will change to Land Mode instead. 

Enabled Continue with Mission in Auto Mode -  ignore the failsafe in an Auto Mode mission. Otherwise, it will behave the same as *Enabled Always RTL*. This option no longer exists in ArduCopter 4.0. Instead, see the [FS_OPTIONS](http://ardupilot.org/copter/docs/parameters.html#fs-options) parameter for this function.

Enabled always Land - switch the copter to Land Mode. 

Enabled always SmartRTL or RTL -  switch the copter to SmartRTL mode. If SmartRTL is not available, the copter will switch to RTL Mode instead. If the GPS position is not usable, the copter will change to Land Mode instead. 

Enabled always SmartRTL or Land -  switch the copter to SmartRTL mode. If SmartRTL is not available, the copter will switch to Land Mode instead. 

Failsafe PWM:

Default value is 975. Different remote controller may have different values. Please modify it base on your situation.




### Optional Hardware

------



**IMU Temperature Control**

------

IMUs in The Cube are temperature-controlled by onboard heating resistors. Target temperature can be set by changing `BRD_IMU_TARGTEMP` in Full Parameter List. Optimal temperature of IMU is 60 degrees Celsius but it may takes a while (around 10 minutes, variate to actual environment) to reach target temperature. Therefore default temperature in ArduPilot is set as 60 degrees Celsius to shorten the heating time.

It is recommended to set `BRD_IMU_TARGTEMP` to 60 and wait for a while for pre-heating, if you need to maximize the accuracy.  After pre-heating, reboot The Cube. Flight controller will re-log the IMU data and the IMU measurement will be at best performance.



**Sensor Position Offset Compensation**

------

 The sensor’s position offsets are specified as 3 values (X, Y and Z) which are distances in meters from the IMU (which can be assumed to be in the middle of the flight controller board) or the vehicle’s center of gravity. 

![../_images/sensor-position-offsets-xyz.png](../assets/sensor-position-offsets-xyz.png)

- X:  distance forward of the IMU or center of gravity. Positive values are towards the front of the vehicle, negative values are towards the back. 

- Y : distance to the right of the IMU or center of gravity. Positive values are towards the right side of the vehicle, negative values are towards the left. 

-  Z : distance *below* the IMU or center of gravity. Positive values are *lower*, negative values are *higher*.

  >Copter-3.5 (and higher) includes compensation for sensor placement on the vehicle. 
  >
  >The compensation is only *partial* because ArduPilot can correct the vehicle’s velocity and position estimate but it does not correct the acceleration estimate. For example if the flight controller was placed on the nose of a vehicle and the vehicle suddenly leans back (i.e. rotates so that it’s nose points up) with no offset compensation the vehicle velocity estimate would momentarily show the vehicle is climbing when it’s not. With the position offsets added the velocity would not show this momentary climb. The EKF would still show a momentary vertical acceleration and because we use the acceleration in our altitude hold controllers this could still lead to the vehicle momentary reducing throttle. 

IMU (aka INS):

For the best results the flight controller (and thus the IMUs) should be placed at the center-of-gravity of the vehicle but if this is physically impossible the offset can be partially compensated for by setting the following parameters. 

`INS_POS1_X`、 `INS_POS1_Y`、 `INS_POS1_Z` the first IMU’s position from the vehicle’s center-of-gravity.

`INS_POS2_X`、 `INS_POS2_Y`、 `INS_POS2_Z` the second IMU’s position from the vehicle’s center-of-gravity.

`INS_POS3_X`、 `INS_POS3_Y`、 `INS_POS3_Z ` the third IMU’s position from the vehicle’s center-of-gravity.

Fore more information please refer to [**Sensor Position Offset Compensation**](http://ardupilot.org/copter/docs/common-sensor-offset-compensation.html#) on Ardupilot.



GPS Blending (aka Dual GPS)

------

Only GPSs that report position and speed accuracy can be used for blending. All UBlox GPSs provide this extra information while GPSs using the NMEA protocol generally do not.

Normally blending should be done with two GPSs from the same manufacturer because the scaling of the accuracy numbers varies and will lead to favouring one GPS over the other.

> Note: Two GPSs should not be used on Copter-3.4.5 (and older) firmware because of the risk of sudden vehicle movements when the primary GPS changes. Copter 3.5 (and higher), Plane 3.8.0 (and higher) and recent versions of Rover all support GPS Blending.



**Hardware Connection**

Connect the 8-pin GPS cable to the `GPS1` JST-GH connector 

Connect the 6-pin GPS cable to the `GPS2` JST-GH connector 

Connect the 4-pin GPS cable to the `CAN 1、2` JST-GH connector

> GPS blending supports up to 2 GPS modules.

**Setup through the Ground Station**

Change the following parameters in ArduPilot firmware to enable GPS blending mode.

- `SERIAL4_PROTOCOL` = 5 /“GPS”。Alternatively `TELEM1` or `TELEM2` can be used by setting `SERIAL1_PROTOCOL` or `SERIAL2_PROTOCOL` to 5.
- `GPS_TYPE2` = 1 /“AUTO” or the specific number corresponding to the type of GPS
- `GPS_AUTO_SWITCH` = 2 / “Blend”. Alternatively set to 1 / “UseBest” to only use the better GPS. The better GPS is decided based on the GPS’s self reported accuracy.



**ADS-B Receiver**

------

ADS-B (aka Automatic Dependent Surveillance Broadcast) is an air traffic surveillance technology that enables aircraft to be accurately tracked by air traffic controllers and other pilots without the need for conventional radar.

There are 2 ways to use ADS-B: 

1. Use carrier board with built-in ADS-B
2. ADSB receivers with a DF13 serial cable that can be plugged directly into serial port on The Cube.



**ADS-B Carrier Board Configuration**

Open Mission Planner and connect to Cube. In "Config/Tuning > Fill Parameter List" screen modify the parameters according to your need. 

> `ADS-B_ENABLE` = 1 (enable ADSB function)
>
> `SERIAL5_BAUD` = 57 (set baud rate as 57600)
>
> `SERIAL5_PROTOCOL` = 1 (set protocol as MAVLink )
>
> `SR0_ADSB` = 2 (ADSB stream rate to ground station in hertz)
>
> `ADSB_LIST_MAX` = 25  (ADSB list size of nearest vehicles)
>
> `ADSB_LIST_RADIUS` = 10000（ADSB vehicle list radius filter. Vehicles detected outside this radius will be completely ignored. A value of 0 will disable this filter. )
> 
> `AVD_ENABLE` = 1 (Enable Avoidance using ADSB)
>
> > The AVD parameters will only appear after `AVD_ENABLE` set to 1 and then refresh params.
>
> `AVD_W_ACTION` =1 (Specifies aircraft behaviour when a collision may occur)
>
> `AVD_F_ACTION` = 1 (Specifies aircraft behaviour when a collision is imminent [0:None 1:Report 2:Climb Or Descend 3:Move Horizontally 4:Move Perpendicularly in 3D 5:RTL 6:Hover])
>
> `AVD_F_RCVRY` = 2  (Determines what the aircraft will do after a fail event is resolved [0:Remain in AVOID_ADSB 1:Resume previous flight mode 2:RTL 3:Resume if AUTO else Loiter]) 



**Connect and Configure ADS-B Receiver Ping**

Set the `ADSB_ENABLE` parameter to `1` to enable receiving data from the ADS-B sensor.

If you are using one of the UARTs on your board which defaults to MAVLink (i.e. `TELEM1`,`TELEM2` on The Cube) then the default settings will work fine for the PingRx. Alternatively you can connect the Ping to one of the other UARTs, such as the GPS UART (if it is unused) or the serial4/5 UART. In that case you will need to configure the UART as MAVLink at a baudrate of 57600.

For example, if you plugged the Ping into “serial4/5” on The Cube you would set:

> `SERIAL4_PROTOCOL` =1 (meaning MAVLink)
>`SERIAL4_BAUD` =57 (meaning 57600)

For the Ping2020 you will need to set the `SERIAL4_PROTOCOL` value to 2. For example, when connected to `TELEM2` you would set:

> `SERIAL2_PROTOCOL` = 2 (meaning MAVLink2.1.0)

You will need to reboot your board after making those changes.

To enable streaming the ADSB data to the GCS you’ll want to check your StreamRate param. In some cases it is already set but it’s good to check. These rates are adjustable per telemetry like in the case of having both a high-bandwidth and a low-bandwitdh link attached. The param to adjust the rate would depend on which one your GCS is connected to. In most cases, it is `TELEM1`.

> `SR1_ADSB` = 5 (meaning 5 Hz)

Once operational aircraft within about 50km should appear on the Mission Planner map.



**OSD (On-Screen Display)**

------

Optional OSD Module

An optional OSD (On Screen Display) module receives real-time data from vehicle and overlay those information on the camera. The video is then streaming through video transmitter and can be viewed in the GCS. To enable video display, Connect the 6 pin DF13 cable from the module to `TELEM2` on The Cube. [More details](http://ardupilot.org/copter/docs/common-minim-osd-quick-installation-guide.html)

​                                                                                                                                    

​                          

​                                                                                         



​                                      











 







 Last Update: 20th November 2019


# Mandatory Hardware Basic Configuration

The following section explains the basic configurations that need to be made on the mandatory hardware. For more advanced configurations, refer to the ArduPilot documentation: [https://ardupilot.org/ardupilot/](https://ardupilot.org/ardupilot/).

## Calibrating the Accelerometer&#x20;

To calibrate the accelerometer, complete the following steps:

1. Open Mission Planner.
2. Click **Setup ->** **Mandatory Hardware ->** **Accel Calibration**.&#x20;
3. Click **Calibrate Accel**.
4. Place the unmanned aerial vehicle (UAV) level to the ground; then, click **Click when Done**.

![](<../../.gitbook/assets/Photo - 10.jpg>)

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 162142.png" alt=""><figcaption></figcaption></figure>

5. Place the UAV with the nose pointing to the front and the left side touching the ground; then, click **Click when Done**.

![](<../../.gitbook/assets/Photo - 12 (1) (1).jpg>)

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 162643.png" alt=""><figcaption></figcaption></figure>

6. Place the UAV with the nose pointing to the back and the right side touching the ground; then, click **Click when Done**.

<figure><img src="../../.gitbook/assets/Photo - 12.jpg" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 163016.png" alt=""><figcaption></figcaption></figure>

7. Place the UAV with the nose touching the ground; then, click **Click when Done**.

![](<../../.gitbook/assets/Photo - 14.jpg>)

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 163127.png" alt=""><figcaption></figcaption></figure>

8. Place the UAV with the nose pointing upward; then, click **Click when Done**.

![](<../../.gitbook/assets/Photo - 16.jpg>)

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 163302.png" alt=""><figcaption></figcaption></figure>

9. Place the UAV with the nose pointing downwards; then, click **Click when Done**.

![](<../../.gitbook/assets/Photo - 18.jpg>)

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 164605.png" alt=""><figcaption></figcaption></figure>

10. Verify that "**Calibration successful**" is shown.

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 164735.png" alt=""><figcaption></figcaption></figure>

For more details on how to minimize the magnetic interference and improve the compass performance, refer to [http://ardupilot.org/copter/docs/common-magnetic-interference.html#common-magnetic-interference](https://ardupilot.org/copter/docs/common-magnetic-interference.html#common-magnetic-interference)

## Calibrating the Accelerometer Level

To calibrate the accelerometer level, complete the following steps:

1. Open Mission Planner.
2. Click **Setup** -> **Mandatory Hardware** -> **Accel Calibration**.
3. Place the vehicle level to the ground and click **Calibrate Level**.&#x20;
4. Verify that "**Completed**" is shown.

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 165257.png" alt=""><figcaption></figcaption></figure>

## Calibrating the Accelerometer Scale Factors

To calibrate the accelerometer scale factors, complete the following steps:

1. Click **Setup** -> **Mandatory Hardware** -> **Accel Calibration.**
2. Place the vehicle level to the ground and click **Simple Accel Cal**.&#x20;
3. Verify that "**Completed**" is shown.

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 165428.png" alt=""><figcaption></figcaption></figure>

## Calibrating the Compass

To calibrate the compass, complete the following steps:

1. Click **Setup** -> **Mandatory Hardware** -> **Compass.**
2. Select the priority for the three different compasses by clicking the up and down arrows.
3. Click **Start** to calibrate the compasses.&#x20;
4. Hold the UAV in the air and slowly rotate it so that each side—front, back, left, right, top, and bottom—faces the ground for a few seconds. As the UAV is rotated, the green bars on the display begin to extend to the right.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 170054.png" alt=""><figcaption></figcaption></figure>

5. Continue rotating the UAV until "**Success"** is shown. A rising tone will be emitted.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 170442.png" alt=""><figcaption></figcaption></figure>

7. When the “**Please reboot the autopilot**” window appears, click **OK**. The autopilot needs to be rebooted before the UAV can be armed. &#x20;

![](<../../.gitbook/assets/Photo - 23.jpg>)

{% hint style="info" %}
If the compass cannot be calibrated, click **Cancel.** Then, click the **Fitness** drop-down menu and select a more relaxed setting to try again.
{% endhint %}

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 170720.png" alt=""><figcaption></figcaption></figure>

## Calibrating the Radio Control

To calibrate the radio control, complete the following steps:

1. Open Mission Planner.
2. Click **Setup** -> **Mandatory Hardware** -> **Radio Calibration**.
3. Connect the RC receiver to the RCIN port on The Cube and turn on the RC transmitter.&#x20;
4. Verify that the receiver displays a solid green light, which indicates a successful connection with the transmitter, and ensure the transmitter is set to the correct UAV.
5. Verify that the green bars move when adjusting the transmitter sticks.
6. When completed, click **Click when Done**.

<figure><img src="../../.gitbook/assets/Screenshot 2024-10-28 171415.png" alt=""><figcaption></figcaption></figure>

## Calibrating the Electronic Speed Controller (ESC)

To calibrate the ESC, complete the following steps:

{% hint style="danger" %}
Before calibrating the ESC, ensure the following:

* No props on the UAV.&#x20;
* The Cube is not connected to the GCS via a USB cable.
* The LiPo battery is disconnected.
{% endhint %}

![](<../../.gitbook/assets/Photo - 27.jpg>)

1. Turn on the transmitter and adjust the throttle stick to maximum.

![](<../../.gitbook/assets/Photo - 28.jpg>)

2. Connect the LiPo battery to the power module.  When connected, The Cube's red, blue, and yellow LEDs will light up in a cyclical pattern.&#x20;

![](<../../.gitbook/assets/Photo - 29.jpg>)

3. With the transmitter throttle stick still adjusted to high, disconnect and reconnect the battery.

![](<../../.gitbook/assets/Photo - 30.jpg>)

4. Press and hold the safety button until it displays a solid red color. The autopilot is now in ESC calibration mode. The red and blue LEDs will blink on and off.
5. Wait for the ESCs to emit a musical tone -> a series of beeps indicating the battery cell count (e.g., 3 beeps for 3S, 4 beeps for 4S), followed by two additional beeps to confirm maximum throttle capture.
6. Adjust the transmitter’s throttle stick to minimum. The ESCs will emit a long tone indicating the minimum throttle has been captured and the calibration is complete.

![](<../../.gitbook/assets/Photo - 31.jpg>)

7. Verify a long tone is emitted, which indicates the ESCs are “live” now.&#x20;
8. Test if the motors can spin by slightly raising the throttle and then lowering it.
9. Set the throttle to minimum and disconnect the battery to exit the ESC-calibration mode.

## Configuring the Flight Mode

The flight mode channel (default is channel 5) is the input radio channel that ArduPilot monitors for mode changes.&#x20;

To change the channel number, complete the following steps:

1. Open Mission Planner.
2. Click **Config** -> **Full Parameter List**
3. Adjust the FLTMODE-CH parameter.

To configure the flight mode, complete the following steps:

1. Open Mission Planner.
2. Click **Setup** -> **Flight Modes**.
3. Toggle the corresponding button to the desired flight mode position.
4. Move the transmitter’s flight mode switch and observe the green bar moving to a new position.
5. When finished, click **Save**.

A total of six autopilot/flight modes can be enabled from the RC transmitter.

<figure><img src="../../.gitbook/assets/flight mode.png" alt=""><figcaption></figcaption></figure>

See below for a brief description of the different flight modes. For a more detailed explanation, refer to the ArduPilot documentation:

* [https://ardupilot.org/plane/docs/flight-modes.html](https://ardupilot.org/plane/docs/flight-modes.html)
* [https://ardupilot.org/copter/docs/flight-modes.html](https://ardupilot.org/copter/docs/flight-modes.html)

| **Manual**                                                                                        | **Circle**                                                                                     | **Stabilize**                                                                  |
| ------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Manual control surface movement, passthrough                                                      | Automatically circles a point in front of the UAV.                                             | Self-levels the roll and pitch axis.                                           |
| **Training**                                                                                      | **Acro**                                                                                       | **FBWA**                                                                       |
| Manual control up to roll and pitch limits                                                        | Holds attitude, no self-level.                                                                 | Roll and pitch follow stick input, up to set limits                            |
| **FBWB**                                                                                          | **Cruise**                                                                                     | **Autotune**                                                                   |
| Like FBWA, but with automatic height and speed control                                            | Like FBWB, but with ground course tracking                                                     | Automated pitch and bank procedure to improve control loops                    |
| **Auto**                                                                                          | **RTL (Return to Launch)**                                                                     | **Loite**r                                                                     |
| Executes pre-defined mission                                                                      | Returns above takeoff location, may also include landing                                       | Holds altitude and position, uses GPS for movements                            |
| **Takeoff**                                                                                       | **Avoid ADSB**                                                                                 | **Guided**                                                                     |
| Automatic takeoff to specific altitude, and loiter at distance from takeoff until mode is changed | Avoid manned vehicles based on the ADS-B sensor's output.                                      | Navigates to single points commanded by GCS                                    |
| **Qstabilize**                                                                                    | **Qhover**                                                                                     | **Qloiter**                                                                    |
| Allows the UAV to be flownmanually, but self-levels the roll and pitch axis.                      | Maintains a consistent altitude while allowing roll, pitch, and yaw to be controlled normally. | Automatically attempts to maintain the current location, heading and altitude. |
| **Qland**                                                                                         | **QRTL**                                                                                       | **Qautotune**                                                                  |
| Attempts to bring the UAV straight down for landing.                                              | Navigates UAV from its current position to hover above the home position and then land.        | Supports autotuning PIDs.                                                      |
| **Qacro**                                                                                         | **Thermal**                                                                                    | **Loiter to Qland**                                                            |
| For advanced users that provides rate based stabilization.                                        | Mode entered to search for thermal lift by SOARING feature or manually if lift is encountered. | Performs a descending down action and then switches to QLand mode.             |
| **Initializing**                                                                                  |                                                                                                |                                                                                |
| Initializes the flight mode.                                                                      |                                                                                                |                                                                                |

## Configuring the Servo Connection

The servo rail is not powered by The Cube. Therefore, an external BEC or ESC that can provide 5V is needed.

To configure the control channels for the servos, complete the following steps:

1. Open Mission Planner
2. Click **Setup** -> **Mandatory Hardware** -> **Servo Output**.
3. Adjust the parameters based on the requirements.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 114809.png" alt=""><figcaption></figcaption></figure>


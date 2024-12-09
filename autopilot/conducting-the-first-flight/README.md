# Conducting the First Flight

## Pre-Arm Safety Check

Mission Planner has a list of pre-arm safety checks that prevent the unmanned aerial vehicle (UAV) from arming if any issues are detected before take-off. This could include missed calibrations, improper configurations, bad sensor data, etc. The safety checks help prevent crashes and fly-aways. If necessary, the safety checks can be disabled.

Use the following guidance:

* **When the LED flashes blue or green**, it means the UAV can be armed. During the arming process, a low-pitch tone is emitted from the buzzer. The motors start to rotate and the UAV is ready to take off.
* **When the LED flashes yellow**, disarm the UAV. The failure messages are shown on the HUD. Use the displayed failure message to resolve the error. For more details on the failure messages and solutions, go to  [https://ardupilot.org/copter/docs/safety-multicopter.html](https://ardupilot.org/copter/docs/safety-multicopter.html).

For more details on the LED indicators, refer to the table below.&#x20;

## LED Indicators

| LED Indicator                    | Description                                                                                                                                                                         |
| -------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Flashing red and blue            | Initializing sensors. Keep the UAV stationary and level while the sensors are being initialized.                                                                                    |
| Flashing blue                    | <p>Disarmed with no GPS lock. <br>Auto-mission, loiter, and return-to-launch flight modes require GPS lock.</p>                                                                     |
| Solid blue                       | Armed with no GPS lock.                                                                                                                                                             |
| Flashing green                   | Disarmed (but ready to arm) and GPS lock acquired. Rapid double tone when disarming from the armed state.                                                                           |
| Flashing green rapidly           | Same as above, but GPS uses Satellite Based Augmentation System (SBAS). The position estimation should be better.                                                                   |
| Solid green                      | <p>Single long tone during arming. <br>When armed and GPS lock is acquired, UAV is ready to fly.  </p>                                                                              |
| Double flashing yellow           | Failed pre-arm checks (system refuses to arm).                                                                                                                                      |
| Single flashing yellow           | Radio failsafe activated.                                                                                                                                                           |
| Flashing yellow                  | <p>Rapid beeping tone. <br>Battery failsafe activated.</p>                                                                                                                          |
| Flashing yellow and blue         | <p>High-high-high-low tone sequence (dah-dah-dah-doh).<br>GPS glitch or GPS failsafe activated.</p>                                                                                 |
| Flashing red and yellow          | Extended Kalman Filter (EKF) or inertial navigation failure.                                                                                                                        |
| Flashing purple and yellow       | Barometer glitch.                                                                                                                                                                   |
| Solid Red                        | Error, usually due to SD card, MTD, or IMU. To resolve the issue, remove and insert the SD card. Additionally, check the SD card and analyze the boot message in the BOOT.txt file. |
| Solid red with SOS tone sequence | SD card missing or bad SD card.                                                                                                                                                     |
| No light when powered on         | No firmware, firmware lost, SD card missing or bad format (ac3.4 or higher version).                                                                                                |

## Arming The Cube

The Cube can be armed by the following methods:

#### **Remote controlle**r

Hold the throttle down and keep the rudder to the right for five seconds.&#x20;

{% hint style="info" %}
Do not keep the rudder right for more than 15 seconds, as this will enable the AutoTrim feature.
{% endhint %}

#### **Ground Control Station (GCS)**

1. Connect The Cube to the GCS.
2. Open Mission Planner.&#x20;
3. Click **Action** under the HUD.&#x20;
4. Click **Arm/Disarm** to arm the vehicle.

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 141158.png" alt="" width="442"><figcaption></figcaption></figure>

# System Architecture

The Cube system architecture incorporates two functional blocks into a single physical module.

![](<../../../.gitbook/assets/Cube System architecture.png>)

### PWM Outputs

Eight PWM outputs are connected to the I/O.&#x20;

* Can be directly controlled by the I/O via the R/C input and onboard mixing even if the FMU is not active (failsafe/manual mode).&#x20;
* Supports multiple update rates in three groups (one group of four outputs and two groups of two outputs).
* Supports signal rates reaching up to 400Hz.&#x20;
* Output only.
* Each PWM output can drive up to 50mA, but the total limit for all eight outputs is 100mA.

Six PWM outputs are connected to the FMU.&#x20;

* Supports reduced update latency.
* Cannot be controlled by the I/O in failsafe conditions.&#x20;
* Supports multiple update rates in two groups (one group of four and one group of two).

All the PWM outputs are EDS-protected and are designed to survive accidental servo misconnection without damage. The servo drivers are specified to drive a 50pF servo input load over 2m of 26AWG servo cable.

The I/O PWM outputs can also be configured as individual GPIOs.&#x20;

{% hint style="info" %}
The I/O PWM outputs are not high-power outputs. The PWM drivers are only designed to drive servos and similar logic inputs and do not include relays or LEDs.
{% endhint %}

### Peripheral Ports

All peripherals are connected through a single 80-pin connector. The peripherals are connected via a baseboard that can be customized for each application.

### Base Board

The initial base board features separate the connectors for each of the peripheral ports, but with a few exceptions.

#### Serial Ports

* Five serial ports are provided.&#x20;
* The serial ports operate at a 3.3V CMOS logic level. They are 5V tolerant, buffered, and ESD-protected.
* Serial 1 and 2 feature full flow control.
* Serial 3 is recommended to function as a GPS port. A safety button and possibly a safety LED are included. An I2C for the compass and RGB LED is also provided.
* Serial 4 has an I2C on the second bus, allowing two compass modules to be connected simultaneously.
* Serial 5 is available as a header underneath the board. It is used for the onboard ADSB-IN receiver that is featured on newer carrier boards.

#### SPI Port

* Not buffered. Should only be used with short cable runs.
* Signals are 3.3V CMOS logic level, but 5V tolerant.
* SPI is only available to test points on the first base board, along with a CS and INT pin.

#### Analog Inputs

* Analogue 1-3 are protected against inputs up to 12V, but scaled for 0-3.3V inputs.&#x20;
* The RSSI input supports either PWM or analog RSSI. As this input shares a pin with the S.Bus output, only one of them may be connected at a time.

#### CPPM, S.Bus and DSM/Spektrum Input

These inputs remain unchanged from the previous versions.

#### CAN Ports

The CAN ports are standard CAN Bus. Termination for one end of the bus is fixed on board. The drivers are onboard the FMU.

#### Piezo Port

The piezo port drives most piezo elements in the 5 - 300nF range at up to 35V. It is extremely loud, where the achievable sound pressure level is limited by the sensitivity of the piezo element being driven.

#### I2C

I2C is direct driven, un-buffered, and pulled up to 3.3v onboard the FMU.

### Sensors

All flight sensors in The Cube are connected via SPI.

| Cube Type                                                                                                                                                                                                          | Life Cycle | IMU1                | IMU2                                 | IMU3                | Barometer1 | Barometer2 |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | ------------------- | ------------------------------------ | ------------------- | ---------- | ---------- |
| <p><strong>Cube Black</strong> </p><p><mark style="color:blue;"><strong>Cube BlueF4</strong></mark> </p><p><mark style="color:green;"><strong>Cube Green</strong></mark></p>                                       | EOL        | MPU9250             | LSM303D/L3GD20                       | MPU9250             | MS5611     | MS6511     |
| **Cube Black+**                                                                                                                                                                                                    | EOL        | MPU9250             | ICM20602                             | ICM20948            | MS5611     | MS5611     |
| **Cube PurpleF4**                                                                                                                                                                                                  | EOL        | MPU9250             | NA                                   | NA                  | MS5611     | NA         |
| <mark style="color:purple;">**CubePurpleH7**</mark>                                                                                                                                                                | ACTIVE     | ICM20649            | NA                                   | NA                  | MS5611     | NA         |
| <p><mark style="color:orange;"><strong>Cube Orange</strong></mark> </p><p><mark style="color:yellow;"><strong>Cube Yellow</strong></mark> </p><p><mark style="color:blue;"><strong>Cube BlueH7</strong></mark></p> | ACTIVE     | ICM20649            | ICM20602                             | ICM20948            | MS5611     | MS5611     |
| <mark style="color:orange;">**Cube Orange+**</mark>                                                                                                                                                                | ACTIVE     | ICM45686 / ICM20649 | ICM20948 / ICM42688 / ICM45686\_EXT2 | ICM42688 / ICM45686 | MS5611     | MS5611     |

{% hint style="info" %}
* IMU1 is not isolated.
* IMU2 and IMU3 are isolated.
* Data-ready signals from any of the sensors are **NOT ROUTED on the Isolated IMU.**
{% endhint %}

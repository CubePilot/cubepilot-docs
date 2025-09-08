# Optional Hardware Basic Configuration

The following section explains the basic configurations that need to be made on the optional hardware. For more advanced configurations, refer to the ArduPilot documentation: [https://ardupilot.org/ardupilot/](https://ardupilot.org/ardupilot/).

## Calibrating the Cube Power Module Voltage

The power module inside The Cube package supports up to 8S voltage, 30A continuous current, and 100A burst current. If a higher load is needed, replace the power module with a higher current limit.

## Connecting the Power Module

To connect the power module, complete the following steps:

1. Connect the XT60 male connector to the battery (female on the other side for motors or ESC) and plug the JST connector into the POWER1 port on The Cube.
2. If necessary, connect the second battery to the POWER2 port on The Cube to monitor two batteries at the same time, as dual input redundant power is supported.&#x20;

## Calibrating the Battery Monitor

To calibrate the Battery Monitor, complete the following steps:

1. Open Mission Planner.
2. Click **Setup** -> **Optional Hardware** -> **Battery Monitor**.
3. Connect The Cube to the power module and power it up.&#x20;
4. Enter the properties the power module can measure, which include the module type, flight controller type, and battery capacity.

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 115344.png" alt=""><figcaption></figcaption></figure>

Default parameters may return inaccurate voltage. When this happens, complete the following steps:

1. Use the following formula to calculate the correct Voltage Divider:

**Voltage Divider Value \* Actual Battery Voltage/Voltage Measured by Power Module = Correct Voltage Divider Value**

2. Enter the new Voltage Divider value and reboot the flight controller.&#x20;
3. Verify if the measured voltage is accurate.

## Calibrating Battery Monitor 2

Battery Monitor 2 corresponds to the POWER2 port on The Cube.

To calibrate Battery Monitor 2, complete the following steps:

1. Open Mission Planner.
2. Click **Config** -> **Full Parameter List** and adjust the parameters highlighted in green to enable battery \_\*\_monitor 2:

![](<../../.gitbook/assets/Photo - 36.jpg>)

3. Enter the power module's properties and type, the flight controller type, and the battery capacity. The Voltage Divider calculation is the same as for the Battery Monitor.

<figure><img src="../../.gitbook/assets/Screenshot 2025-09-08 165944.png" alt=""><figcaption></figcaption></figure>

Monitor: Analog Voltage Only

Volt Pin: Pixhawk/Pixracer/Navio2/Pixhawk

Current Pin: Pixhawk/Pixracer/Navio2/Pixhawk

### Displaying Battery Monitor 2 Voltage on HUD

To display the Battery Monitor 2 voltage on the HUD, complete the following steps:

1. Open Mission Planner.
2. Click **Data**.
3. Move the cursor to the HUD and right-click mouse.
4. Select **User Items** to open the **Display This** window.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 121447.png" alt="" width="455"><figcaption></figcaption></figure>

5. Select **battery-voltage2** and modify the display header.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 121622.png" alt=""><figcaption></figcaption></figure>

6. Click **OK.** The Battery Monitor 2 voltage will be displayed on the HUD.

## IMU Temperature Control

The IMUs are temperature-controlled by onboard heating resistors. The pre-heating time will vary based on the environmental conditions and the set target temperature.&#x20;

To adjust the IMU temperature control, complete the following steps:

1. Open Mission Planner.
2. Click **Config** -> **Full Parameter List**.
3. Adjust the target temperature by changing the BRD\_HEAT\_TARG parameter.  It is recommended to set BRD\_HEAT\_TARG to 60°C for the most accurate IMU measurements.&#x20;
4. After the pre-heating is completed, reboot The Cube to let it re-log the IMU data.

## GPS Blending (Dual GPS)

Only GPS modules that report both position and speed accuracy can be used for GPS blending.

The two GPS modules should be from the same manufacturer, as differences in how the accuracy is scaled can cause one GPS to be favored over the other.

{% hint style="warning" %}
If Copter-3.4.5 or older firmware is installed, do not use two GPS modules. Switching to the primary GPS module could result in sudden vehicle movements.

The following firmware versions support GPS Blending:

* Copter 3.5 or higher
* Plane 3.8.0 or higher
* Recent versions of Rover
{% endhint %}

### Connecting the GPS modules to The Cube

To connect the GPS modules to The Cube, complete the following steps:

1. Connect the 8-pin DF13 connector on one of the GPS modules to GPS1 port.&#x20;
2. Connect the the 8-pin DF13 connector on the other GPS module to GPS2 port.

The GPS module can be connected to other ports if that port has the supported protocols.&#x20;

For Here GPS modules, all the LEDs use the same I2C address. Thus, the LED on GPS2 will not light up.

### Enabling the GPS Blending Mode

To enable the GPS blending mode, change the following parameters in the ArduPilot firmware:

* SERIAL4\_PROTOCOL = 5 /“GPS”. Alternatively, TELEM1 or TELEM2 can be used by setting SERIAL1\_PROTOCOL or SERIAL2\_PROTOCOL to 5.
* GPS\_TYPE2 = 1 /“AUTO” or the specific number corresponding to the GPS type.
* GPS\_AUTO\_SWITCH = 2 / “Blend”. Alternatively, set to 1/“UseBest” to only use the better GPS, which is decided based on the GPS’s self reported accuracy.

## Automatic Dependent Surveillance Broadcast (ADS-B) Receiver

ADS-B is an air traffic surveillance technology that enables the aircraft to be accurately tracked by air traffic controllers or pilots without a conventional radar. Some carrier boards come with the ADS-B antenna included. If it is not included, a ADS-B receiver can be bought, which includes the following two types:&#x20;

* PingRX
* Ping2020

### Connecting the ADS-B Receiver to The Cube

To connect the receiver to The Cube, connect the DF13 serial cable to a serial port on The Cube. The sensor should be mounted with the antenna oriented vertically.

### Receiving Data from the ADS-B Receiver

To receive data from the ADS-B receiver, complete the following steps:

1. Open Mission Planner.
2. Click **Config** -> **Full Parameter List**.
3. Enable the ADSB\_TYPE parameter to receive data from the ADSB sensor. For older Mission Planner versions, set the ADSB\_ENABLE parameter to "1".
4. Check which UART port was used.&#x20;

* If TELEM1 or TELEM2 (UART) was connected, it means MAVLink is being used. No additional settings need to be made for the ADS-B Receiver.&#x20;
* If GPS UART serial 4/5 UART was connected, configure the UART to MAVLink with a baud rate of 57600.

For example, if “serial4/5” was used, set the following:

SERIAL4\_PROTOCOL =1 (meaning MAVLink) SERIAL4\_BAUD =57 (baud rate is 57600)

5. Reboot the The Cube.
6. Open Mission Planner again.
7. Click **Config** -> **Full Parameter List**.
8. Adjust the StreamRate parameter (SR\*\_ADSB) to enable ADS-B data streaming to the GCS. The rate varies based on the telemetry, which is similar to having both a high-bandwidth and a low-bandwidth link attached. In most cases, this would be TELEM1. Thus, set SR1\_ADSB = 5 (meaning 5Hz)

Once configured, operational aircraft within approximately 50km should appear on the Mission Planner map.

## On-Screen Display (OSD)

The OSD module receives real-time data from the UAV and overlays this information onto the video feed from the camera. The video is then streamed via the video transmitter to the GCS. To enable this function, connect the module's 6-pin DF13 cable to the TELEM2 port on The Cube.

# Here+V2 User Manual

### Overview

HERE+/HERE+ V2 RTK kit developed by HEX and Ardupilot Team is compatible with Mission Planner, a ground control station for ArduPilot, as well as PX4 and QGroundControl. The kit is the first Differential Global Positioning System \(DGPS\) module for open source flight controller users. 

RTK technology provides much more accurate position estimates than regular GNSS systems. Its ideal accuracy can reach up to centimeters, which greatly improve the precision of flight. 

Being the first RTK positioning system developed for open source community, HERE+ is easy to use. The Here+ GPS kit comes with a base and a rover. The base can work with Mission Planner with minimum setup required. The data communication between rover and base modules is through a pair of telemetry module\(not provided in the standard Here+ package\). 

HERE+/HERE+ V2 has a full set of Inertial navigation system \(gyroscope, accelerometer, compass and barometer\) and GNSS data to acquire more accurate navigation. In the Ardupilot and PX4 firmware, RTK positioning data is fused with build-in Extended Kalman filter \(EKF\) algorithm for optimized positioning result.

### High Precision Positioning:

Many applications of UAV need better precision than what regular GNSS can provide. For example: UAV surveying and mapping; agriculture measuring; high precision take-off and landing; UAV swarming; etc.

RTK Differential GPS that is compatible with open source flight controllers THE CUBE、pixhawk、APM.

-Support 1 Base to Multiple Rovers   
-Light and Power Efficient RTK Real-time DGPS Solution   
-Centimeters Level Positioning and Navigation

By Real-time kinematic technology, HERE+ provides real-time 3D coordinate of the observing point. Transmitting carrier phase measurement of the base to rover for correction. Comparing carrier phase from GPS and base respectively, the module calculate the phase difference to obtain centimeters level positioning in real-time.

### The Standard Here+ Kit Includes:

#### HERE+ V1

| Item | Number |
| :--- | :--- |
| here+ RTK Rover | x1 |
| here+ RTK Rover Connecting Cable | x1 |
| here+ RTK Base Base | x1 |
| here+ RTK Base Base USB Cable | x1 |

#### HERE+ V2

| Item | Number |
| :--- | :--- |
| here+ v2 RTK Rover | x1 |
| here+ RTK Rover Connecting Cable \(serial + I2C\) | x1 |
| here+ RTK Rover Connecting Cable \(CAN\) | x1 |
| UART-USB Converter for Upgrading Rover | x1 |
| here+ RTK Base Base | x1 |
| here+ RTK Base Base USB Cable | x1 |

### Antenna Placing

#### Placing the RTK Antenna is very important for getting precise RTK positioning

For the working condition of RTK, there are some special requirements that are more demanding than regular GPS.

The best environment requires the base and rover antenna to have clear view of the sky that is 30 degrees above horizon. RTK antenna can be elevated but make sure that there are no obstacles around, such as buildings, trees, cars, and etc.

**Example of bad environment**: indoors, urban area, forest, near the ground.

**Example of good environment**: Open spaces, peak of the mountains, roof of the buildings.

Do not place the antenna near electronic devices, as high power electronic devices nearby may affect the radio frequency noise of GPS signal. Examples are mobile phone base stations, high voltage transformers, and etc.

### Hardware Specification

#### HERE+ Rover Hardware Parameters

<table>
  <thead>
    <tr>
      <th style="text-align:left">GNSS module</th>
      <th style="text-align:left">Connector</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">u-blox NEO-M8P-0</td>
      <td style="text-align:left">
        <p>HERE+ V1: USB, UART (JST-GH connector)</p>
        <p>HERE+ V2: UART (JST-GH connector)</p>
      </td>
    </tr>
  </tbody>
</table>#### Sensors

| IMU | Compass | Barometer |
| :--- | :--- | :--- |
| MPU9250/ICM20948 | HMC5983/ICM20948 | MS5611 |

#### HERE+ Base Hardware Parameters

| GNSS module | Ceramic antenna | Connector |
| :--- | :--- | :--- |
| u-blox NEO-M8P-2 | CGGBP.25.4.A.02 | USB, UART, SMA |

| GNSS Signals Supported | Working Environment | Working Voltage | Working Temperature |
| :--- | :--- | :--- | :--- |
| GPS L1 C/A，GLONASS L10F， BeiDou B11 | Height 5000m，Velocity 500m/s | 5V | -40℃ to 85℃ |

#### Time-To-First-Fix

**!!Updating in progress!!**


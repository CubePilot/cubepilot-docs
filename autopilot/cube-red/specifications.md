# Specifications

* **Microcontroller**
  * 2 x STM32H7 series microcontrollers (primary controller + secondary controller)
  * Dual-core (Cortex®-M7 + Cortex®-M4) processors
  * Double-precision floating point unit (FPU)
  * Embedded flash memory based on nonvolatile memory (NVM)
  * Primary controller includes external flash memory
  * Supports ambient temperature between 125°C to - 40°C
* **4 x Inertial Measurement Units (IMUs)**
  * 3 x IMUs connected to primary microcontroller
  * 1 x IMU connected to secondary microcontroller
* **1 x Compass**
  * Sensitivity: 13nT
  * Noise: 15nT
  * Linearity over +/- 200 uT: 0.50%
  * Field Measurement Range: +/- 1100 uT
  * Current @ 8Hz, 3 Axes: 260 uA
  * SPI and I2C interface
  * Operating Temperature: -40°C to +85°C
* **Barometric pressure sensor**
  * 3 x barometers
    * 2 x barometer connected to primary microcontroller
    * 1 x barometer connected to secondary microcontroller
  * Altitude resolution of 10 cm
  * Conversion rate down to 1 ms
  * Low power, 1 μA (standby < 0.15 μA)
  * QFN package: 5.0 x 3.0 x 1.0 mm3
  * Supply voltage: 1.8 to 3.6 V
  * Integrated digital pressure sensor (24 bit ΔΣ ADC)
  * Operating range: 10 to 1200 mbar, -40 to +85 °C
  * I2C and SPI interface, up to 20 MHz
  * No external components (internal oscillator)
* **CAN FD Transceiver**
  * 3 x CAN FD ports
    * 1 x CAN FD connected to primary microcontroller
    * 1 x CAN FD connected to secondary microcontroller
    * 1 x CAN FD connected to both primary and secondary microcontroller (serves as a backup if a failure occurs)
  * Optimized for CAN FD (flexible data rate) at 2, 5, and 8 Mbps Operation
  * Meets the latest ISO/DIS 11898-2:2015 specification
  * Supports Wake-up pattern
  * AEC-Q100 Grade 0 Very Low Standby Current (5 µA, typical)
  * VIO supply pin to interface directly to CAN controllers and microcontrollers with 1.7V to 5.5V I/O
  * An unpowered node or brown-out event will not load the CAN bus
  * Permanent dominant detection on TXD
  * Permanent dominant detection on Bus
  * Power-on reset and voltage brown-out protection on VDD pin
  * Protection against damage from short-circuit conditions (positive or negative battery voltage)
  * Protection against high-voltage transients in automotive environments
  * Automatic thermal shutdown protection
  * Suitable for 12V and 24V systems
  * Temperature range: -40°C to +150°C
* USB FS compatible with USB Type C connector
* 10/100BaseT Ethernet interface
* Display Serial Interface (DSI)
* Isolated static air port
* Replaceable, fully closed upper lid and isolated static air ducts provide stable pressure for the barometers, ensuring accurate altitude measurements
* Foams with different hardness options tailored to various flight purposes

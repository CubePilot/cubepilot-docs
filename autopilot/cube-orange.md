---
description: Cube Orange Flight Controller and Carrier Board Specification
---

# Cube Orange

Cube Orange target to education, drones lovers and professional cost-effective flight control hardware providers.

The new generation of more powerful H7 processor, stronger performance, faster, more secure, built-in triple redundant sensor, temperature control shock absorption IUM.

With the help of flight software, Cube Orange can completely fly any remotely controlled aircraft, helicopter or multi-rotor vehicle and become a more professional UAV platform.Getting Super Powers

## About Cube Orange

#### Design goals for this generation

* An integrated all-in-one, integrated flight control 
* Provide adequate data interfaces for most applications that do not require extensions 
* Easier to use, more powerful processors, faster processing 
* Better sensor performance, better power optimization 
* Better microcontroller resources 
* Higher reliability and reduced integration complexity 
* Integrated encryption/hashing module for aes-128, -192 and -256 encryption hardware acceleration, support GCM and CCM, 3DES and hashing \(MD5, sha-1 and sha-2\) algorithm

## Design feature

* All-in-one design with integrated Flight Management Unit \(FMU\), I/O module and sufficient data ports 
* Better industrial manufacturing capability, stronger processing performance and processing speed 
* Separate power supplies for FMU and I/O  \(see power architecture section\)
* Provides on-board backup batteries for the FMU and I/O SRAM \(static memory\)/RTC \(clock chip\) 
* Can be integrated with standard power module

## Features

### Processor

* 32 bit ARM ® STM32H753VIT6 Cortex ® - M7 \(double-precision floating-point unit\) 
* 400 MHz/856 DMIPS/2.14 DMIPS/MHz \(Dhrystone 2.1\) 
* 1 MB RAM:192 KB TCM RAM，64 KB ITCM RAM+128 KB DTCM RAM，864 KB + 4 KB SRAM 
* 2 MB Flash 32 bit STM32F103 fault protection processor 
* The microcontroller has a built-in JPEG hardware accelerator for fast JPEG encoding and decoding

## I/O Ports

* 5 UART \(serial ports\): 1 with high-power capability; 2 with hardware flow control 
* 2 CAN bus \(1 with internal 3.3 V transceiver; 1 on expansion connector\) Compatible with Spektrum DSM / DSM2 / DSM-X® Satellite input
* Compatible with Futaba S.BUS® input and output
* Compatible with PPM sum signal input 
* 2 I2C bus
* 1 SPI port
* 3.3 V ADC inputs
* Internal micro USB port and external micro USB port extension

## Power System and Protection

* deal diode controller with automatic failover 
* High-power \(max. 10 V\) and high-current \(10 A+\) capability on servo rail 
* Over-current protection on all peripheral outputs ，ESD protection on all inputs 
* Triple power supply redundancy by power module, servo rail, and USB port

## Detail Specification

### Processors

| Processor | Model |
| :--- | :--- |
| Main Processor | STM32H753VIT6 \(32 Bit ARM® Cortex®-M7, 400 MHz, 2 MB flash, 864 KB SRAM\) |
| Companion Processor | STM32F100 \(32 Bit ARM® Cortex®-M3, 24 MHz, 8 KB SRAM\) |

## Sensors

| Type of Sensors | Model |
| :--- | :--- |
| Accelerometer | ICM20948 / ICM20649 / ICM20602 |
| Gyroscope | L3GD20 / ICM20649 / ICM20602 |
| Barometric Pressure Sensor | MS5611 |

## Ports Definition

<table>
  <thead>
    <tr>
      <th style="text-align:left">Name</th>
      <th style="text-align:left">Description</th>
      <th style="text-align:left">Marking</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">SERIAL 1 / UART 1</td>
      <td style="text-align:left">UART 1 with hardware flow control. 3.3V-5V CMOS TTL level, with ESD protection</td>
      <td
      style="text-align:left">TELEM1</td>
    </tr>
    <tr>
      <td style="text-align:left">SERIAL 2 / UART 2</td>
      <td style="text-align:left">UART 2 with hardware flow control. 3.3V-5V CMOS TTL level, with ESD protection</td>
      <td
      style="text-align:left">TELEM2</td>
    </tr>
    <tr>
      <td style="text-align:left">SERIAL 3 / UART 3 /I2C 1</td>
      <td style="text-align:left">3.3V-5V CMOS TTL level, with ESD protection</td>
      <td style="text-align:left">GPS1</td>
    </tr>
    <tr>
      <td style="text-align:left">SERIAL 4 / UART 4 / I2C 2</td>
      <td style="text-align:left">UART 4 / I2C 2, 3.3V-5V CMOS TTL level, with ESD protection</td>
      <td style="text-align:left">GPS2</td>
    </tr>
    <tr>
      <td style="text-align:left">SERIAL 5 / UART 5 (Debug Console)</td>
      <td style="text-align:left">UART 5. Debug Console</td>
      <td style="text-align:left">CONS</td>
    </tr>
    <tr>
      <td style="text-align:left">I2C 2</td>
      <td style="text-align:left">Independent I2C 2 port. Drivers are on-board on FMU. UN- buffered, and
        pulled up to 3.3V COMS TTL level</td>
      <td style="text-align:left">I2C2</td>
    </tr>
    <tr>
      <td style="text-align:left">CAN Bus</td>
      <td style="text-align:left">Standard CAN Bus. Drivers are on-board on FMU.</td>
      <td style="text-align:left">
        <p>CAN1</p>
        <p>CAN2</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">R/C IN</td>
      <td style="text-align:left">Support CPPM / Futaba S.Bus signal input</td>
      <td style="text-align:left">RCIN</td>
    </tr>
    <tr>
      <td style="text-align:left">DSM / USART</td>
      <td style="text-align:left">Support Spektrum DSM&#xAE; Technology, DSM2 / DSMX Satellite compatible
        input; I/O USART 1 RX</td>
      <td style="text-align:left">SKPT</td>
    </tr>
    <tr>
      <td style="text-align:left">S.Bus OUT / RSSI IN</td>
      <td style="text-align:left">S.Bus Servo I/O. PPM Output. Can be used as RSSI input</td>
      <td style="text-align:left">SBUSo</td>
    </tr>
    <tr>
      <td style="text-align:left">POWER</td>
      <td style="text-align:left">Main Power source and Backup Power source Input</td>
      <td style="text-align:left">
        <p>POWER1</p>
        <p>POWER2</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">MAIN OUT</td>
      <td style="text-align:left">Standard PWM Servo Signal I/O Port x 8</td>
      <td style="text-align:left">MAINOUT</td>
    </tr>
    <tr>
      <td style="text-align:left">AUX OUT</td>
      <td style="text-align:left">Programmable FMU GPIO x 6. Support PWM Signal Output</td>
      <td style="text-align:left">AUX OUT</td>
    </tr>
    <tr>
      <td style="text-align:left">USB</td>
      <td style="text-align:left">Human Machine Interface (HMI): LED, Speaker and USB extension</td>
      <td
      style="text-align:left">USB</td>
    </tr>
    <tr>
      <td style="text-align:left">ADC</td>
      <td style="text-align:left">3.3 V and 6.6 V ADC Input</td>
      <td style="text-align:left">ADC</td>
    </tr>
    <tr>
      <td style="text-align:left">USB</td>
      <td style="text-align:left">USB 2.0 (Micro - B 5 Pin)</td>
      <td style="text-align:left">The Cube</td>
    </tr>
    <tr>
      <td style="text-align:left">SD Card / SDIO</td>
      <td style="text-align:left">MicroSD Card for Log Storage; Support SDIO</td>
      <td style="text-align:left">The Cube</td>
    </tr>
    <tr>
      <td style="text-align:left">SPI</td>
      <td style="text-align:left">Built-in SPI port, with NO buffer, can only use short cable for connection.
        Not recommended.</td>
      <td style="text-align:left">Built-in contact</td>
    </tr>
    <tr>
      <td style="text-align:left">Debug</td>
      <td style="text-align:left">I/O and FMU Testing Port</td>
      <td style="text-align:left">Built-in port</td>
    </tr>
  </tbody>
</table>## Operating Conditions and Performance

| About | Description |
| :--- | :--- |
| POWER input voltage / rated input current | 4-5.7 V / 2.5 A; 0-20 V is safe for the system but it will not work |
| POWER rated output / input power | 14 W |
| USB port input voltage / rated input current | 4-5.7 V / 250 mA |
| Servo rail input voltage | 4-10.5V |
| Waterproof performance | Not waterproof. External waterproof protection is needed |
| Operation Temperature | -10°C / 55°C |

## Ports Standard and Definition

### Cube Orange Ports Standard

| Name | Type |
| :--- | :--- |
| Cube Orange Connector | DF17 80P |
| Cube Orange USB | USB 2.0 \(Micro - B 5 Pin\) |
| Cube Orange SD Card Type | microSD Card |

## Standard Carrier Board Ports Standard

| Ports | Connector Type |
| :--- | :--- |
| GPS1 | JST-GH 1.25 mm \(8-pin\) |
| GPS2 | JST-GH 1.25 mm \(6-pin\) |
| TELEM1 | JST-GH 1.25 mm \(6-pin\) |
| TELEM2 | JST-GH 1.25 mm \(6-pin\) |
| I2C2 | JST-GH 1.25 mm \(4-pin\) |
| USB | JST-GH 1.25 mm \(6-pin\) |
| CAN1 | JST-GH 1.25 mm \(4-pin\) |
| CAN2 | JST-GH 1.25 mm \(4-pin\) |
| POWER1 | Molex CLIK-Mate 2mm \(6-pin\) |
| POWER2 | Molex CLIK-Mate 2mm \(6-pin\) |
| ADC | JST-GH 1.25 mm \(3-pin\) |

## Cube Orange 80-pin DF17 Connector

| Pin \# | Name | I/O | Description |
| :--- | :--- | :--- | :--- |
| 1 | FMU\_SWDIO | I/O | FMU serial wire debug I/O |
| 2 | FMU\_LED\_AMBER | O | Boot error LED \(drive only, controlled by FET\) |
| 3 | FMU\_SWCLK | O | FMU serial wire debug clock |
| 4 | I2C\_2\_SDA | I/O | I2C Serial Data Tx/Rx |
| 5 | EXTERN\_CS | O | Chip select for external SPI \(NC, just for debugging\) |
| 6 | I2C\_2\_SCL | O | I2C Serial Clock Signal |
| 7 | FMU\_!RESET | I | Reset pin for the FMU |
| 8 | PROT\_SPARE\_1 |  | Spare |
| 9 | VDD\_SERVO\_IN | I | Power for last resort I/O failsafe |
| 10 | PROT\_SPARE\_2 |  | Spare |
| 11 | EXTERN\_DRDY | I | Interrupt pin for external SPI \(NC, just for debugging\) |
| 12 | SERIAL\_5\_RX | I | UART 5 RX \(Receive Data\) |
| 13 | GND |  | System GND |
| 14 | SERIAL\_5\_TX | O | UART 5 TX \(Transmit Data\) |
| 15 | GND |  | System GND |
| 16 | SERIAL\_4\_RX | I | UART 4 RX \(Receive Data\) |
| 17 | SAFETY |  | Safety button input |
| 18 | SERIAL\_4\_TX | O | UART 4 TX \(Transmit Data\) |
| 19 | VDD\_3V3\_SPEKTRUM\_EN | O | Enable for the Spektrum voltage regulator |
| 20 | SERIAL\_3\_RX | I | UART 3 RX \(Receive Data\) |
| 21 | PRESSURE\_SENS\_IN | AI | Analogue Signal port, for pressure sensor, Laser range finder, or Sonar |
| 22 | SERIAL\_3\_TX | O | UART 3 TX \(Transmit Data\) |
| 23 | AUX\_BATT\_VOLTAGE\_SENS | AI | Voltage sense for Aux battery input |
| 24 | ALARM | O | Buzzer PWM Signal |
| 25 | AUX\_BATT\_CURRENT\_SENS | AI | Current sense for Aux battery input |
|  |  |  |  |


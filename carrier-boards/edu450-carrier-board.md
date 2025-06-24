# EDU450 Carrier Board

<figure><img src="../.gitbook/assets/EDU450 Main-20230913-03.jpg" alt=""><figcaption></figcaption></figure>

## **Introduction**

The EDU-450 carrier board is a highly integrated component designed to fit seamlessly into the EDU-450 drone frame. Its primary purpose is to minimize the common wire and module entanglement issues that are often experienced during multi-rotor assembly.

The board offers a range of features, such as built-in power distribution, redundant power supplies for the autopilot, fail-over power selection built-in as a backup, a dedicated payload power regulator, etc.

It is primarily designed with geometric optimization for quadcopters, X8 configurations, and octocopters. It also provides connections for all the functions supported by The Cube. As a result, it can be easily integrated into any vehicle type that is compatible with The Cube.

## Features

* Up to 8-cell Lithium battery (36V)
* 100A continuous current
* Power and signal for ESCs
* 5V navigation light port
* Built-in power distribution unit (PDU)
* Built-in Hall effect voltage and current sensor
* Redundant power supplies for flight critical components
* Built-in 5V/10A, 7V/1.5A BEC
* Main power failure indicator lights
* Connectors for all functions of The Cube
* RS485 and SPI ports

## Power

The carrier board incorporates a built-in voltage and Hall current sensor. The main battery can be connected to the XT60 "MAIN PWR" port on the board, removing the need for an external power brick.

The power distribution system is rated to distribute 100A in total to the ESCs when under stagnant, room-temperature air conditions.

If the EDU450 carrier board is installed within an enclosure or used in challenging conditions, such as high temperatures, the current capacity rating needs to be reduced. For vehicles operating consistently at high currents, conduct a ground test first by using a temperature gun to assess the thermal performance.

The carrier board incorporates a built-in voltage and Hall current sensor. The main battery can be connected to the XT60 "MAIN PWR" port on the board, removing the need for an external power brick.

The power distribution system is rated to distribute 100A in total to the ESCs when under stagnant, room-temperature air conditions.

If the EDU450 carrier board is installed within an enclosure or used in challenging conditions, such as high temperatures, the current capacity rating needs to be reduced. For vehicles operating consistently at high currents, conduct a ground test first by using a temperature gun to assess the thermal performance.

To ensure the built-in sensors on the EDU-450 board accurately read the voltage and current numbers, complete the following steps:

1. Go to Mission Planner.
2. Go to **Config/Tuning** -> **Full Parameter List**.
3. Configure the following parameters to the values shown below.

| Parameter          | Value |
| ------------------ | ----- |
| BATT\_AMP\_OFFSET  | 0.25  |
| BATT\_AMP\_PERVOLT | 50    |
| BATT\_CURR\_PIN    | 3     |
| BATT\_MONITOR      | 4     |
| BATT\_VOLT\_MULT   | 12.05 |
| BATT\_VOLT\_PIN    | 2     |

## Specification

**Size**: 170 mm x 145 mm

**Weight**: 185g (with carbon fiber plate)

## **Port Interface**

### RS485 and SPI

The carrier board introduces enhancements such as anti-interference capabilities, high-sensitivity RS485, and a full-duplex, high-speed, synchronous serial communication SPI interface. This interface can be used to connect with Profi-LED or various industrial equipment, thereby offering increased communication support for the extended hardware and a wider range of applications.

### Customized Port for HerePro

The carrier board features a dedicated HerePro interface designed for data streamlining, debugging, and power supply functions. This single connection point enhances the overall integration and minimizes excess wiring.

### ADS-B External Antenna

The integrated ADS-B system is used to receive air traffic information. You can connect an external antenna to the standard SMA interface to extend the data reception range.&#x20;

<figure><img src="../.gitbook/assets/ADS_B ext antenna.png" alt=""><figcaption></figcaption></figure>

### HereLink Airunit Installation

{% hint style="info" %}
Connect the receiver to the PPM port, as shown in the figure below. The two SBUS ports are configured for output.
{% endhint %}

<figure><img src="../.gitbook/assets/EDU450 Main-20230914-04.jpg" alt=""><figcaption></figcaption></figure>

### 5V BEC

The board can supply 5V to the Main and AUX rails by bridging the following pad with solder.

<figure><img src="../.gitbook/assets/5V BEC BEC Output (2).png" alt=""><figcaption></figcaption></figure>

### ProfiLed

The board has four built-in ProfiLed interfaces for connecting and controlling navigation lights.

<figure><img src="../.gitbook/assets/ProfiLed comunication ports.png" alt=""><figcaption></figcaption></figure>

### ESC Port

The ESCs use the Amass-MR30 connector to power the motor and transmit the PWM signals.

The eight ESC ports are for multi-rotor UAVs with either four rotors or eight coaxial rotors.

<figure><img src="../.gitbook/assets/ESC.png" alt=""><figcaption></figcaption></figure>

## Pin Identification

### ProfiLED

<figure><img src="../.gitbook/assets/7pin-20230818-2.png" alt=""><figcaption></figcaption></figure>

| Pin Number | Name    |
| ---------- | ------- |
| 1          | 5V\_LED |
| 2          | CI      |
| 3          | DI      |
| 4          | CO      |
| 5          | DO      |
| 6          | GND     |
| 7          | GND     |

### SPI

<figure><img src="../.gitbook/assets/6pin -20230818-2.png" alt=""><figcaption></figcaption></figure>

| Pin Number | Name |
| ---------- | ---- |
| 1          | 5V   |
| 2          | MOSI |
| 3          | MISO |
| 4          | SCK  |
| 5          | CS   |
| 6          | GND  |

### 485

<figure><img src="../.gitbook/assets/4pin-20230818-2.png" alt=""><figcaption></figcaption></figure>

| Pin Number | Name |
| ---------- | ---- |
| 1          | Y    |
| 2          | Z    |
| 3          | B    |
| 4          | A    |

### I2C

<figure><img src="../.gitbook/assets/4pin-20230818-2-1692329616925-4.png" alt=""><figcaption></figcaption></figure>

| Pin Number  | Name        |
| ----------- | ----------- |
| 1           | VCC\_5V     |
| 2           | I2C\_2\_SCL |
| 3           | I2C\_2\_SDA |
| 4           | GND         |

### BUZZER

<figure><img src="../.gitbook/assets/EDU450 Port -20230817-1.png" alt=""><figcaption></figcaption></figure>

| Pin Number | Name   |
| ---------- | ------ |
| 1          | BUZZER |
| 2          | GND    |

### SBUS

<figure><img src="../.gitbook/assets/3pin-20230818-2.png" alt=""><figcaption></figcaption></figure>

| Pin Number | Name        |
| ---------- | ----------- |
| 1          | S.bus out 1 |
| 2          | S.bus out 2 |
| 3          | GND         |

### 5V (BEC POWER)

<figure><img src="../.gitbook/assets/6pin-20230818-2-1692329630451-7.png" alt=""><figcaption></figcaption></figure>

| Pin Number  | Name |
| ----------- | ---- |
| 1           | 5V   |
| 2           | 5V   |
| 3           | 5V   |
| 4           | GND  |
| 5           | GND  |
| 6           | GND  |

### CAN

<figure><img src="../.gitbook/assets/4pin-20230818-2-1692329636361-9.png" alt=""><figcaption></figcaption></figure>

| Pin Number | Name    |
| ---------- | ------- |
| 1          | VCC\_5V |
| 2          | CAN\_H  |
| 3          | CAN\_L  |
| 4          | GND     |

### Serial (Uart)

<figure><img src="../.gitbook/assets/6pin-20230818-2-1692329640608-11.png" alt=""><figcaption></figcaption></figure>

**SERIAL 1 | Telem 1**

| Pin Number | Name                |
| ---------- | ------------------- |
| 1          | VCC\_5V             |
| 2          | SERIAL\_1\_TX       |
| 3          | SERIAL\_1\_RX       |
| 4          | SERIAL\_1\_CTS (TX) |
| 5          | SERIAL\_1\_RTS (RX) |
| 6          | GND                 |

**SERIAL 2 |Telem 2**

| Pin Number | Name                |
| ---------- | ------------------- |
| 1          | VCC\_5V             |
| 2          | SERIAL\_2\_TX       |
| 3          | SERIAL\_2\_RX       |
| 4          | SERIAL\_2\_CTS (TX) |
| 5          | SERIAL\_2\_RTS (RX) |
| 6          | GND                 |

**SERIAL 3**

| Pin Number | Name                |
| ---------- | ------------------- |
| 1          | VCC\_5V             |
| 2          | SERIAL\_3\_TX       |
| 3          | SERIAL\_3\_RX       |
| 4          | SERIAL\_3\_CTS (TX) |
| 5          | SERIAL\_3\_RTS (RX) |
| 6          | GND                 |

**SERIAL 4**

| Pin Number | Name                |
| ---------- | ------------------- |
| 1          | VCC\_5V             |
| 2          | SERIAL\_4\_TX       |
| 3          | SERIAL\_4\_RX       |
| 4          | SERIAL\_4\_CTS (TX) |
| 5          | SERIAL\_4\_RTS (RX) |
| 6          | GND                 |

### ADC

<figure><img src="../.gitbook/assets/-20230817-1.png" alt=""><figcaption></figcaption></figure>

| Pin Number | Name              |
| ---------- | ----------------- |
| 1          | VDD\_5V\_Periph   |
| 2          | Pressure sense in |
| 3          | GND               |

### Debug

<figure><img src="../.gitbook/assets/EDU450 port-20230817-1.png" alt=""><figcaption></figcaption></figure>

**IO\_DEBUG**

| Pin Number | Name  |
| ---------- | ----- |
| 1          | GND   |
| 2          | SWCLK |
| 3          | SWDIO |
| 4          | NC    |
| 5          | NC    |
| 6          | 5V    |

**FMU\_DEBUG**

| Pin Number | Name  |
| ---------- | ----- |
| 1          | GND   |
| 2          | SWCLK |
| 3          | SWDIO |
| 4          | NC    |
| 5          | NC    |
| 6          | 5V    |

## Indication LED

### **Main Power Failure if LED is ON**

<figure><img src="../.gitbook/assets/Main power Failure.png" alt=""><figcaption></figcaption></figure>

The following Github link can be used to revise and update the EDU450 carrier board informatio&#x6E;**:** \
[**https://github.com/CubePilot/cubepilot-docs/blob/master/carrier-boards/edu450-carrier-board.md**](edu450-carrier-board.md)

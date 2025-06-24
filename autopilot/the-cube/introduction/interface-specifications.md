# Interface Specifications

This section covers the complete interface standard and the core mechanical, electrical, and external connection options of The Cube. Areas marked as LT (long term) need to be kept stable to isolate any autopilot revisions being made to the unmanned aerial vehicle (UAV).

## **Interface Standard**

### Connector Series

**Low density**: 0.1” over mould keyed servo connectors

> Cabling: AWG24, ribbon or round, iconic color scheme

**Stack**: [Hirose DF17, 80pos](http://www.hirose.co.jp/cataloge_hp/en_DF17_20130411.pdf) , 4 mm stacking height, 0.5 mm pitch, drop-proof

**High density**: [JST-GH](http://www.jst-mfg.com/product/detail_e.php?series=105\\) 1.25 mm

> Cabling: AWG28, ribbon, iconic colour scheme

**Power Module**: [Molex Clik-Mate](https://www.molex.com/molex/products/family/clikmate_wiretoboard_connectors) 2 mm for both main and backup power (connector is not on The Cube, but on the carrier board).

## **The Cube**

* Mechanica&#x6C;**:** 30x30 mm M1.6 mounting hole pattern, 35x35 mm footprint.
* 80 position DF17 connector: Carries all autopilot interface connections.
* No power management, which means power modules cannot be selected.
* &#x20;3.8 to 5.7V operation (absolute maximum ratings).
* 4.0 to 5.5V operation (compliant rating).

{% hint style="info" %}
Minimal electrical protection is provided to The Cube.
{% endhint %}

## **The Cube I/O**

Connecting Interfaces:

* Two I2C.
* Two CAN: CAN1 and CAN2.
* Four UART: TELEM1, TELEM2, GPS (I2C 1 embedded), SERIAL4(I2C 2 embedded).
* One Console: CONSOLE (SERIAL5).
* One HMI: USB extender.

## Serial Ports Parameters

### **Port Interface and Pin Label**

<figure><img src="../../../.gitbook/assets/Ports Sequence.svg" alt=""><figcaption></figcaption></figure>

### **Main Power - | Connector: POWER1**

| Pin Number | Name                | I/O | Voltage | Wire Colour | Description                   |
| ---------- | ------------------- | --- | ------- | ----------- | ----------------------------- |
| 1          | VDD\_5V\_BRICK      | IN  | 5 V     | RED/GRAY    | Supply To AP from Power Brick |
| 2          | VDD\_5V\_BRICK      | IN  | 5 V     | RED/GRAY    | Supply To AP from Power Brick |
| 3          | BATT\_CURRENT\_SENS | IN  | 3.3 V   | BLACK       | Battery Current Connecter     |
| 4          | BATT\_VOLTAGE\_SENS | IN  | 3.3 V   | BLACK       | Battery Voltage Connecter     |
| 5          | GND                 | -   | GND     | BLACK       | GND connection                |
| 6          | GND                 | -   | GND     | BLACK       | GND connection                |

### **Backup Power -  | Connector: POWER2**

| Pin Number | Name                     | I/O | Voltage | Wire Colour | Description                   |
| ---------- | ------------------------ | --- | ------- | ----------- | ----------------------------- |
| 1          | VDD\_5V\_BRICK           | IN  | 5 V     | RED/GRAY    | Supply To AP from Power Brick |
| 2          | VDD\_5V\_BRICK           | IN  | 5 V     | RED/GRAY    | Supply To AP from Power Brick |
| 3          | AUX\_BATT\_CURRENT\_SENS | IN  | 3.3 V   | BLACK       | Aux Battery Current Connecter |
| 4          | AUX\_BATT\_VOLTAGE\_SENS | IN  | 3.3 V   | BLACK       | Aux Battery Voltage Connecter |
| 5          | GND                      | -   | GND     | BLACK       | GND connection                |
| 6          | GND                      | -   | GND     | BLACK       | GND connection                |

### **I2C - 4 pos (one fitted as a standalone, one as an old internal) | Connector: I2C2**

| Pin Number | Name        | I/O    | Voltage         | Wire Colour | Description                  |
| ---------- | ----------- | ------ | --------------- | ----------- | ---------------------------- |
| 1          | VCC\_5V     | OUT    | 5 V             | RED/GRAY    | Supply to peripheral from AP |
| 2          | I2C\_2\_SCL | IN/OUT | 3.3 V (PULLUPS) | BLUE/BLACK  | SCL, Pull-up on AP           |
| 3          | I2C\_2\_SDA | IN/OUT | 3.3 V (PULLUPS) | GREEN/BLACK | SDA, Pull-up on AP           |
| 4          | GND         |        | GND             | BLACK       | GND connection               |

### **CAN (2 fitted) | Connector: CAN1, CAN2**

| Pin Number | Name    | I/O    | Voltage | Wire Colour  | Description                  |
| ---------- | ------- | ------ | ------- | ------------ | ---------------------------- |
| 1          | VCC\_5V | OUT    | 5 V     | RED/GRAY     | Supply to peripheral from AP |
| 2          | CAN\_H  | IN/OUT | 12 V    | YELLOW/BLACK | CAN High                     |
| 3          | CAN\_L  | IN/OUT | 12 V    | GREEN/BLACK  | CAN Low                      |
| 4          | GND     | -      | GND     | BLACK        | GND connection               |

### **UART GENERIC (autopilot side) | Connector: TELEM1, TELEM2**

| Pin Number | Name          | I/O | Voltage           | Wire Colour  | Description                  |
| ---------- | ------------- | --- | ----------------- | ------------ | ---------------------------- |
| 1          | VCC\_5V       | OUT | 5 V               | RED/GRAY     | Supply to peripheral from AP |
| 2          | MCU\_TX       | OUT | 3.3 V - 5.0 V TTL | YELLOW/BLACK | TX of AP                     |
| 3          | MCU\_RX       | IN  | 3.3 V - 5.0 V TTL | GREEN/BLACK  | RX of AP                     |
| 4          | MCU\_CTS (TX) | OUT | 3.3 V - 5.0 V TTL | GRAY/BLACK   | CTS (Clear To Send)          |
| 5          | MCU\_RTS (RX) | IN  | 3.3 V - 5.0 V TTL | GRAY/BLACK   | RTS (Request To Send)        |
| 6          | GND           | -   | GND               | BLACK        | GND connection               |

### **UART GPS (autopilot side, I2C is the original “External” bus), UART 3 | Connector: GPS1**

| Pin Number | Name                 | I/O    | Voltage           | Wire Colour | Description                    |
| ---------- | -------------------- | ------ | ----------------- | ----------- | ------------------------------ |
| 1          | VCC\_5V              | IN     | 5 V               | RED         | Supply to GPS from AP          |
| 2          | GPS\_TX              | IN     | 3.3 V - 5.0 V TTL | BLACK       | TX of AP                       |
| 3          | GPS\_RX              | OUT    | 3.3 V - 5.0 V TTL | BLACK       | RX of AP                       |
| 4          | SCL                  | IN     | 3.3 V             | BLACK       | I2C 1 SCL                      |
| 5          | SDA                  | IN/OUT | 3.3 V             | BLACK       | I2C 1 SDA                      |
| 6          | BUTTON               | OUT    | GND               | BLACK       | Signal shorted to GND on press |
| 7          | IO\_LED\_SAFET\_PROT | OUT    | GND               | BLACK       | LED Driver For Safety Button   |
| 8          | GND                  | -      | GND               | BLACK       | GND connection                 |

### **UART 4 (I2C2, the original “Internal” bus) | Port: GPS2**

| Pin Number | Name    | I/O | Voltage           | Wire Colour  | Description           |
| ---------- | ------- | --- | ----------------- | ------------ | --------------------- |
| 1          | VCC\_5V | OUT | 5 V               | RED/GRAY     | Supply to GPS from AP |
| 2          | MCU\_TX | OUT | 3.3 V - 5.0 V TTL | YELLOW/BLACK | TX of AP              |
| 3          | MCU\_RX | IN  | 3.3 V - 5.0 V TTL | GREEN/BLACK  | RX of AP              |
| 4          | SCL     | OUT | 3.3 V - 5.0 V     | GRAY/BLACK   | I2C 2 SCL             |
| 5          | SDA     | IN  | 3.3 V - 5.0 V     | GRAY/BLACK   | I2C 2 SDA             |
| 6          | GND     | -   | GND               | BLACK        | GND connection        |

### **UART 5 (Debug), S.Bus out - FR-SKY TELEM or Debug | Port: CONS SBUSo**

| Pin Number | Name       | I/O | Voltage           | Wire Colour | Description                   |
| ---------- | ---------- | --- | ----------------- | ----------- | ----------------------------- |
| 1          | S.Bus\_Out | OUT |                   |             | S.Bus Signal Output, TX of AP |
| 2          | MCU\_TX    | OUT | 3.3 V - 5.0 V TTL |             | TX of AP                      |
| 3          | VDD\_SERVO | OUT | Servo Voltage     |             | Servo rail voltage            |
| 4          | MCU\_RX    | IN  | 3.3 V - 5.0 V TTL |             | RX of AP                      |
| 5          | GND        | -   | GND               |             | GND connection                |
| 6          | GND        | -   | GND               |             | GND connection                |

### **Debug (New Standard Debug) (Digikey PN for housing SM06B-SURS-TF(LF)(SN)-ND)**

#### **IO DEBUG**

| Pin Number | Name         | I/O | Voltage           | Wire Color | Description           |
| ---------- | ------------ | --- | ----------------- | ---------- | --------------------- |
| 1          | VDD 5V PEIPH | OUT | 5 V               |            | 5V                    |
| 2          | IO\_TX       | OUT | 3.3 V - 5.0 V TTL |            | TX of AP IO\_uart1 TX |
| 3          | IO\_RX       | IN  | 3.3V - 5.0 V TTL  |            | RX of AP IO\_uart1 RX |
| 4          | IO-SWDIO     | I/O | 3.3 V - 5.0 V TTL |            | Serial wire debug I/O |
| 5          | IO-SWCLK     | I/O | 3.3 V - 5.0 V TTL |            | Serial wire Clock     |
| 6          | GND          | OUT | GND               |            | GND connection        |

#### **FMU Debug**

| Pin Number | Name               | I/O | Voltage           | Wire Color | Description            |
| ---------- | ------------------ | --- | ----------------- | ---------- | ---------------------- |
| 1          | VDD 5V PEIPH       | OUT | 5 V               |            | 5V                     |
| 2          | FMU\_TX (SERIAL 5) | OUT | 3.3 V - 5.0 V TTL |            | TX of AP FMU\_uart5 TX |
| 3          | FMU\_RX (SERIAL 5) | IN  | 3.3V - 5.0 V TTL  |            | RX of AP FMU\_uart5 RX |
| 4          | FMU-SWDIO          | I/O | 3.3 V - 5.0 V TTL |            | Serial wire debug I/O  |
| 5          | FMU-SWCLK          | I/O | 3.3 V - 5.0 V TTL |            | Serial wire Clock      |
| 6          | GND                | OUT | GND               |            | GND connection         |

#### **Analog | Port:`ADC`**

| Pin Number | Name              | I/) | Voltage | Wire Color | Description    |
| ---------- | ----------------- | --- | ------- | ---------- | -------------- |
| 1          | VDD\_5V\_Periph   | OUT |         |            |                |
| 2          | Pressure sense in | IN  |         |            |                |
| 3          | GND               | -   |         |            | GND connection |

#### **IO USART 1/DSM/Spektrum | Port:`SPKT`**

| Pin Number | Name                          | I/O | Voltage | Wire Colour | Description              |
| ---------- | ----------------------------- | --- | ------- | ----------- | ------------------------ |
| 1          | IO\_USART1\_RX\_SPECTRUM\_DSM | IN  |         |             | IO USART 1 RX, DSM INPUT |
| 2          | GND                           | -   | GND     |             | GND                      |
| 3          | VDD\_3V3\_Spektrum            | OUT | 3.3 V   |             | private Power Supply     |

#### **HMI (Buzzer, USB, LEDs) | Port:`USB`**

| Pin # | Name            | I/O    | Voltage         | Wire Colour | Description                   |
| ----- | --------------- | ------ | --------------- | ----------- | ----------------------------- |
| 1     | V BUS           | OUT    | 5 V             | RED/GRAY    | USB V BUS                     |
| 2     | OTG\_DP1        | IN/OUT | 3.3 V           | GREEN/BLACK | USB Data Positive (D+)        |
| 3     | OTG\_DM1        | IN/OUT | 3.3 V           | RED/BLACK   | USB Data Minus (D-)           |
| 4     | GND             | -      | GND             | BLACK       | GND                           |
| 5     | BUZZER\_OUT     | OUT    | Battery Voltage | GRAY/BLACK  | VBAT (8.4 - 42 V)             |
| 6     | FMU\_LED\_AMBER | OUT    |                 | BLACK       | Boot / Error LED (FW updates) |

#### **Back Edge (can be rearranged in accordance with PCB layout) | Port：`RCIN`** **`MAIN OUT`** **`AUX OUT`**

#### **SERVO HEADER (0.1”, 1/1/15 power layout)**

| Pin Number | Name            | I/O    | Voltage                              | Wire Colour | Description        |
| ---------- | --------------- | ------ | ------------------------------------ | ----------- | ------------------ |
| S - 1      | FMU\_CH1\_PROT  | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 2      | FMU\_CH2\_PROT  | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 3      | FMU\_CH3\_PROT  | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 4      | FMU\_CH4\_PROT  | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 5      | FMU\_CH5\_PROT  | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 6      | FMU\_CH6\_PROT  | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 7      | IO\_CH1\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 8      | IO\_CH2\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 9      | IO\_CH3\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 10     | IO\_CH4\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 11     | IO\_CH5\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 12     | IO\_CH6\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 13     | IO\_CH7\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 14     | IO\_CH8\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power |             | PWM Signal         |
| S - 15     | PPM\_SBUS\_PROT | IN/OUT | 3.3 V / 4.5 V Powered                |             | PPM / S.Bus Signal |

#### **The Cube 80-pin DF17 Connector (long term standard)**

| Pin Number | Name                          | I/O | Description                                                             |
| ---------- | ----------------------------- | --- | ----------------------------------------------------------------------- |
| 1          | FMU\_SWDIO                    | I/O | FMU serial wire debug I/O                                               |
| 2          | FMU\_LED\_AMBER               | O   | Boot error LED (drive only, controlled by FET)                          |
| 3          | FMU\_SWCLK                    | O   | FMU serial wire debug clock                                             |
| 4          | I2C\_2\_SDA                   | I/O | I2C Serial Data Tx/Rx                                                   |
| 5          | EXTERN\_CS                    | O   | Chip select for external SPI (NC, just for debugging)                   |
| 6          | I2C\_2\_SCL                   | O   | I2C Serial Clock Signal                                                 |
| 7          | FMU\_!RESET                   | I   | Reset pin for the FMU                                                   |
| 8          | PROT\_SPARE\_1                |     | Spare                                                                   |
| 9          | VDD\_SERVO\_IN                | I   | Power for last resort I/O failsafe                                      |
| 10         | PROT\_SPARE\_2                |     | Spare                                                                   |
| 11         | EXTERN\_DRDY                  | I   | Interrupt pin for external SPI (NC, just for debugging)                 |
| 12         | SERIAL\_5\_RX                 | I   | UART 5 RX (Receive Data)                                                |
| 13         | GND                           |     | System GND                                                              |
| 14         | SERIAL\_5\_TX                 | O   | UART 5 TX (Transmit Data)                                               |
| 15         | GND                           |     | System GND                                                              |
| 16         | SERIAL\_4\_RX                 | I   | UART 4 RX (Receive Data)                                                |
| 17         | SAFETY                        |     | Safety button input                                                     |
| 18         | SERIAL\_4\_TX                 | O   | UART 4 TX (Transmit Data)                                               |
| 19         | VDD\_3V3\_SPEKTRUM\_EN        | O   | Enable for the Spektrum voltage regulator                               |
| 20         | SERIAL\_3\_RX                 | I   | UART 3 RX (Receive Data)                                                |
| 21         | PRESSURE\_SENS\_IN            | AI  | Analogue Signal port, for pressure sensor, Laser range finder, or Sonar |
| 22         | SERIAL\_3\_TX                 | O   | UART 3 TX (Transmit Data)                                               |
| 23         | AUX\_BATT\_VOLTAGE\_SENS      | AI  | Voltage sense for Aux battery input                                     |
| 24         | ALARM                         | O   | Buzzer PWM Signal                                                       |
| 25         | AUX\_BATT\_CURRENT\_SENS      | AI  | Current sense for Aux battery input                                     |
| 26         | IO\_VDD\_3V3                  | I   | IO chip power, pinned through for debug                                 |
| 27         | VDD\_5V\_PERIPH\_EN           | O   | Enable voltage supply for Peripherals                                   |
| 28         | IO\_LED\_SAFET\_PROT          | O   | IO-LED\_SAFETY (safety LED) pinned out for IRIS                         |
| 29         | VBUS                          | I   | USB VBus (VDD)                                                          |
| 30         | SERIAL\_2\_RTS                |     | UART 2 RTS (Request To Send)                                            |
| 31         | OTG\_DP1                      | I/O | USB Data+ (D)                                                           |
| 32         | SERIAL\_2\_CTS                |     | UART 2 CTS (Clear To Send)                                              |
| 33         | OTG\_DM1                      | I/O | USB Data- (M)                                                           |
| 34         | SERIAL\_2\_RX                 | I   | UART 2 RX (Receive Data)                                                |
| 35         | I2C\_1\_SDA                   | I/O | I2C Serial Data Tx/Rx                                                   |
| 36         | SERIAL\_2\_TX                 | O   | UART 2 TX (Transmit Data)                                               |
| 37         | I2C\_1\_SCL                   | O   | I2C Serial Clock Signal                                                 |
| 38         | SERIAL\_1\_RX                 | I   | UART 1 RX (Receive Data)                                                |
| 39         | CAN\_L\_2                     | I/O | FMU CAN bus Low Signal Driver                                           |
| 40         | SERIAL\_1\_TX                 | O   | UART 1 TX (Transmit Data)                                               |
| 41         | CAN\_H\_2                     | I/O | FMU CAN bus High Signal Driver                                          |
| 42         | SERIAL\_1\_RTS                |     | UART 1 RTS (Request To Send)                                            |
| 43         | VDD\_5V\_PERIPH\_OC           | I   | Error state message  from Peripheral power supply                       |
| 44         | SERIAL\_1\_CTS                |     | UART 1 CTS (Clear To Send)                                              |
| 45         | VDD\_5V\_HIPOWER\_OC          | I   | Error state message  from High power Peripheral power supply            |
| 46         | IO\_USART\_1\_TX              | O   | I/O USART 1 TX                                                          |
| 47         | BATT\_VOLTAGE\_SENS\_PROT     | AI  | Voltage sense from main battery                                         |
| 48         | IO\_USART1\_RX\_SPECTRUM\_DSM | O   | Signal from Spectrum receiver                                           |
| 49         | BATT\_CURRENT\_SENS\_PROT     | AI  | Current sense from main battery                                         |
| 50         | FMU\_CH1\_PROT                | O   | FMU PWM output channel 1                                                |
| 51         | SPI\_EXT\_MOSI                | O   | External SPI, for debug only                                            |
| 52         | FMU\_CH2\_PROT                | O   | FMU PWM output channel 2                                                |
| 53         | VDD\_SERVO                    | I   | VDD\_Servo, for monitoring servo bus                                    |
| 54         | FMU\_CH3\_PROT                | O   | FMU PWM Output Channel 3                                                |
| 55         | VDD\_BRICK\_VALID             | I   | Main Power valid signal                                                 |
| 56         | FMU\_CH4\_PROT                | O   | FMU PWM Output Channel 4                                                |
| 57         | VDD\_BACKUP\_VALID            | I   | Backup Power valid Signal                                               |
| 58         | FMU\_CH5\_PROT                | O   | FMU PWM Output Channel 5                                                |
| 59         | VBUS\_VALID                   | I   | USB bus valid signal                                                    |
| 60         | FMU\_CH6\_PROT                | O   | FMU PWM Output Channel 6                                                |
| 61         | VDD\_5V\_IN\_PROT             | I   | Main power (5V) into FMU from power selection                           |
| 62         | PPM\_SBUS\_PROT               | I   | PPM / S.Bus Signal Input                                                |
| 63         | VDD\_5V\_IN\_PROT             | I   | Main power (5V) into FMU from power selection                           |
| 64         | S.BUS\_OUT                    | O   | S.Bus Signal Output                                                     |
| 65         | IO\_VDD\_5V5                  | O   | IO VDD 5.5 V                                                            |
| 66         | IO\_CH8\_PROT                 | O   | I/O PWM Output Channel 8                                                |
| 67         | SPI\_EXT\_MISO                | I   | External SPI, for Debug only                                            |
| 68         | IO\_CH7\_PROT                 | O   | I/O PWM Channel 7                                                       |
| 69         | IO\_SWDIO                     | I/O | I/O serial wire debug                                                   |
| 70         | IO\_CH6\_PROT                 | O   | I/O PWM Output Channel 6                                                |
| 71         | IO\_SWCLK                     | O   | I/O Serial Wire Debug Clock                                             |
| 72         | IO\_CH5\_PROT                 | O   | I/O PWM Output Channel 5                                                |
| 73         | SPI\_EXT\_SCK                 | O   | External SPI, for Debug only                                            |
| 74         | IO\_CH4\_PROT                 | O   | I/O PWM Output Channel 4                                                |
| 75         | IO\_!RESET                    | I   | I/O Reset Pin                                                           |
| 76         | IO\_CH3\_PROT                 | O   | I/O PWM Output Channel 3                                                |
| 77         | CAN\_L\_1                     | I/O | FMU CAN bus Low Signal Driver                                           |
| 78         | IO\_CH2\_PROT                 | O   | I/O PWM Output Channel 2                                                |
| 79         | CAN\_H\_1                     | I/O | FMU CAN bus High Signal Driver                                          |
| 80         | IO\_CH1\_PROT                 | O   | I/O PWM Output Channel 1                                                |

## Differences between the Colored Cubes

<table data-header-hidden><thead><tr><th width="277">The Cube Series</th><th>Cube Orange+</th><th>Cube Orange</th><th>Cube Blue H7</th><th>Cube Purple H7</th><th>Cube Yellow</th><th>Cube Black+</th><th>Cube Black</th><th>Cube Green</th><th>Cube Blue</th><th>Cube Purple F4</th><th data-hidden></th></tr></thead><tbody><tr><td><strong>The Cube</strong></td><td><mark style="color:orange;"><strong>Cube Orange+</strong></mark></td><td><mark style="color:orange;"><strong>Cube Orange</strong></mark></td><td><mark style="color:blue;"><strong>Cube Blue H7</strong></mark></td><td><mark style="color:purple;"><strong>Cube Purple H7</strong></mark></td><td><mark style="color:yellow;"><strong>Cube Yellow</strong></mark></td><td><strong>Cube Black+</strong></td><td><strong>Cube Black</strong></td><td><mark style="color:green;"><strong>Cube Green</strong></mark></td><td><mark style="color:blue;"><strong>Cube Blue</strong></mark></td><td><mark style="color:purple;"><strong>Cube Purple F4</strong></mark></td><td></td></tr><tr><td>Processor</td><td>STM32H757</td><td>STM32H753</td><td>STM32H753</td><td>STM32H753</td><td>STM32F777</td><td>STM32F427 V3</td><td>STM32F427 V3</td><td>STM32F427 V3</td><td>STM32F427 V3</td><td>STM32F427 V3</td><td></td></tr><tr><td>Remote Signal</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td>PPM/SBUS/DSM</td><td></td></tr><tr><td>I/O PWN Voltage</td><td>3.3V/5V software selectable</td><td>3.3V/5V software selectable</td><td>3.3V/5V software selectable</td><td>3.3V/5V software selectable</td><td>3.3V/5V software selectable</td><td>3.3V</td><td>3.3V</td><td>5.4v</td><td>3.3V</td><td>3.3V</td><td></td></tr><tr><td>Redundancy</td><td>Triple Redundancy</td><td>Triple Redundancy</td><td>Triple Redundancy</td><td>N/A</td><td>Triple Redundancy</td><td>Triple Redundancy</td><td>Triple Redundancy</td><td>Triple Redundancy</td><td>Triple Redundancy</td><td>N/A</td><td></td></tr><tr><td>Isolation System</td><td>Y</td><td>Y</td><td>Y</td><td>N</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td><td>N</td><td></td></tr><tr><td>Temp Regulator</td><td>Y</td><td>Y</td><td>Y</td><td>N</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td><td>N</td><td></td></tr><tr><td>Number of Accelerometers</td><td>Three</td><td>Three</td><td>3</td><td>1</td><td>3</td><td>3</td><td>3</td><td>3</td><td>3</td><td>1</td><td></td></tr><tr><td>Number of Gyroscopes</td><td>Three</td><td>Three</td><td>3</td><td>1</td><td>3</td><td>3</td><td>3</td><td>3</td><td>3</td><td>1</td><td></td></tr><tr><td>Number of Magnetometers</td><td>One</td><td>One</td><td>1</td><td>N/A</td><td>1</td><td>2</td><td>3</td><td>3</td><td>3</td><td>1</td><td></td></tr><tr><td>Number of Barometers</td><td>Two</td><td>Two</td><td>2</td><td>1</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>1</td><td></td></tr><tr><td>Manufacturing Origin</td><td>Taiwan</td><td>Taiwan</td><td>U.S.A</td><td>Taiwan</td><td>Taiwan</td><td>Taiwan</td><td>Taiwan</td><td>Taiwan</td><td>U.S.A</td><td>Taiwan</td><td></td></tr><tr><td>Product Lifecycle</td><td>Available</td><td>Available</td><td>Available</td><td>Available</td><td>Available</td><td><p>EOL </p><p>Use <mark style="color:orange;"><strong>Cube Orange</strong></mark></p></td><td><p>EOL </p><p>Use <mark style="color:orange;"><strong>Cube Orange</strong></mark></p></td><td><p>EOL </p><p>Use <mark style="color:orange;"><strong>Cube Orange</strong></mark></p></td><td><p>EOL </p><p>Use <mark style="color:blue;"><strong>Cube Blue H7</strong></mark></p></td><td><p>EOL </p><p>Use <mark style="color:purple;"><strong>Cube Purple H7</strong></mark></p></td><td></td></tr></tbody></table>

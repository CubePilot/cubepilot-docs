# Mini Carrier Board

## Working Conditions and Performance

| About                                        | Description                                                      |
| -------------------------------------------- | ---------------------------------------------------------------- |
| POWER input voltage / rated input current    | 4-5.7V / 2.5A; 0-20V is safe for the system but it will not work |
| POWER rated output / input power             | 14 W                                                             |
| USB port input voltage / rated input current | 4-5.7V / 250mA                                                   |
| Servo rail input voltage                     | 4-10.5V                                                          |
| Waterproof                                   | Not waterproof. External waterproof protection is needed         |
| Working temperature                          | -10°C / 55°C                                                     |

## Size and Specifications

| Type                                       | Description                       |
| ------------------------------------------ | --------------------------------- |
| Mini Carrier Board Size / Chassis Material | 47.5x38.5x17.8 (mm) / ABS Molding |
|                                            |                                   |

## Interfaces and Definitions

Pinout

![](<../.gitbook/assets/Purple Cube and Mini Carrier Board -1.jpg>)

Red dot on plug side denotes pin 1

![](<../.gitbook/assets/Purple Cube and Mini Carrier Board -2.jpg>)

![](<../.gitbook/assets/Purple Cube and Mini Carrier Board -3.jpg>)

![](<../.gitbook/assets/Purple Cube and Mini Carrier Board -4.jpg>)

![](<../.gitbook/assets/Purple Cube and Mini Carrier Board -5.jpg>)

![](<../.gitbook/assets/Purple Cube and Mini Carrier Board -6.jpg>)

## Mini Carrier Board Interface Model

| Ports  | Corresponding Connecter Model |
| ------ | ----------------------------- |
| GPS1   | JST-GH 1.25 mm (8-pin)        |
| GPS2   | JST-GH 1.25 mm (6-pin)        |
| TELEM1 | JST-GH 1.25 mm (6-pin)        |
| TELEM2 | JST-GH 1.25 mm (6-pin)        |
| I2C    | JST-GH 1.25 mm (4-pin)        |
| CAN2   | JST-GH 1.25 mm (4-pin)        |
| POWER1 | Molex CLIK-Mate 2 mm (6-pin)  |
| POWER2 | Molex CLIK-Mate 2 mm (6-pin)  |
| BUZZER | DF13 1.25 mm (2-pin)          |

## Mini Cube 80-pin DF17 Connector Assignments (same as the Cube Black)

| Pin # | Name                          | Direction | Description                                                         |
| ----- | ----------------------------- | --------- | ------------------------------------------------------------------- |
| 1     | FMU\_SWDIO                    | I/O       | FMU serial wire debug I/O                                           |
| 2     | FMU\_LED\_AMBER               | O         | Boot error LED (drive only, controlled by FET)                      |
| 3     | FMU\_SWCLK                    | O         | FMU serial wire debug clock                                         |
| 4     | I2C\_2\_SDA                   | I/O       | I2C data I/O                                                        |
| 5     | EXTERN\_CS                    | O         | Chip select for external SPI (NC, just for debugging)               |
| 6     | I2C\_2\_SCL                   | O         | I2C clock                                                           |
| 7     | FMU\_!RESET                   | I         | Reset pin for the FMU                                               |
| 8     | PROT\_SPARE\_1                |           | Spare                                                               |
| 9     | VDD\_SERVO\_IN                | I         | Power for last resort I/O failsafe                                  |
| 10    | PROT\_SPARE\_2                |           | Spare                                                               |
| 11    | EXTERN\_DRDY                  | I         | Interrupt pin for external SPI (NC, just for debugging)             |
| 12    | SERIAL\_5\_RX                 | I         | UART 5 RX (Receive Data)                                            |
| 13    | GND                           |           | System GND                                                          |
| 14    | SERIAL\_5\_TX                 | O         | UART 5 TX (Transmit Data)                                           |
| 15    | GND                           |           | System GND                                                          |
| 16    | SERIAL\_4\_RX                 | I         | UART 4 RX (Receive Data)                                            |
| 17    | SAFETY                        |           | Safety button input                                                 |
| 18    | SERIAL\_4\_TX                 | O         | UART 4 TX (Transmit Data)                                           |
| 19    | VDD\_3V3\_SPEKTRUM\_EN        | O         | Enable for the spectrum voltage supply                              |
| 20    | SERIAL\_3\_RX                 | I         | UART 3 RX (Receive Data)                                            |
| 21    | PRESSURE\_SENS\_IN            | AI        | Analogue port, for pressure sensor, or Laser range finder, or Sonar |
| 22    | SERIAL\_3\_TX                 | O         | UART 3 TX (Transmit Data)                                           |
| 23    | AUX\_BATT\_VOLTAGE\_SENS      | AI        | Voltage sense for Aux battery input                                 |
| 24    | ALARM                         | O         | Buzzer PWM signal                                                   |
| 25    | AUX\_BATT\_CURRENT\_SENS      | AI        | Current sense for Aux battery input                                 |
| 26    | IO\_VDD\_3V3                  | I         | IO chip power, pinned through for debugging                         |
| 27    | VDD\_5V\_PERIPH\_EN           | O         | Enable voltage supply for Peripherals                               |
| 28    | IO\_LED\_SAFET\_PROT          | O         | IO-LED\_SAFETY(safety LED) pinned out for IRIS                      |
| 29    | VBUS                          | I         | USB VBus (VDD)                                                      |
| 30    | SERIAL\_2\_RTS                |           | UART 2 RTS (Request To Send)                                        |
| 31    | OTG\_DP1                      | I/O       | USB Data+                                                           |
| 32    | SERIAL\_2\_CTS                |           | UART 2 CTS (Clear To Send)                                          |
| 33    | OTG\_DM1                      | I/O       | USB Data-                                                           |
| 34    | SERIAL\_2\_RX                 | I         | UART 2 RX (Receive Data)                                            |
| 35    | I2C\_1\_SDA                   | I/O       | I2C data I/O                                                        |
| 36    | SERIAL\_2\_TX                 | O         | UART 2 TX (Transmit Data)                                           |
| 37    | I2C\_1\_SCL                   | O         | I2C clock                                                           |
| 38    | SERIAL\_1\_RX                 | I         | UART 1 RX (Receive Data)                                            |
| 39    | CAN\_L\_2                     | I/O       | FMU CAN bus Low signal driver                                       |
| 40    | SERIAL\_1\_TX                 | O         | UART 1 TX (Transmit Data)                                           |
| 41    | CAN\_H\_2                     | I/O       | FMU CAN bus High signal driver                                      |
| 42    | SERIAL\_1\_RTS                |           | UART 1 RTS (Request To Send)                                        |
| 43    | VDD\_5V\_PERIPH\_OC           | I         | Error state message from peripheral power supply                    |
| 44    | SERIAL\_1\_CTS                |           | UART 1 CTS (Clear To Send)                                          |
| 45    | VDD\_5V\_HIPOWER\_OC          | I         | Error state message from High power peripheral power supply         |
| 46    | IO\_USART\_1\_TX              | O         | I/O USART 1 TX                                                      |
| 47    | BATT\_VOLTAGE\_SENS\_PROT     | AI        | Voltage sense from main battery                                     |
| 48    | IO\_USART1\_RX\_SPECTRUM\_DSM | O         | Signal from Spectrum receiver                                       |
| 49    | BATT\_CURRENT\_SENS\_PROT     | AI        | Current sense from main battery                                     |
| 50    | FMU\_CH1\_PROT                | O         | FMU PWM output channel 1                                            |
| 51    | SPI\_EXT\_MOSI                | O         | External SPI, for debug only                                        |
| 52    | FMU\_CH2\_PROT                | O         | FMU PWM output channel 2                                            |
| 53    | VDD\_SERVO                    | I         | VDD\_Servo, for monitoring servo bus                                |
| 54    | FMU\_CH3\_PROT                | O         | FMU PWM output channel 3                                            |
| 55    | VDD\_BRICK\_VALID             | I         | Main power valid signal                                             |
| 56    | FMU\_CH4\_PROT                | O         | FMU PWM output channel 4                                            |
| 57    | VDD\_BACKUP\_VALID            | I         | Backup power valid signal                                           |
| 58    | FMU\_CH5\_PROT                | O         | FMU PWM output channel 5                                            |
| 59    | VBUS\_VALID                   | I         | USB bus valid signal                                                |
| 60    | FMU\_CH6\_PROT                | O         | FMU PWM output channel 6                                            |
| 61    | VDD\_5V\_IN\_PROT             | I         | Main power (5V) into FMU from power selection                       |
| 62    | PPM\_SBUS\_PROT               | I         | PPM / S.Bus signal input                                            |
| 63    | VDD\_5V\_IN\_PROT             | I         | Main power (5V) into FMU from power selection                       |
| 64    | S.BUS\_OUT                    | O         | S.Bus signal output                                                 |
| 65    | IO\_VDD\_5V5                  | O         | IO VDD 5.5 V                                                        |
| 66    | IO\_CH8\_PROT                 | O         | I/O PWM output channel 8                                            |
| 67    | SPI\_EXT\_MISO                | I         | External SPI, for debug only                                        |
| 68    | IO\_CH7\_PROT                 | O         | I/O PWM output channel 7                                            |
| 69    | IO\_SWDIO                     | I/O       | I/O serial wire debug                                               |
| 70    | IO\_CH6\_PROT                 | O         | I/O PWM output channel 6                                            |
| 71    | IO\_SWCLK                     | O         | I/O serial wire debug clock                                         |
| 72    | IO\_CH5\_PROT                 | O         | I/O PWM output channel 5                                            |
| 73    | SPI\_EXT\_SCK                 | O         | External SPI, for debug only                                        |
| 74    | IO\_CH4\_PROT                 | O         | I/O PWM output channel 4                                            |
| 75    | IO\_!RESET                    | I         | I/O reset pin                                                       |
| 76    | IO\_CH3\_PROT                 | O         | I/O PWM output channel 3                                            |
| 77    | CAN\_L\_1                     | I/O       | FMU CAN bus Low signal driver                                       |
| 78    | IO\_CH2\_PROT                 | O         | I/O PWM output channel 2                                            |
| 79    | CAN\_H\_1                     | I/O       | FMU CAN bus High signal driver                                      |
| 80    | IO\_CH1\_PROT                 | O         | I/O PWM output channel 1                                            |

## Serial Ports Parameter and power distribution

SERIAL 1 / UART 1 | Connector： TELEM1

| Pin # | Name                | Direction | Voltage           | Wire Color   | Caption                      |
| ----- | ------------------- | --------- | ----------------- | ------------ | ---------------------------- |
| 1     | VCC\_5V             | OUT       | 5 V               | RED/GRAY     | VCC                          |
| 2     | SERIAL\_1\_TX       | OUT       | 3.3 V - 5.0 V TTL | YELLOW/BLACK | UART 1 TX (Transmit Data)    |
| 3     | SERIAL\_1\_RX       | IN        | 3.3 V - 5.0 V TTL | GREEN/BLACK  | UART 1 RX (Receive Data)     |
| 4     | SERIAL\_1\_CTS (TX) | OUT       | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 1 CTS (Clear To Send)   |
| 5     | SERIAL\_1\_RTS (RX) | IN        | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 1 RTS (Request To Send) |
| 6     | GND                 |           | GND               | BLACK        | GND                          |

## SERIAL 2 / UART 2 | Connector： TELEM2

| Pin # | Name                | Direction | Voltage           | Wire Color   | Caption                      |
| ----- | ------------------- | --------- | ----------------- | ------------ | ---------------------------- |
| 1     | VCC\_5V             | OUT       | 5 V               | RED/GRAY     | VCC                          |
| 2     | SERIAL\_2\_TX       | OUT       | 3.3 V - 5.0 V TTL | YELLOW/BLACK | UART 2 TX (Transmit Data)    |
| 3     | SERIAL\_2\_RX       | IN        | 3.3 V - 5.0 V TTL | GREEN/BLACK  | UART 2 RX (Receive Data)     |
| 4     | SERIAL\_2\_CTS (TX) | OUT       | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 2 CTS (Clear To Send)   |
| 5     | SERIAL\_2\_RTS (RX) | IN        | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 2 RTS (Request To Send) |
| 6     | GND                 |           | GND               | BLACK        | GND                          |

## SERIAL 3 / UART 3 (GPS) / I2C 1 | Connector： GPS1

| Pin # | Name                 | Direction | Voltage           | Wire Color | Caption                         |
| ----- | -------------------- | --------- | ----------------- | ---------- | ------------------------------- |
| 1     | VCC\_5V              | IN        | 5 V               | RED        | VCC Power Supply To GPS From AP |
| 3     | SERIAL\_3\_TX        | OUT       | 3.3 V - 5.0 V TTL | BLACK      | UART 3 TX (Transmit Data)       |
| 2     | SERIAL\_3\_RX        | IN        | 3.3 V - 5.0 V TTL | BLACK      | UART 3 RX (Receive Data)        |
| 4     | I2C\_1\_SCL          | IN        | 3.3 V             | BLACK      | I2C 1 Clock Signal              |
| 5     | I2C\_1\_SDA          | IN/OUT    | 3.3 V             | BLACK      | I2C 1 Serial Data               |
| 6     | BUTTON               |           | GND               | BLACK      | Signal shorted to GND on press  |
| 7     | IO\_LED\_SAFET\_PROT |           | GND               | BLACK      | LED Driver For Safety Button    |
| 8     | GND                  |           | GND               | BLACK      | GND Connection                  |

## SERIAL 4 / UART 4 / I2C 2 | Connector： GPS2

| Pin | Name          | Direction | Voltage           | Wire Color   | Caption                         |
| --- | ------------- | --------- | ----------------- | ------------ | ------------------------------- |
| 1   | VCC\_5V       | OUT       | 5 V               | RED/GRAY     | VCC Power Supply To GPS From AP |
| 2   | SERIAL\_4\_TX | OUT       | 3.3 V - 5.0 V TTL | YELLOW/BLACK | UART 4 TX (Transmit Data)       |
| 3   | SERIAL\_4\_RX | IN        | 3.3 V - 5.0 V TTL | GREEN/BLACK  | UART 4 RX (Receive Data)        |
| 4   | I2C\_2\_SCL   | OUT       | 3.3 V - 5.0 V     | GRAY/BLACK   | I2C 2 Clock Signal              |
| 5   | I2C\_2\_SDA   | IN        | 3.3 V - 5.0 V     | GRAY/BLACK   | I2C 2 Serial Data               |
| 6   | GND           |           | GND               | BLACK        | GND                             |

## Buzzer | Connector： BUZZER

| Pin # | Name   | Direction | Voltage         | Wire Color | Caption           |
| ----- | ------ | --------- | --------------- | ---------- | ----------------- |
| 1     | BUZZER | OUT       | Battery voltage | GRAY/BLACK | VBAT (8.4 - 42 V) |
| 2     | GND    |           | GND             | BLACK      | GND Connection    |

## I2C 2 | Connector： I2C 2

| Pin | Name    | Direction | Voltage          | Wire Color  | Caption                       |
| --- | ------- | --------- | ---------------- | ----------- | ----------------------------- |
| 1   | VCC\_5V | OUT       | +5 V             | RED/GRAY    | Power supply                  |
| 2   | SCL     | IN/OUT    | +3.3 V (PULLUPS) | BLUE/BLACK  | SCL, 5 V level, pull-up on AP |
| 3   | SDA     | IN/OUT    | +3.3 V (PULLUPS) | GREEN/BLACK | SDA, 5 V level, pull-up on AP |
| 4   | GND     |           | GND              | BLACK       | GND Connection                |

## Main Power POWER 1 | Connector： POWER1

| Pin # | Name                      | Direction | Voltage | Wire Color | Caption                       |
| ----- | ------------------------- | --------- | ------- | ---------- | ----------------------------- |
| 1     | VDD\_5V\_BRICK            | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 2     | VDD\_5V\_BRICK            | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 3     | BATT\_CURRENT\_SENS\_PROT | IN        | 3.3 V   | BLACK      | Battery Current Connecter     |
| 4     | BATT\_VOLTAGE\_SENS\_PROT | IN        | 3.3 V   | BLACK      | Battery Voltage Connecter     |
| 5     | GND                       |           | GND     | BLACK      | GND                           |
| 6     | GND                       |           | GND     | BLACK      | GND                           |

## Backup Power POWER 2 | Connector： POWER2

| Pin # | Name                     | Direction | Voltage | Wire Color | Caption                       |
| ----- | ------------------------ | --------- | ------- | ---------- | ----------------------------- |
| 1     | VDD\_5V\_BRICK           | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 2     | VDD\_5V\_BRICK           | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 3     | AUX\_BATT\_CURRENT\_SENS | IN        | 3.3 V   | BLACK      | Aux Battery Current Connecter |
| 4     | AUX\_BATT\_VOLTAGE\_SENS | IN        | 3.3 V   | BLACK      | Aux Battery Voltage Connecter |
| 5     | GND                      |           | GND     | BLACK      | GND Connection                |
| 6     | GND                      |           | GND     | BLACK      | GND                           |

## CAN | Connector： CAN2

| Pin # | Name      | Direction | Voltage | Wire Color   | Caption          |
| ----- | --------- | --------- | ------- | ------------ | ---------------- |
| 1     | VCC\_5V   | OUT       | 5 V     | RED/GRAY     | VCC Power Supply |
| 2     | CAN\_H\_2 | IN/OUT    | 12 V    | YELLOW/BLACK | CAN High         |
| 3     | CAN\_L\_2 | IN/OUT    | 12 V    | GREEN/BLACK  | CAN Low          |
| 4     | GND       |           | GND     | BLACK        | GND              |

## IO USART 1 / DSM | Connector： SPKT

| Pin # | Name                          | Direction | Voltage | Caption                  |
| ----- | ----------------------------- | --------- | ------- | ------------------------ |
| 1     | IO\_USART1\_RX\_SPECTRUM\_DSM | IN        |         | IO USART 1 RX, DSM INPUT |
| 2     | GND                           |           | GND     | GND                      |
| 3     | VDD\_3V3\_Spektrum            | OUT       | 3.3 V   | Independent Power Supply |

## CPPM / S.BUS / SERVO SYSTEM | Connector： RCIN MAIN OUT

| Pin # | Name            | Direction | Voltage                              | Caption            |
| ----- | --------------- | --------- | ------------------------------------ | ------------------ |
| S - 1 | IO\_CH1\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 2 | IO\_CH2\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 3 | IO\_CH3\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 4 | IO\_CH4\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 5 | IO\_CH5\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 6 | IO\_CH6\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 7 | IO\_CH7\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 8 | IO\_CH8\_PROT   | OUT       | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 9 | PPM\_SBUS\_PROT | IN/OUT    | 3.3 V / 4.5 V Powered                | PPM / S.Bus Signal |

## PPM S.bus signal and SPKT signal switching

By default, Mini Carrier Board uses PPM and S.bus in RC IN. If you want to switch it to SPKT signals, you need to solder the carrier board as shown below:

![](<../.gitbook/assets/Purple Cube and Mini Carrier Board -7.jpg>)

The middle solder pad of the left hand side is shorted with 5v pin. Therefore, you need to break their connection on PCB. The middle solder pad of the right hand side is shorted with PPM/S.B, so break their connection on PCB as well.

Solder the 3v3 solder pad with the middle solder pad at left hand side; and solder the SPKT solder pad with the middle solder pad at right hand side. So that RC IN port is compatible with SPKT signal.

**Page available for revision and updating through the Github link below:**\
[https://github.com/CubePilot/cubepilot-docs/edit/master/carrier-boards/mini-carrier-board.md](https://github.com/CubePilot/cubepilot-docs/edit/master/carrier-boards/mini-carrier-board.md)

Last update: 10th Jan 2019

# Cube Red Standard Carrier Board Pinout

## Operating Conditions and Performance

<table><thead><tr><th width="310">Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Power Input Voltage/Rated Input Current</td><td>4.1 ~ 5.7V / 2.5A <br><br><strong>Note</strong>: 0 ~ 20 V is supported, but The Cube may not operate properly. </td></tr><tr><td>Power Rated Output/Input power</td><td>14W</td></tr><tr><td>USB Port Input Voltage/Rated Input Current</td><td>4 ~ 5.7V / 250mA</td></tr><tr><td>Servo Rail Input Voltage</td><td>4 ~ 10.5V</td></tr><tr><td>Waterproof Performance</td><td>Not waterproof. External waterproof protection is needed</td></tr><tr><td>Operational Temperature</td><td><p>Recommended ambient temperature: -10°C ~ 55°C. <br></p><p><strong>Note</strong>: The Cube can operate within a wider range of -40°C ~ 100°C but with possible performance degradation or risks.</p></td></tr></tbody></table>

## Ports Standard and Definition

### Standard Carrier Board Ports&#x20;

| Connector | Connector Type              |
| --------- | --------------------------- |
| `GPS1`    | JST-GH 1.25 mm (8-pin)      |
| `GPS2`    | JST-GH 1.25 mm (6-pin)      |
| `TELEM1`  | JST-GH 1.25 mm (6-pin)      |
| `TELEM2`  | JST-GH 1.25 mm (6-pin)      |
| `I2C2`    | JST-GH 1.25 mm (4-pin)      |
| `USB`     | JST-GH 1.25 mm (6-pin)      |
| `CAN1`    | JST-GH 1.25 mm (4-pin)      |
| `CAN2`    | JST-GH 1.25 mm (4-pin)      |
| `CAN3`    | JST-GH 1.25 mm (4-pin)      |
| `POWER1`  | Molex CLIK-Mate 2mm (6-pin) |
| `POWER2`  | Molex CLIK-Mate 2mm (6-pin) |
| `ADC`     | JST-GH 1.25 mm (3-pin)      |
| `DSI`     | JST-GH 1.25 mm (15-pin)     |
| `ETH`     | TE Multi-purp pluh (8P)     |

## <mark style="color:red;">Cube Red</mark> 80-Pin DF17 Connector

<figure><img src="../.gitbook/assets/cube-bottom.png" alt=""><figcaption></figcaption></figure>

### **Connector 1 Assignments**

| Pin Number | Pin Type | Pin Name                      | Function                                                              |
| ---------- | -------- | ----------------------------- | --------------------------------------------------------------------- |
| 1          | I/O      | FMU\_SWDIO                    | FMU serial wire debug I/O                                             |
| 2          | O        | FMU\_LED\_AMBER               | Boot error LED (drive only, controlled by FET)                        |
| 3          | O        | FMU\_SWCLK                    | FMU serial wire debug clock                                           |
| 4          | I/O      | I2C\_2\_SDA                   | I2C serial data Tx/Rx                                                 |
| 5          | O        | EXTERN\_CS                    | Chip select for external SPI (NC, just for debugging)                 |
| 6          | O        | I2C\_2\_SCL                   | I2C serial clock signal                                               |
| 7          | I        | FMU\_!RESET                   | Reset pin for the FMU                                                 |
| 8          | I/O      | CAN\_L\_3                     | CAN bus low signal driver                                             |
| 9          | I        | VDD\_SERVO\_IN                | Power for last resort I/O failsafe                                    |
| 10         | I/O      | CAN\_H\_3                     | CAN bus high signal driver                                            |
| 11         | I        | EXTERN\_DRDY                  | Interrupt pin for external SPI (NC, just for debugging)               |
| 12         | I        | SERIAL\_5\_RX                 | UART 5 RX (receive data)                                              |
| 13         |          | GND                           | System GND                                                            |
| 14         | O        | SERIAL\_5\_TX                 | UART 5 TX (transmit data)                                             |
| 15         |          | GND                           | System GND                                                            |
| 16         | I        | SERIAL\_4\_RX                 | UART 4 RX (receive data)                                              |
| 17         |          | SAFETY                        | Safety button input                                                   |
| 18         | O        | SERIAL\_4\_TX                 | UART 4 TX (transmit data)                                             |
| 19         | O        | VDD\_3V3\_SPEKTRUM\_EN        | Enable for the Spektrum voltage regulator                             |
| 20         | I        | SERIAL\_3\_RX                 | UART 3 RX (receive data)                                              |
| 21         | AI       | PRESSURE\_SENS\_IN            | Analog signal port, for pressure sensor, laser range finder, or sonar |
| 22         | O        | SERIAL\_3\_TX                 | UART 3 TX (transmit data)                                             |
| 23         | AI       | AUX\_BATT\_VOLTAGE\_SENS      | Voltage sense for Aux battery input                                   |
| 24         | O        | ALARM                         | Buzzer PWM signal                                                     |
| 25         | AI       | AUX\_BATT\_CURRENT\_SENS      | Current sense for Aux battery input                                   |
| 26         | I        | IO\_VDD\_3V3                  | IO chip power, pinned through for debug                               |
| 27         | O        | VDD\_5V\_PERIPH\_EN           | Enable voltage supply for peripherals                                 |
| 28         | O        | IO\_LED\_SAFET\_PROT          | IO-LED\_SAFETY (safety LED) pinned out for IRIS                       |
| 29         | I        | VBUS                          | USB VBus (VDD)                                                        |
| 30         |          | SERIAL\_2\_RTS                | UART 2 RTS (request to send)                                          |
| 31         | I/O      | OTG\_DP1                      | USB Data+ (D)                                                         |
| 32         |          | SERIAL\_2\_CTS                | UART 2 CTS (clear to send)                                            |
| 33         | I/O      | OTG\_DM1                      | USB Data- (M)                                                         |
| 34         | I        | SERIAL\_2\_RX                 | UART 2 RX (receive data)                                              |
| 35         | I/O      | I2C\_1\_SDA                   | I2C serial data Tx/Rx                                                 |
| 36         | O        | SERIAL\_2\_TX                 | UART 2 TX (transmit data)                                             |
| 37         | O        | I2C\_1\_SCL                   | I2C serial clock signal                                               |
| 38         | I        | SERIAL\_1\_RX                 | UART 1 RX (receive data)                                              |
| 39         | I/O      | CAN\_L\_2                     | FMU CAN bus low signal driver                                         |
| 40         | O        | SERIAL\_1\_TX                 | UART 1 TX (transmit data)                                             |
| 41         | I/O      | CAN\_H\_2                     | FMU CAN bus high signal driver                                        |
| 42         |          | SERIAL\_1\_RTS                | UART 1 RTS (request to send)                                          |
| 43         | I        | VDD\_5V\_PERIPH\_OC           | Error state message from peripheral power supply                      |
| 44         |          | SERIAL\_1\_CTS                | UART 1 CTS (clear to send)                                            |
| 45         | I        | VDD\_5V\_HIPOWER\_OC          | Error state message from high power peripheral power supply           |
| 46         | O        | IO\_USART\_1\_TX              | I/O USART 1 TX                                                        |
| 47         | AI       | BATT\_VOLTAGE\_SENS\_PROT     | Voltage sense from main battery                                       |
| 48         | O        | IO\_USART1\_RX\_SPECTRUM\_DSM | Signal from Spectrum receiver                                         |
| 49         | AI       | BATT\_CURRENT\_SENS\_PROT     | Current sense from main battery                                       |
| 50         | O        | FMU\_CH1\_PROT                | FMU PWM Output Channel 1                                              |
| 51         | O        | SPI\_EXT\_MOSI                | External SPI, for debug only                                          |
| 52         | O        | FMU\_CH2\_PROT                | FMU PWM Output Channel 2                                              |
| 53         | I        | VDD\_SERVO                    | VDD\_Servo, for monitoring servo bus                                  |
| 54         | O        | FMU\_CH3\_PROT                | FMU PWM Output Channel 3                                              |
| 55         | I        | VDD\_BRICK\_VALID             | Main power valid signal                                               |
| 56         | O        | FMU\_CH4\_PROT                | FMU PWM Output Channel 4                                              |
| 57         | I        | VDD\_BACKUP\_VALID            | Backup power valid signal                                             |
| 58         | O        | FMU\_CH5\_PROT                | FMU PWM Output Channel 5                                              |
| 59         | I        | VBUS\_VALID                   | USB bus valid signal                                                  |
| 60         | O        | FMU\_CH6\_PROT                | FMU PWM Output Channel 6                                              |
| 61         | I        | VDD\_5V\_IN\_PROT             | Main power (5V) into FMU from power selection                         |
| 62         | I        | PPM\_SBUS\_PROT               | PPM / S.Bus signal input                                              |
| 63         | I        | VDD\_5V\_IN\_PROT             | Main power (5V) into FMU from power selection                         |
| 64         | O        | S.BUS\_OUT                    | S.Bus signal output                                                   |
| 65         | O        | IO\_VDD\_5V5                  | IO VDD 5.5V                                                           |
| 66         | O        | IO\_CH8\_PROT                 | I/O PWM Output Channel 8                                              |
| 67         | I        | SPI\_EXT\_MISO                | External SPI, for debug only                                          |
| 68         | O        | IO\_CH7\_PROT                 | I/O PWM Output Channel 7                                              |
| 69         | I/O      | IO\_SWDIO                     | I/O serial wire debug                                                 |
| 70         | O        | IO\_CH6\_PROT                 | I/O PWM Output Channel 6                                              |
| 71         | O        | IO\_SWCLK                     | I/O serial wire debug clock                                           |
| 72         | O        | IO\_CH5\_PROT                 | I/O PWM Output Channel 5                                              |
| 73         | O        | SPI\_EXT\_SCK                 | External SPI, for debug only                                          |
| 74         | O        | IO\_CH4\_PROT                 | I/O PWM Output Channel 4                                              |
| 75         | I        | IO\_!RESET                    | I/O reset pin                                                         |
| 76         | O        | IO\_CH3\_PROT                 | I/O PWM Output Channel 3                                              |
| 77         | I/O      | CAN\_L\_1                     | FMU CAN bus low signal driver                                         |
| 78         | O        | IO\_CH2\_PROT                 | I/O PWM Output Channel 2                                              |
| 79         | I/O      | CAN\_H\_1                     | FMU CAN bus high signal driver                                        |
| 80         | O        | IO\_CH1\_PROT                 | I/O PWM Output Channel 1                                              |

### **Connector 2 Assignments**

| Pin Number | Pin Type | Pin Name            | Description                                   |
| ---------- | -------- | ------------------- | --------------------------------------------- |
| 1          |          | GND                 | System GND                                    |
| 2          | I        | FMU\_BOOT           | FMU boot                                      |
| 3          | I/O      | FC\_NET\_TX+        | Ethernet TX+,Auto-MDIX support                |
| 4          |          | NC                  | For future use                                |
| 5          |          | GND                 | System GND                                    |
| 6          |          | IO\_BOOT            | IO MCU boot                                   |
| 7          | I/O      | FC\_NET\_TX-        | Ethernet TX-, Auto-MDIX support               |
| 8          |          | NC                  | For future use                                |
| 9          |          | GND                 | System GND                                    |
| 10         |          | NC                  | For future use                                |
| 11         | I/O      | FC\_NET\_RX+        | Ethernet RX+, Auto-MDIX support               |
| 12         |          | NC                  | For future use                                |
| 13         |          | GND                 | System GND                                    |
| 14         |          | NC                  | For future use                                |
| 15         | I/O      | FC\_NET\_RX-        | Ethernet RX-, Auto-MDIX support               |
| 16         |          | NC                  | For future use                                |
| 17         |          | GND                 | System GND                                    |
| 18         |          | NC                  | For future use                                |
| 19         | O        | FC\_NET\_LEDY       | Link speed LED indication                     |
| 20         |          | NC                  | For future use                                |
| 21         | O        | FC\_NET\_LEDG       | Ethernet link activity LED indication         |
| 22         |          | NC                  | For future use                                |
| 23         | I        | FC\_NET\_VCC        | Ethernet 3.3V power in                        |
| 24         |          | NC                  | For future use                                |
| 25         | I        | Timestamp rtc       | Timestamp RTC                                 |
| 26         |          | NC                  | For future use                                |
| 27         |          | GND                 | System GND                                    |
| 28         |          | NC                  | For future use                                |
| 29         | I/O      | CAN\_L\_1           | CAN bus low signal driver                     |
| 30         |          | NC                  | For future use                                |
| 31         | I/O      | CAN\_H\_1           | CAN bus high signal driver                    |
| 32         |          | NC                  | For future use                                |
| 33         | I/O      | CAN\_L\_2           | CAN bus low signal driver                     |
| 34         |          | NC                  | For future use                                |
| 35         | I/O      | CAN\_H\_2           | CAN bus high signal driver                    |
| 36         |          | NC                  | For future use                                |
| 37         | I/O      | CAN\_L\_3           | CAN bus low signal driver                     |
| 38         |          | NC                  | For future use                                |
| 39         | I/O      | CAN\_H\_3           | CAN bus high signal driver                    |
| 40         |          | NC                  | For future use                                |
| 41         |          | GND                 | System GND                                    |
| 42         |          | NC                  | For future use                                |
| 43         | I        | UART8\_RX           | IO UART 8 RX (receive data)                   |
| 44         |          | NC                  | For future use                                |
| 45         | O        | UART8\_TX           | IO UART 8 TX (transmit data)                  |
| 46         |          | NC                  | For future use                                |
| 47         |          | GND                 | System GND                                    |
| 48         |          | NC                  | For future use                                |
| 49         | O        | DSI\_CKP            | MIPI DSI host clock postive                   |
| 50         |          | NC                  | For future use                                |
| 51         | O        | DSI\_CKN            | MIPI DSI host clock negative                  |
| 52         |          | NC                  | For future use                                |
| 53         |          | GND                 | System GND                                    |
| 54         |          | NC                  | For future use                                |
| 55         | O        | DSI\_D0P            | MIPI DSI host DATA0 postive                   |
| 56         |          | NC                  | For future use                                |
| 57         | O        | DSI\_D0N            | MIPI DSI host DATA0 negative                  |
| 58         |          | NC                  | For future use                                |
| 59         |          | GND                 | System GND                                    |
| 60         |          | NC                  | For future use                                |
| 61         | O        | DSI\_D1P            | MIPI DSI host DATA1 postive                   |
| 62         |          | NC                  | For future use                                |
| 63         | O        | DSI\_D1N            | MIPI DSI host DATA1 negative                  |
| 64         |          | NC                  | For future use                                |
| 65         |          | GND                 | System GND                                    |
| 66         |          | NC                  | For future use                                |
| 67         | O        | FMU\_DAC            | FMU analog output                             |
| 68         |          | NC                  | For future use                                |
| 69         | O        | IO\_DAC             | IO analog output                              |
| 70         |          | NC                  | For future use                                |
| 71         |          | GND                 | System GND                                    |
| 72         |          | NC                  | For future use                                |
| 73         | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 74         |          | NC                  | For future use                                |
| 75         | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 76         |          | NC                  | For future use                                |
| 77         | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 78         |          | NC                  | For future use                                |
| 79         | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 80         |          | NC                  | For future use                                |

### Ports and Protocols

<table><thead><tr><th width="199.33333333333331">Name </th><th width="412">Function</th><th>Label</th></tr></thead><tbody><tr><td>SERIAL 1 / UART 1</td><td>UART 1 with hardware flow control; 3.3V ~ 5V CMOS TTL level with ESD protection</td><td><code>TELEM1</code></td></tr><tr><td>SERIAL 2 / UART 2</td><td>UART 2 with hardware flow control; 3.3V ~ 5V CMOS TTL level with ESD protection</td><td><code>TELEM2</code></td></tr><tr><td>SERIAL 3 / UART 3 / I2C 1</td><td>3.3V ~ 5V CMOS TTL level with ESD protection</td><td><code>GPS1</code></td></tr><tr><td>SERIAL 4 / UART 4 / I2C 2</td><td>UART 4 / I2C 2; 3.3V ~ 5V CMOS TTL level with ESD protection</td><td><code>GPS2</code></td></tr><tr><td>SERIAL 8 / UART 8 (Debug Console)</td><td>UART 8 on IO; Debug Console</td><td><code>CONS</code></td></tr><tr><td>I2C 2</td><td>Independent I2C 2 port. Drivers are on-board FMU. Un-buffered, and pulled up to 3.3V COMMS TTL level</td><td><code>I2C2</code></td></tr><tr><td>CAN Bus</td><td>Standard CAN Bus. Drivers are on-board FMU</td><td><code>CAN1</code> <code>CAN2</code> <code>CAN3</code></td></tr><tr><td>R/C IN</td><td>Support CPPM / Futaba S.Bus signal input or any protocols supported by ArduPilot</td><td><code>RCIN_FMU1</code><br><code>RCIN_FMU2</code></td></tr><tr><td>DSM / USART</td><td>Support Spektrum DSM® Technology, Spektrum DSM2™ / DSMX™ compatible input; I/O USART 1 RX</td><td><code>SKPT</code></td></tr><tr><td>S.Bus OUT / RSSI IN</td><td>S.Bus Servo I/O. PPM Output. Can be used as RSSI input</td><td><code>SBUSo</code></td></tr><tr><td>POWER</td><td>Main power source and Backup power source input</td><td><code>POWER1</code> <code>POWER2</code></td></tr><tr><td>MAIN OUT</td><td>Secondary FMU 8 x PWM/BDSHOT/RELAY</td><td><code>MAIN OUT</code></td></tr><tr><td>AUX OUT</td><td>Primary FMU 6 x PWM/BDSHOT/RELAY</td><td><code>AUX OUT</code></td></tr><tr><td>USB</td><td>LED, speaker, and USB extension</td><td><code>USB</code></td></tr><tr><td>ADC</td><td>3.3 V ADC Input</td><td><code>ADC</code></td></tr><tr><td>SPI</td><td>Built-in SPI port, with NO buffer, can only use short cable for connection. Not recommended for use.</td><td><code>Built-in contact point</code></td></tr><tr><td>Debug</td><td>I/O and FMU testing port</td><td><code>Built-in port</code></td></tr><tr><td>ETH</td><td>Ethernet port</td><td></td></tr><tr><td>DSI</td><td>MIPI DSI output and timestamp; FMU/IO BOOT</td><td></td></tr></tbody></table>

### **Carrier Board Port Interface and Pin Label**

<figure><img src="../.gitbook/assets/Cube-Red-20231124-04.png" alt=""><figcaption></figcaption></figure>

### **SERIAL 1 / UART 1 | Port: `TELEM1`**

<table><thead><tr><th width="140">Pin Number</th><th width="104">Name</th><th width="67">I/O</th><th width="93">Voltage</th><th width="145">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>VCC</td></tr><tr><td>2</td><td>SERIAL_1_TX</td><td>OUT</td><td>3.3 V ~ 5.0 V TTL</td><td>Orange/Black</td><td>UART 1 TX (Transmit Data)</td></tr><tr><td>3</td><td>SERIAL_1_RX</td><td>IN</td><td>3.3 V ~ 5.0 V TTL</td><td>Green/Black</td><td>UART 1 RX (Receive Data)</td></tr><tr><td>4</td><td>SERIAL_1_CTS (TX)</td><td>OUT</td><td>3.3 V ~ 5.0 V TTL</td><td>Gray/Black</td><td>UART 1 CTS (Clear to Send)</td></tr><tr><td>5</td><td>SERIAL_1_RTS (RX)</td><td>IN</td><td>3.3 V ~ 5.0 V TTL</td><td>Gray/Black</td><td>UART 1 RTS (Request to Send)</td></tr><tr><td>6</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **SERIAL 3 / UART 3 (GPS) / I2C 1 | Port: `GPS1`**

<table><thead><tr><th width="136">Pin Number</th><th width="125">Name</th><th width="73">I/O</th><th width="106">Voltage</th><th width="115">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>IN</td><td>5 V</td><td>Red</td><td>VCC Power Supply to GPS from AP</td></tr><tr><td>3</td><td>SERIAL_3_TX</td><td>OUT</td><td>3.3 V ~ 5.0 V TTL</td><td>Black</td><td>UART 3 TX (Transmit Data)</td></tr><tr><td>2</td><td>SERIAL_3_RX</td><td>IN</td><td>3.3 V ~ 5.0 V TTL</td><td>Black</td><td>UART 3 RX (Receive Data)</td></tr><tr><td>4</td><td>I2C_1_SCL</td><td>IN</td><td>3.3 V</td><td>Black</td><td>I2C 1 Clock Signal</td></tr><tr><td>5</td><td>I2C_1_SDA</td><td>IN/OUT</td><td>3.3 V</td><td>Black</td><td>I2C 1 Serial Data</td></tr><tr><td>6</td><td>BUTTON</td><td></td><td>GND</td><td>Black</td><td>Signal shorted to GND on press</td></tr><tr><td>7</td><td>IO_LED_SAFET_PROT</td><td></td><td>GND</td><td>Black</td><td>LED Driver for Safety Button</td></tr><tr><td>8</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **Buzzer / USB / LED | Port: `USB`**

<table><thead><tr><th width="134">Pin Number</th><th width="86">Name</th><th width="92">I/O</th><th width="90">Voltage</th><th width="127">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>V BUS</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>USB V BUS</td></tr><tr><td>2</td><td>OTG_DP1</td><td>IN/OUT</td><td>3.3 V</td><td>Green/Black</td><td>USB Data Positive (D+)</td></tr><tr><td>3</td><td>OTG_DM1</td><td>IN/OUT</td><td>3.3 V</td><td>Red/Black</td><td>USB Data Minus (D-)</td></tr><tr><td>4</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr><tr><td>5</td><td>BUZZER_OUT</td><td>OUT</td><td>Battery Voltage</td><td>Gray/Black</td><td>VBAT (8.4 - 42 V)</td></tr><tr><td>6</td><td>FMU_LED_AMBER</td><td>OUT</td><td></td><td>Black</td><td>Boot / Error LED (FW updates)</td></tr></tbody></table>

### **I2C 2 | Port: `I2C 2`**

<table><thead><tr><th width="137">Pin Number</th><th width="119">Name</th><th width="90">I/O</th><th width="116">Voltage</th><th width="127">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>VCC Power Supply</td></tr><tr><td>2</td><td>I2C_2_SCL</td><td>IN/OUT</td><td>3.3 V (PULLUPS)</td><td>Blue/Black</td><td>I2C 2 Clock Signal, Pull-up on AP</td></tr><tr><td>3</td><td>I2C_2_SDA</td><td>IN/OUT</td><td>3.3 V (PULLUPS)</td><td>Green/Black</td><td>I2C 2 Serial Data, Pull-up on AP</td></tr><tr><td>4</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **CAN 1 | Port: `CAN1`**

<table><thead><tr><th width="136">Pin Number</th><th width="108">Name</th><th width="96">I/O</th><th width="92">Voltage</th><th width="149">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>VCC Power Supply</td></tr><tr><td>2</td><td>CAN_H_1</td><td>IN/OUT</td><td>12 V</td><td>Orange/Black</td><td>CAN High</td></tr><tr><td>3</td><td>CAN_L_1</td><td>IN/OUT</td><td>12 V</td><td>Green/Black</td><td>CAN Low</td></tr><tr><td>4</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **CAN 2 | Port: `CAN2`**

<table><thead><tr><th width="134">Pin Number</th><th width="105">Name</th><th width="90">I/O</th><th width="93">Voltage</th><th width="162">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>VCC Power Supply</td></tr><tr><td>2</td><td>CAN_H_2</td><td>IN/OUT</td><td>12 V</td><td>Orange/Black</td><td>CAN High</td></tr><tr><td>3</td><td>CAN_L_2</td><td>IN/OUT</td><td>12 V</td><td>Green/Black</td><td>CAN Low</td></tr><tr><td>4</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **ADC | Port: `ADC`**

<table><thead><tr><th width="135">Pin Number</th><th>Name</th><th width="71">I/O</th><th width="93">Voltage</th><th>Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VDD_5V_PRES</td><td>OUT</td><td>5 V</td><td>Red</td><td>Power Supply</td></tr><tr><td>2</td><td>PRESSURE_SENS_IN</td><td>IN</td><td></td><td>Black</td><td></td></tr><tr><td>3</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **IO USART 1 / DSM | Port: `SPKT`**

<table><thead><tr><th width="140">Pin Number</th><th>Name</th><th width="68">I/O</th><th width="90">Voltage</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>IO_USART1_RX_SPECTRUM_DSM</td><td>IN</td><td></td><td>IO USART 1 RX, DSM INPUT</td></tr><tr><td>2</td><td>GND</td><td></td><td>GND</td><td>GND</td></tr><tr><td>3</td><td>VDD_3V3_Spektrum</td><td>OUT</td><td>3.3 V</td><td>Independent Power Supply</td></tr></tbody></table>

<figure><img src="../.gitbook/assets/Cube-Red-20231124-05.png" alt=""><figcaption></figcaption></figure>

### **SERIAL 8/ UART 8  / S.Bus OUT | Port: `CONS`** **`SBUSo`**

<table><thead><tr><th width="138">Pin Number</th><th width="149">Name</th><th width="86">I/O</th><th>Voltage</th><th>Definition</th></tr></thead><tbody><tr><td>1 <code>SBUSo</code></td><td>S.Bus_Out</td><td>OUT</td><td></td><td>S.Bus Signal Output</td></tr><tr><td>2 <code>CONS</code></td><td>SERIAL_8_TX</td><td>OUT</td><td>3.3 V - 5.0 V TTL</td><td>IO UART 8 TX (Transmit Data)</td></tr><tr><td>3 <code>SBUSo</code></td><td>VDD_SERVO</td><td>OUT</td><td>Servo Voltage</td><td></td></tr><tr><td>4 <code>CONS</code></td><td>SERIAL_8_RX</td><td>IN</td><td>3.3 V - 5.0 V TTL</td><td>IO UART 8 RX (Receive Data)</td></tr><tr><td>5 <code>SBUSo</code></td><td>GND</td><td></td><td>GND</td><td>GND</td></tr><tr><td>6 <code>CONS</code></td><td>GND</td><td></td><td>GND</td><td>GND</td></tr></tbody></table>

### **Main Power POWER 1 | Port: `POWER1`**

<table><thead><tr><th width="136">Pin Number</th><th>Name</th><th width="63">I/O</th><th width="103">Voltage</th><th>Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VDD_5V_BRICK</td><td>IN</td><td>5 V</td><td>Red/Gray</td><td>Supply to AP from Power Brick</td></tr><tr><td>2</td><td>VDD_5V_BRICK</td><td>IN</td><td>5 V</td><td>Red/Gray</td><td>Supply to AP from Power Brick</td></tr><tr><td>3</td><td>BATT_CURRENT_SENS_PROT</td><td></td><td>3.3 V</td><td>Black</td><td>Battery Current Connecter</td></tr><tr><td>4</td><td>BATT_CURRENT_VOLTAGE_PROT</td><td>IN</td><td>3.3 V</td><td>Black</td><td>Battery Voltage Connecter</td></tr><tr><td>5</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr><tr><td>6</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **Backup Power POWER 2 | Port: `POWER2`**

<table><thead><tr><th width="134">Pin Number</th><th>Name</th><th width="68">I/O</th><th width="93">Voltage</th><th width="128">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VDD_5V_BRICK</td><td>IN</td><td>5 V</td><td>Red/Gray</td><td>Supply to AP from Power Brick</td></tr><tr><td>2</td><td>VDD_5V_BRICK</td><td>IN</td><td>5 V</td><td>Red/Gray</td><td>Supply to AP from Power Brick</td></tr><tr><td>3</td><td>AUX_BATT_CURRENT_SENS</td><td></td><td>3.3 V</td><td>Black</td><td>Aux Battery Current Connecter</td></tr><tr><td>4</td><td>AUX_BATT_VOLTAGE_SENS</td><td>IN</td><td>3.3 V</td><td>Black</td><td>Aux Battery Voltage Connecter</td></tr><tr><td>5</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND Connection</td></tr><tr><td>6</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **CPPM / S.BUS / SERVO SYSTEM | Port: `RCIN`** **`MAIN OUT`** **`AUX OUT`**

<table><thead><tr><th width="142">Pin Number</th><th>Name</th><th width="68">I/O</th><th width="172">Voltage</th><th>Definition</th></tr></thead><tbody><tr><td>S - 1</td><td>Secondary_FMU_CH1_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 2</td><td>Secondary_FMU_CH2_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 3</td><td>Secondary_FMU_CH3_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 4</td><td>Secondary_FMU_CH4_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 5</td><td>Secondary_FMU_CH5_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 6</td><td>Secondary_FMU_CH6_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 7</td><td>Primary_FMU_CH1_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 8</td><td>Primary_FMU_CH2_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 9</td><td>Primary_FMU_CH3_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 10</td><td>Primary_FMU_CH4_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 11</td><td>Primary_FMU_CH5_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 12</td><td>Primary_FMU_CH6_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 13</td><td>Primary_FMU_CH7_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 14</td><td>Primary_FMU_CH8_PROT</td><td>OUT</td><td>3.3 V Servo Signal, Servo Rail Power</td><td>PWM Signal</td></tr><tr><td>S - 15</td><td>PPM_SBUS_PROT</td><td>IN/OUT</td><td>3.3 V / 4.5 V Powered</td><td>PPM / S.Bus Signal, goes to both Primary and Secondary FMU</td></tr></tbody></table>

<figure><img src="../.gitbook/assets/Cube-Red-20231124-03-1701049699027-5.png" alt=""><figcaption></figcaption></figure>

### **SERIAL 2 / UART 2 | Port: `TELEM2`**

<table><thead><tr><th width="135">Pin Number</th><th>Name</th><th width="71">I/O</th><th width="123">Voltage</th><th width="146">Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>VCC</td></tr><tr><td>2</td><td>SERIAL_2_TX</td><td>OUT</td><td>3.3 V - 5.0 V TTL</td><td>Orange/Black</td><td>UART 2 TX (Transmit Data)</td></tr><tr><td>3</td><td>SERIAL_2_RX</td><td>IN</td><td>3.3 V - 5.0 V TTL</td><td>Green/Black</td><td>UART 2 RX (Receive Data)</td></tr><tr><td>4</td><td>SERIAL_2_CTS (TX)</td><td>OUT</td><td>3.3 V - 5.0 V TTL</td><td>Gray/Black</td><td>UART 2 CTS (Clear To Send)</td></tr><tr><td>5</td><td>SERIAL_2_RTS (RX)</td><td>IN</td><td>3.3 V - 5.0 V TTL</td><td>Gray/Black</td><td>UART 2 RTS (Request To Send)</td></tr><tr><td>6</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **SERIAL 4 / UART 4 / I2C 2 | Port: `GPS2`**

<table><thead><tr><th width="135">Pin Number</th><th>Name</th><th width="66">I/O</th><th width="124">Voltage</th><th>Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>VCC Power Supply To GPS From AP</td></tr><tr><td>2</td><td>SERIAL_4_TX</td><td>OUT</td><td>3.3 V - 5.0 V TTL</td><td>Orange/Black</td><td>UART 4 TX (Transmit Data)</td></tr><tr><td>3</td><td>SERIAL_4_RX</td><td>IN</td><td>3.3 V - 5.0 V TTL</td><td>Green/Black</td><td>UART 4 RX (Receive Data)</td></tr><tr><td>4</td><td>I2C_2_SCL</td><td>OUT</td><td>3.3 V - 5.0 V</td><td>Gray/Black</td><td>I2C 2 Clock Signal</td></tr><tr><td>5</td><td>I2C_2_SDA</td><td>IN</td><td>3.3 V - 5.0 V</td><td>Gray/Black</td><td>I2C 2 Serial Data</td></tr><tr><td>6</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

### **CAN 3 | Port: `CAN3`**

<table><thead><tr><th width="98">Pin Number</th><th width="105">Name</th><th width="100">I/O</th><th width="90">Voltage</th><th>Cable Color</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>VCC_5V</td><td>OUT</td><td>5 V</td><td>Red/Gray</td><td>VCC Power Supply</td></tr><tr><td>2</td><td>CAN_H_2</td><td>IN/OUT</td><td>12 V</td><td>Orange/Black</td><td>CAN High</td></tr><tr><td>3</td><td>CAN_L_2</td><td>IN/OUT</td><td>12 V</td><td>Green/Black</td><td>CAN Low</td></tr><tr><td>4</td><td>GND</td><td></td><td>GND</td><td>Black</td><td>GND</td></tr></tbody></table>

<figure><img src="../.gitbook/assets/Cube-Red-20231124-01.png" alt=""><figcaption></figcaption></figure>

### **Ethernet: `ETH1`**

<table><thead><tr><th width="136">Pin Number</th><th width="107">Name</th><th width="103">I/O</th><th>Desciption</th></tr></thead><tbody><tr><td>1</td><td>TXP/RXP</td><td>IN/OUT</td><td>Ethernet TXP/RXP Auto-MDIX support</td></tr><tr><td>2</td><td>TXN/RXN</td><td>IN/OUT</td><td>Ethernet TXN/RXN Auto-MDIX support</td></tr><tr><td>3</td><td>RXP/TXP</td><td>IN/OUT</td><td>Ethernet RXP/TXP Auto-MDIX support</td></tr><tr><td>4</td><td>NC</td><td></td><td>No connect</td></tr><tr><td>5</td><td>NC</td><td></td><td>No connect</td></tr><tr><td>6</td><td>RXN/TXN</td><td>IN/OUT</td><td>Ethernet RXN/TXN Auto-MDIX support</td></tr><tr><td>7</td><td>NC</td><td></td><td>No connect</td></tr><tr><td>8</td><td>NC</td><td></td><td>No connect</td></tr></tbody></table>



<figure><img src="../.gitbook/assets/Cube-Red-20231124-02.png" alt=""><figcaption></figcaption></figure>

### **DSI / Timestamp / Boot| Port: `DSI`**

<table><thead><tr><th width="136">Pin Number</th><th width="169">Name</th><th width="91">I/O</th><th>Definition</th></tr></thead><tbody><tr><td>1</td><td>IO_BOOT_0</td><td>OUT</td><td>IO Boot</td></tr><tr><td>2</td><td>FMU_BOOT_0</td><td>OUT</td><td>FMU Boot</td></tr><tr><td>3</td><td>TIMESTAMP_RTC</td><td>OUT</td><td>Timestamp</td></tr><tr><td>4</td><td>GND</td><td></td><td>GND</td></tr><tr><td>5</td><td>DSI_CKP</td><td>OUT</td><td>MIPI DSI Host Clock Positive</td></tr><tr><td>6</td><td>DSI_CKN</td><td>OUT</td><td>MIPI DSI Host Clock Negative</td></tr><tr><td>7</td><td>GND</td><td></td><td>GND</td></tr><tr><td>8</td><td>DSI_D0P</td><td>OUT</td><td>MIPI DSI Host DATA 0 Positive</td></tr><tr><td>9</td><td>DSI_D0N</td><td>OUT</td><td>MIPI DSI Host DATA 0 Negative</td></tr><tr><td>10</td><td>GND</td><td></td><td>GND</td></tr><tr><td>11</td><td>DSI_D1P</td><td>OUT</td><td>MIPI DSI Host DATA 1 Positive</td></tr><tr><td>12</td><td>DSI_D1N</td><td>OUT</td><td>MIPI DSI Host DATA 1 Negative</td></tr><tr><td>13</td><td>GND</td><td></td><td>GND</td></tr><tr><td>14</td><td>IO_DAC</td><td>OUT</td><td>IO analog output</td></tr><tr><td>15</td><td>FMU_DAC</td><td>OUT</td><td>FMU analog output</td></tr></tbody></table>

The following Github link can be used to revise and update the <mark style="color:red;">Cube Red</mark> Standard Carrier Board Pinout informatio&#x6E;**:** [https://github.com/CubePilot/cubepilot-docs/blob/master/carrier-boards/cube-red-standard-carrier-board-pinout.md](cube-red-standard-carrier-board-pinout.md)

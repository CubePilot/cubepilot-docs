# Mini Carrier Board

## Working Conditions and Performance

| Parameter                                    | Description                                                      |
| -------------------------------------------- | ---------------------------------------------------------------- |
| POWER Input Voltage / Rated Input Current    | 4-5.7V / 2.5A; 0-20V is safe for the system but it will not work |
| POWER rated output / input power             | 14 W                                                             |
| USB port input voltage / rated input current | 4-5.7V / 250mA                                                   |
| Servo rail input voltage                     | 4-10.5V                                                          |
| Waterproof performance                       | Not waterproof. External waterproof protection is needed         |
| Working temperature                          | -10°C / 55°C                                                     |

## Size and Specifications

| Type                                       | Description                       |
| ------------------------------------------ | --------------------------------- |
| Mini Carrier Board Size / Chassis Material | 47.5x38.5x17.8 (mm) / ABS Molding |
|                                            |                                   |

## Interfaces and Definitions

### Pinout

![](<../../.gitbook/assets/Purple Cube and Mini Carrier Board -1.jpg>)

The red dot on the plug side denotes Pin 1.

![](<../../.gitbook/assets/Purple Cube and Mini Carrier Board -2.jpg>)

![](<../../.gitbook/assets/Purple Cube and Mini Carrier Board -3.jpg>)

![](<../../.gitbook/assets/Purple Cube and Mini Carrier Board -4.jpg>)

![](<../../.gitbook/assets/Purple Cube and Mini Carrier Board -5.jpg>)

![](<../../.gitbook/assets/Purple Cube and Mini Carrier Board -6.jpg>)

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

<table><thead><tr><th>Pin Number</th><th>Name</th><th width="158">Direction</th><th>Description</th></tr></thead><tbody><tr><td>1</td><td>FMU_SWDIO</td><td>I/O</td><td>FMU serial wire debug I/O</td></tr><tr><td>2</td><td>FMU_LED_AMBER</td><td>O</td><td>Boot error LED (drive only, controlled by FET)</td></tr><tr><td>3</td><td>FMU_SWCLK</td><td>O</td><td>FMU serial wire debug clock</td></tr><tr><td>4</td><td>I2C_2_SDA</td><td>I/O</td><td>I2C data I/O</td></tr><tr><td>5</td><td>EXTERN_CS</td><td>O</td><td>Chip select for external SPI (NC, only for debugging)</td></tr><tr><td>6</td><td>I2C_2_SCL</td><td>O</td><td>I2C clock</td></tr><tr><td>7</td><td>FMU_!RESET</td><td>I</td><td>Reset pin for the FMU</td></tr><tr><td>8</td><td>PROT_SPARE_1</td><td></td><td>Spare</td></tr><tr><td>9</td><td>VDD_SERVO_IN</td><td>I</td><td>Power for last resort I/O failsafe</td></tr><tr><td>10</td><td>PROT_SPARE_2</td><td></td><td>Spare</td></tr><tr><td>11</td><td>EXTERN_DRDY</td><td>I</td><td>Interrupt pin for external SPI (NC, just for debugging)</td></tr><tr><td>12</td><td>SERIAL_5_RX</td><td>I</td><td>UART 5 RX (Receive Data)</td></tr><tr><td>13</td><td>GND</td><td></td><td>System GND</td></tr><tr><td>14</td><td>SERIAL_5_TX</td><td>O</td><td>UART 5 TX (Transmit Data)</td></tr><tr><td>15</td><td>GND</td><td></td><td>System GND</td></tr><tr><td>16</td><td>SERIAL_4_RX</td><td>I</td><td>UART 4 RX (Receive Data)</td></tr><tr><td>17</td><td>SAFETY</td><td></td><td>Safety button input</td></tr><tr><td>18</td><td>SERIAL_4_TX</td><td>O</td><td>UART 4 TX (Transmit Data)</td></tr><tr><td>19</td><td>VDD_3V3_SPEKTRUM_EN</td><td>O</td><td>Enable for the spectrum voltage supply</td></tr><tr><td>20</td><td>SERIAL_3_RX</td><td>I</td><td>UART 3 RX (Receive Data)</td></tr><tr><td>21</td><td>PRESSURE_SENS_IN</td><td>AI</td><td>Analogue port, for pressure sensor, or Laser range finder, or Sonar</td></tr><tr><td>22</td><td>SERIAL_3_TX</td><td>O</td><td>UART 3 TX (Transmit Data)</td></tr><tr><td>23</td><td>AUX_BATT_VOLTAGE_SENS</td><td>AI</td><td>Voltage sense for Aux battery input</td></tr><tr><td>24</td><td>ALARM</td><td>O</td><td>Buzzer PWM signal</td></tr><tr><td>25</td><td>AUX_BATT_CURRENT_SENS</td><td>AI</td><td>Current sense for Aux battery input</td></tr><tr><td>26</td><td>IO_VDD_3V3</td><td>I</td><td>IO chip power, pinned through for debugging</td></tr><tr><td>27</td><td>VDD_5V_PERIPH_EN</td><td>O</td><td>Enable voltage supply for Peripherals</td></tr><tr><td>28</td><td>IO_LED_SAFET_PROT</td><td>O</td><td>IO-LED_SAFETY(safety LED) pinned out for IRIS</td></tr><tr><td>29</td><td>VBUS</td><td>I</td><td>USB VBus (VDD)</td></tr><tr><td>30</td><td>SERIAL_2_RTS</td><td></td><td>UART 2 RTS (Request To Send)</td></tr><tr><td>31</td><td>OTG_DP1</td><td>I/O</td><td>USB Data+</td></tr><tr><td>32</td><td>SERIAL_2_CTS</td><td></td><td>UART 2 CTS (Clear To Send)</td></tr><tr><td>33</td><td>OTG_DM1</td><td>I/O</td><td>USB Data-</td></tr><tr><td>34</td><td>SERIAL_2_RX</td><td>I</td><td>UART 2 RX (Receive Data)</td></tr><tr><td>35</td><td>I2C_1_SDA</td><td>I/O</td><td>I2C data I/O</td></tr><tr><td>36</td><td>SERIAL_2_TX</td><td>O</td><td>UART 2 TX (Transmit Data)</td></tr><tr><td>37</td><td>I2C_1_SCL</td><td>O</td><td>I2C clock</td></tr><tr><td>38</td><td>SERIAL_1_RX</td><td>I</td><td>UART 1 RX (Receive Data)</td></tr><tr><td>39</td><td>CAN_L_2</td><td>I/O</td><td>FMU CAN bus Low signal driver</td></tr><tr><td>40</td><td>SERIAL_1_TX</td><td>O</td><td>UART 1 TX (Transmit Data)</td></tr><tr><td>41</td><td>CAN_H_2</td><td>I/O</td><td>FMU CAN bus High signal driver</td></tr><tr><td>42</td><td>SERIAL_1_RTS</td><td></td><td>UART 1 RTS (Request To Send)</td></tr><tr><td>43</td><td>VDD_5V_PERIPH_OC</td><td>I</td><td>Error state message from peripheral power supply</td></tr><tr><td>44</td><td>SERIAL_1_CTS</td><td></td><td>UART 1 CTS (Clear To Send)</td></tr><tr><td>45</td><td>VDD_5V_HIPOWER_OC</td><td>I</td><td>Error state message from High power peripheral power supply</td></tr><tr><td>46</td><td>IO_USART_1_TX</td><td>O</td><td>I/O USART 1 TX</td></tr><tr><td>47</td><td>BATT_VOLTAGE_SENS_PROT</td><td>AI</td><td>Voltage sense from main battery</td></tr><tr><td>48</td><td>IO_USART1_RX_SPECTRUM_DSM</td><td>O</td><td>Signal from Spectrum receiver</td></tr><tr><td>49</td><td>BATT_CURRENT_SENS_PROT</td><td>AI</td><td>Current sense from main battery</td></tr><tr><td>50</td><td>FMU_CH1_PROT</td><td>O</td><td>FMU PWM output channel 1</td></tr><tr><td>51</td><td>SPI_EXT_MOSI</td><td>O</td><td>External SPI, for debug only</td></tr><tr><td>52</td><td>FMU_CH2_PROT</td><td>O</td><td>FMU PWM output channel 2</td></tr><tr><td>53</td><td>VDD_SERVO</td><td>I</td><td>VDD_Servo, for monitoring servo bus</td></tr><tr><td>54</td><td>FMU_CH3_PROT</td><td>O</td><td>FMU PWM output channel 3</td></tr><tr><td>55</td><td>VDD_BRICK_VALID</td><td>I</td><td>Main power valid signal</td></tr><tr><td>56</td><td>FMU_CH4_PROT</td><td>O</td><td>FMU PWM output channel 4</td></tr><tr><td>57</td><td>VDD_BACKUP_VALID</td><td>I</td><td>Backup power valid signal</td></tr><tr><td>58</td><td>FMU_CH5_PROT</td><td>O</td><td>FMU PWM output channel 5</td></tr><tr><td>59</td><td>VBUS_VALID</td><td>I</td><td>USB bus valid signal</td></tr><tr><td>60</td><td>FMU_CH6_PROT</td><td>O</td><td>FMU PWM output channel 6</td></tr><tr><td>61</td><td>VDD_5V_IN_PROT</td><td>I</td><td>Main power (5V) into FMU from power selection</td></tr><tr><td>62</td><td>PPM_SBUS_PROT</td><td>I</td><td>PPM / S.Bus signal input</td></tr><tr><td>63</td><td>VDD_5V_IN_PROT</td><td>I</td><td>Main power (5V) into FMU from power selection</td></tr><tr><td>64</td><td>S.BUS_OUT</td><td>O</td><td>S.Bus signal output</td></tr><tr><td>65</td><td>IO_VDD_5V5</td><td>O</td><td>IO VDD 5.5 V</td></tr><tr><td>66</td><td>IO_CH8_PROT</td><td>O</td><td>I/O PWM output channel 8</td></tr><tr><td>67</td><td>SPI_EXT_MISO</td><td>I</td><td>External SPI, for debug only</td></tr><tr><td>68</td><td>IO_CH7_PROT</td><td>O</td><td>I/O PWM output channel 7</td></tr><tr><td>69</td><td>IO_SWDIO</td><td>I/O</td><td>I/O serial wire debug</td></tr><tr><td>70</td><td>IO_CH6_PROT</td><td>O</td><td>I/O PWM output channel 6</td></tr><tr><td>71</td><td>IO_SWCLK</td><td>O</td><td>I/O serial wire debug clock</td></tr><tr><td>72</td><td>IO_CH5_PROT</td><td>O</td><td>I/O PWM output channel 5</td></tr><tr><td>73</td><td>SPI_EXT_SCK</td><td>O</td><td>External SPI, for debug only</td></tr><tr><td>74</td><td>IO_CH4_PROT</td><td>O</td><td>I/O PWM output channel 4</td></tr><tr><td>75</td><td>IO_!RESET</td><td>I</td><td>I/O reset pin</td></tr><tr><td>76</td><td>IO_CH3_PROT</td><td>O</td><td>I/O PWM output channel 3</td></tr><tr><td>77</td><td>CAN_L_1</td><td>I/O</td><td>FMU CAN bus Low signal driver</td></tr><tr><td>78</td><td>IO_CH2_PROT</td><td>O</td><td>I/O PWM output channel 2</td></tr><tr><td>79</td><td>CAN_H_1</td><td>I/O</td><td>FMU CAN bus High signal driver</td></tr><tr><td>80</td><td>IO_CH1_PROT</td><td>O</td><td>I/O PWM output channel 1</td></tr></tbody></table>

## Serial Ports Parameter and Power Distribution

### SERIAL 1 / UART 1 | Connector： TELEM1

| Pin Number | Name                | Direction | Voltage           | Wire Color   | Caption                      |
| ---------- | ------------------- | --------- | ----------------- | ------------ | ---------------------------- |
| 1          | VCC\_5V             | OUT       | 5 V               | RED/GRAY     | VCC                          |
| 2          | SERIAL\_1\_TX       | OUT       | 3.3 V - 5.0 V TTL | YELLOW/BLACK | UART 1 TX (Transmit Data)    |
| 3          | SERIAL\_1\_RX       | IN        | 3.3 V - 5.0 V TTL | GREEN/BLACK  | UART 1 RX (Receive Data)     |
| 4          | SERIAL\_1\_CTS (TX) | OUT       | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 1 CTS (Clear To Send)   |
| 5          | SERIAL\_1\_RTS (RX) | IN        | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 1 RTS (Request To Send) |
| 6          | GND                 |           | GND               | BLACK        | GND                          |

### SERIAL 2 / UART 2 | Connector： TELEM2

| Pin Number | Name                | Direction | Voltage           | Wire Color   | Caption                      |
| ---------- | ------------------- | --------- | ----------------- | ------------ | ---------------------------- |
| 1          | VCC\_5V             | OUT       | 5 V               | RED/GRAY     | VCC                          |
| 2          | SERIAL\_2\_TX       | OUT       | 3.3 V - 5.0 V TTL | YELLOW/BLACK | UART 2 TX (Transmit Data)    |
| 3          | SERIAL\_2\_RX       | IN        | 3.3 V - 5.0 V TTL | GREEN/BLACK  | UART 2 RX (Receive Data)     |
| 4          | SERIAL\_2\_CTS (TX) | OUT       | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 2 CTS (Clear To Send)   |
| 5          | SERIAL\_2\_RTS (RX) | IN        | 3.3 V - 5.0 V TTL | GRAY/BLACK   | UART 2 RTS (Request To Send) |
| 6          | GND                 |           | GND               | BLACK        | GND                          |

### SERIAL 3 / UART 3 (GPS) / I2C 1 | Connector： GPS1

| Pin Number | Name                 | Direction | Voltage           | Wire Color | Caption                         |
| ---------- | -------------------- | --------- | ----------------- | ---------- | ------------------------------- |
| 1          | VCC\_5V              | IN        | 5 V               | RED        | VCC Power Supply To GPS From AP |
| 3          | SERIAL\_3\_TX        | OUT       | 3.3 V - 5.0 V TTL | BLACK      | UART 3 TX (Transmit Data)       |
| 2          | SERIAL\_3\_RX        | IN        | 3.3 V - 5.0 V TTL | BLACK      | UART 3 RX (Receive Data)        |
| 4          | I2C\_1\_SCL          | IN        | 3.3 V             | BLACK      | I2C 1 Clock Signal              |
| 5          | I2C\_1\_SDA          | IN/OUT    | 3.3 V             | BLACK      | I2C 1 Serial Data               |
| 6          | BUTTON               |           | GND               | BLACK      | Signal shorted to GND on press  |
| 7          | IO\_LED\_SAFET\_PROT |           | GND               | BLACK      | LED Driver For Safety Button    |
| 8          | GND                  |           | GND               | BLACK      | GND Connection                  |

### SERIAL 4 / UART 4 / I2C 2 | Connector： GPS2

| Pin NUmber | Name          | Direction | Voltage           | Wire Color   | Caption                         |
| ---------- | ------------- | --------- | ----------------- | ------------ | ------------------------------- |
| 1          | VCC\_5V       | OUT       | 5 V               | RED/GRAY     | VCC Power Supply To GPS From AP |
| 2          | SERIAL\_4\_TX | OUT       | 3.3 V - 5.0 V TTL | YELLOW/BLACK | UART 4 TX (Transmit Data)       |
| 3          | SERIAL\_4\_RX | IN        | 3.3 V - 5.0 V TTL | GREEN/BLACK  | UART 4 RX (Receive Data)        |
| 4          | I2C\_2\_SCL   | OUT       | 3.3 V - 5.0 V     | GRAY/BLACK   | I2C 2 Clock Signal              |
| 5          | I2C\_2\_SDA   | IN        | 3.3 V - 5.0 V     | GRAY/BLACK   | I2C 2 Serial Data               |
| 6          | GND           |           | GND               | BLACK        | GND                             |

### Buzzer | Connector： BUZZER

| Pin Number | Name   | Direction | Voltage         | Wire Color | Caption           |
| ---------- | ------ | --------- | --------------- | ---------- | ----------------- |
| 1          | BUZZER | OUT       | Battery voltage | GRAY/BLACK | VBAT (8.4 - 42 V) |
| 2          | GND    |           | GND             | BLACK      | GND Connection    |

### I2C 2 | Connector： I2C 2

| Pin Number | Name    | Direction | Voltage          | Wire Color  | Caption                       |
| ---------- | ------- | --------- | ---------------- | ----------- | ----------------------------- |
| 1          | VCC\_5V | OUT       | +5 V             | RED/GRAY    | Power supply                  |
| 2          | SCL     | IN/OUT    | +3.3 V (PULLUPS) | BLUE/BLACK  | SCL, 5 V level, pull-up on AP |
| 3          | SDA     | IN/OUT    | +3.3 V (PULLUPS) | GREEN/BLACK | SDA, 5 V level, pull-up on AP |
| 4          | GND     |           | GND              | BLACK       | GND Connection                |

### Main Power POWER 1 | Connector： POWER1

| Pin Number | Name                      | Direction | Voltage | Wire Color | Caption                       |
| ---------- | ------------------------- | --------- | ------- | ---------- | ----------------------------- |
| 1          | VDD\_5V\_BRICK            | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 2          | VDD\_5V\_BRICK            | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 3          | BATT\_CURRENT\_SENS\_PROT | IN        | 3.3 V   | BLACK      | Battery Current Connecter     |
| 4          | BATT\_VOLTAGE\_SENS\_PROT | IN        | 3.3 V   | BLACK      | Battery Voltage Connecter     |
| 5          | GND                       |           | GND     | BLACK      | GND                           |
| 6          | GND                       |           | GND     | BLACK      | GND                           |

### Backup Power POWER 2 | Connector： POWER2

| Pin Number | Name                     | Direction | Voltage | Wire Color | Caption                       |
| ---------- | ------------------------ | --------- | ------- | ---------- | ----------------------------- |
| 1          | VDD\_5V\_BRICK           | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 2          | VDD\_5V\_BRICK           | IN        | 5 V     | RED/GRAY   | Supply To AP from Power Brick |
| 3          | AUX\_BATT\_CURRENT\_SENS | IN        | 3.3 V   | BLACK      | Aux Battery Current Connecter |
| 4          | AUX\_BATT\_VOLTAGE\_SENS | IN        | 3.3 V   | BLACK      | Aux Battery Voltage Connecter |
| 5          | GND                      |           | GND     | BLACK      | GND Connection                |
| 6          | GND                      |           | GND     | BLACK      | GND                           |

### CAN | Connector： CAN2

| Pin Number | Name      | Direction | Voltage | Wire Color   | Caption          |
| ---------- | --------- | --------- | ------- | ------------ | ---------------- |
| 1          | VCC\_5V   | OUT       | 5 V     | RED/GRAY     | VCC Power Supply |
| 2          | CAN\_H\_2 | IN/OUT    | 12 V    | YELLOW/BLACK | CAN High         |
| 3          | CAN\_L\_2 | IN/OUT    | 12 V    | GREEN/BLACK  | CAN Low          |
| 4          | GND       |           | GND     | BLACK        | GND              |

### IO USART 1 / DSM | Connector： SPKT

| 1 | IO\_USART1\_RX\_SPECTRUM\_DSM | IN  |       | IO USART 1 RX, DSM INPUT |
| - | ----------------------------- | --- | ----- | ------------------------ |
| 2 | GND                           |     | GND   | GND                      |
| 3 | VDD\_3V3\_Spektrum            | OUT | 3.3 V | Independent Power Supply |

### CPPM / S.BUS / SERVO SYSTEM | Connector： RCIN MAIN OUT

| S - 1 | IO\_CH1\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| ----- | --------------- | ------ | ------------------------------------ | ------------------ |
| S - 2 | IO\_CH2\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 3 | IO\_CH3\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 4 | IO\_CH4\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 5 | IO\_CH5\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 6 | IO\_CH6\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 7 | IO\_CH7\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 8 | IO\_CH8\_PROT   | OUT    | 3.3 V Servo Signal, Servo Rail Power | PWM Signal         |
| S - 9 | PPM\_SBUS\_PROT | IN/OUT | 3.3 V / 4.5 V Powered                | PPM / S.Bus Signal |

## PPM S.bus Signal and SPKT Signal Switching

By default, the Mini carrier board uses PPM and S.bus (PPM/S.B) for the RC IN input. Specifically,

* Left center pad is connected to the 5V pad (provides power).
* Right center pad is connected to the PPM/S.B pad (receives the signal).

To modify the PCB to receive SPKT signals, complete the following steps:

1. Cut the existing connections:
   * Disconnect the left center pad from the 5V pad.
   * Disconnect the right center pad from the PPM/S.B pad.
2. Solder the new connections:
   * Connect the 3V3 pad to the left center pad.
   * Connect the SPKT pad to the right center pad.

![](<../../.gitbook/assets/Purple Cube and Mini Carrier Board -7.jpg>)

The following Github link can be used to revise and update the Mini carrier board informatio&#x6E;**:** \
[https://github.com/CubePilot/cubepilot-docs/edit/master/carrier-boards/mini-carrier-board.md](https://github.com/CubePilot/cubepilot-docs/edit/master/carrier-boards/mini-carrier-board.md)

# Ports Standard and Definition

### **Standard Carrier Board Ports Standard**

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
| `ETH`     | TE Multi-purp pluh(8P)      |

### <mark style="color:red;">Cube Red</mark> 80-Pin DF17 Connector

<figure><img src="../../.gitbook/assets/cube-bottom (1).png" alt="" width="340"><figcaption></figcaption></figure>

### **Connector 1 Assignments**

<table><thead><tr><th width="156">Pin Number</th><th width="124">Pin Type</th><th width="217">Pin Name</th><th width="256">Function</th></tr></thead><tbody><tr><td>1</td><td>I/O</td><td>FMU_SWDIO</td><td>FMU serial wire debug I/O</td></tr><tr><td>2</td><td>O</td><td>FMU_LED_AMBER</td><td>Boot error LED (drive only, controlled by FET)</td></tr><tr><td>3</td><td>O</td><td>FMU_SWCLK</td><td>FMU serial wire debug clock</td></tr><tr><td>4</td><td>I/O</td><td>I2C_2_SDA</td><td>I2C serial data Tx/Rx</td></tr><tr><td>5</td><td>O</td><td>EXTERN_CS</td><td>Chip select for external SPI (NC, just for debugging)</td></tr><tr><td>6</td><td>O</td><td>I2C_2_SCL</td><td>I2C serial clock signal</td></tr><tr><td>7</td><td>I</td><td>FMU_!RESET</td><td>Reset pin for the FMU</td></tr><tr><td>8</td><td>I/O</td><td>CAN_L_3</td><td>CAN bus low signal driver</td></tr><tr><td>9</td><td>I</td><td>VDD_SERVO_IN</td><td>Power for last resort I/O failsafe</td></tr><tr><td>10</td><td>I/O</td><td>CAN_H_3</td><td>CAN bus high signal driver</td></tr><tr><td>11</td><td>I</td><td>EXTERN_DRDY</td><td>Interrupt pin for external SPI (NC, just for debugging)</td></tr><tr><td>12</td><td>I</td><td>SERIAL_5_RX</td><td>UART 5 RX (receive data)</td></tr><tr><td>13</td><td></td><td>GND</td><td>System GND</td></tr><tr><td>14</td><td>O</td><td>SERIAL_5_TX</td><td>UART 5 TX (transmit data)</td></tr><tr><td>15</td><td></td><td>GND</td><td>System GND</td></tr><tr><td>16</td><td>I</td><td>SERIAL_4_RX</td><td>UART 4 RX (receive data)</td></tr><tr><td>17</td><td></td><td>SAFETY</td><td>Safety button input</td></tr><tr><td>18</td><td>O</td><td>SERIAL_4_TX</td><td>UART 4 TX (transmit data)</td></tr><tr><td>19</td><td>O</td><td>VDD_3V3_SPEKTRUM_EN</td><td>Enable for the Spektrum voltage regulator</td></tr><tr><td>20</td><td>I</td><td>SERIAL_3_RX</td><td>UART 3 RX (receive data)</td></tr><tr><td>21</td><td>AI</td><td>PRESSURE_SENS_IN</td><td>Analog signal port, for pressure sensor, laser range finder, or sonar</td></tr><tr><td>22</td><td>O</td><td>SERIAL_3_TX</td><td>UART 3 TX (transmit data)</td></tr><tr><td>23</td><td>AI</td><td>AUX_BATT_VOLTAGE_SENS</td><td>Voltage sense for Aux battery input</td></tr><tr><td>24</td><td>O</td><td>ALARM</td><td>Buzzer PWM signal</td></tr><tr><td>25</td><td>AI</td><td>AUX_BATT_CURRENT_SENS</td><td>Current sense for Aux battery input</td></tr><tr><td>26</td><td>I</td><td>IO_VDD_3V3</td><td>IO chip power, pinned through for debug</td></tr><tr><td>27</td><td>O</td><td>VDD_5V_PERIPH_EN</td><td>Enable voltage supply for peripherals</td></tr><tr><td>28</td><td>O</td><td>IO_LED_SAFET_PROT</td><td>IO-LED_SAFETY (safety LED) pinned out for IRIS</td></tr><tr><td>29</td><td>I</td><td>VBUS</td><td>USB VBus (VDD)</td></tr><tr><td>30</td><td></td><td>SERIAL_2_RTS</td><td>UART 2 RTS (request to send)</td></tr><tr><td>31</td><td>I/O</td><td>OTG_DP1</td><td>USB Data+ (D)</td></tr><tr><td>32</td><td></td><td>SERIAL_2_CTS</td><td>UART 2 CTS (clear to send)</td></tr><tr><td>33</td><td>I/O</td><td>OTG_DM1</td><td>USB Data- (M)</td></tr><tr><td>34</td><td>I</td><td>SERIAL_2_RX</td><td>UART 2 RX (receive data)</td></tr><tr><td>35</td><td>I/O</td><td>I2C_1_SDA</td><td>I2C serial data Tx/Rx</td></tr><tr><td>36</td><td>O</td><td>SERIAL_2_TX</td><td>UART 2 TX (transmit data)</td></tr><tr><td>37</td><td>O</td><td>I2C_1_SCL</td><td>I2C serial clock signal</td></tr><tr><td>38</td><td>I</td><td>SERIAL_1_RX</td><td>UART 1 RX (receive data)</td></tr><tr><td>39</td><td>I/O</td><td>CAN_L_2</td><td>FMU CAN bus low signal driver</td></tr><tr><td>40</td><td>O</td><td>SERIAL_1_TX</td><td>UART 1 TX (transmit data)</td></tr><tr><td>41</td><td>I/O</td><td>CAN_H_2</td><td>FMU CAN bus high signal driver</td></tr><tr><td>42</td><td></td><td>SERIAL_1_RTS</td><td>UART 1 RTS (request to send)</td></tr><tr><td>43</td><td>I</td><td>VDD_5V_PERIPH_OC</td><td>Error state message from peripheral power supply</td></tr><tr><td>44</td><td></td><td>SERIAL_1_CTS</td><td>UART 1 CTS (clear to send)</td></tr><tr><td>45</td><td>I</td><td>VDD_5V_HIPOWER_OC</td><td>Error state message from high power peripheral power supply</td></tr><tr><td>46</td><td>O</td><td>IO_USART_1_TX</td><td>I/O USART 1 TX</td></tr><tr><td>47</td><td>AI</td><td>BATT_VOLTAGE_SENS_PROT</td><td>Voltage sense from main battery</td></tr><tr><td>48</td><td>O</td><td>IO_USART1_RX_SPECTRUM_DSM</td><td>Signal from Spectrum receiver</td></tr><tr><td>49</td><td>AI</td><td>BATT_CURRENT_SENS_PROT</td><td>Current sense from main battery</td></tr><tr><td>50</td><td>O</td><td>FMU_CH1_PROT</td><td>FMU PWM Output Channel 1</td></tr><tr><td>51</td><td>O</td><td>SPI_EXT_MOSI</td><td>External SPI, for debug only</td></tr><tr><td>52</td><td>O</td><td>FMU_CH2_PROT</td><td>FMU PWM Output Channel 2</td></tr><tr><td>53</td><td>I</td><td>VDD_SERVO</td><td>VDD_Servo, for monitoring servo bus</td></tr><tr><td>54</td><td>O</td><td>FMU_CH3_PROT</td><td>FMU PWM Output Channel 3</td></tr><tr><td>55</td><td>I</td><td>VDD_BRICK_VALID</td><td>Main power valid signal</td></tr><tr><td>56</td><td>O</td><td>FMU_CH4_PROT</td><td>FMU PWM Output Channel 4</td></tr><tr><td>57</td><td>I</td><td>VDD_BACKUP_VALID</td><td>Backup power valid signal</td></tr><tr><td>58</td><td>O</td><td>FMU_CH5_PROT</td><td>FMU PWM Output Channel 5</td></tr><tr><td>59</td><td>I</td><td>VBUS_VALID</td><td>USB bus valid signal</td></tr><tr><td>60</td><td>O</td><td>FMU_CH6_PROT</td><td>FMU PWM Output Channel 6</td></tr><tr><td>61</td><td>I</td><td>VDD_5V_IN_PROT</td><td>Main power (5V) into FMU from power selection</td></tr><tr><td>62</td><td>I</td><td>PPM_SBUS_PROT</td><td>PPM / S.Bus signal input</td></tr><tr><td>63</td><td>I</td><td>VDD_5V_IN_PROT</td><td>Main power (5V) into FMU from power selection</td></tr><tr><td>64</td><td>O</td><td>S.BUS_OUT</td><td>S.Bus signal output</td></tr><tr><td>65</td><td>O</td><td>IO_VDD_5V5</td><td>IO VDD 5.5V</td></tr><tr><td>66</td><td>O</td><td>IO_CH8_PROT</td><td>I/O PWM Output Channel 8</td></tr><tr><td>67</td><td>I</td><td>SPI_EXT_MISO</td><td>External SPI, for debug only</td></tr><tr><td>68</td><td>O</td><td>IO_CH7_PROT</td><td>I/O PWM Output Channel 7</td></tr><tr><td>69</td><td>I/O</td><td>IO_SWDIO</td><td>I/O serial wire debug</td></tr><tr><td>70</td><td>O</td><td>IO_CH6_PROT</td><td>I/O PWM Output Channel 6</td></tr><tr><td>71</td><td>O</td><td>IO_SWCLK</td><td>I/O serial wire debug clock</td></tr><tr><td>72</td><td>O</td><td>IO_CH5_PROT</td><td>I/O PWM Output Channel 5</td></tr><tr><td>73</td><td>O</td><td>SPI_EXT_SCK</td><td>External SPI, for debug only</td></tr><tr><td>74</td><td>O</td><td>IO_CH4_PROT</td><td>I/O PWM Output Channel 4</td></tr><tr><td>75</td><td>I</td><td>IO_!RESET</td><td>I/O reset pin</td></tr><tr><td>76</td><td>O</td><td>IO_CH3_PROT</td><td>I/O PWM Output Channel 3</td></tr><tr><td>77</td><td>I/O</td><td>CAN_L_1</td><td>FMU CAN bus low signal driver</td></tr><tr><td>78</td><td>O</td><td>IO_CH2_PROT</td><td>I/O PWM Output Channel 2</td></tr><tr><td>79</td><td>I/O</td><td>CAN_H_1</td><td>FMU CAN bus high signal driver</td></tr><tr><td>80</td><td>O</td><td>IO_CH1_PROT</td><td>I/O PWM Output Channel 1</td></tr></tbody></table>

### **Connector 2 Assignments**

| Pin Number  | Pin Type | Pin Name            | Description                                   |
| ----------- | -------- | ------------------- | --------------------------------------------- |
| 1           |          | GND                 | System GND                                    |
| 2           | I        | FMU\_BOOT           | FMU boot                                      |
| 3           | I/O      | FC\_NET\_TX+        | Ethernet TX+,Auto-MDIX support                |
| 4           |          | NC                  | For future use                                |
| 5           |          | GND                 | System GND                                    |
| 6           |          | IO\_BOOT            | IO MCU boot                                   |
| 7           | I/O      | FC\_NET\_TX-        | Ethernet TX-, Auto-MDIX support               |
| 8           |          | NC                  | For future use                                |
| 9           |          | GND                 | System GND                                    |
| 10          |          | NC                  | For future use                                |
| 11          | I/O      | FC\_NET\_RX+        | Ethernet RX+, Auto-MDIX support               |
| 12          |          | NC                  | For future use                                |
| 13          |          | GND                 | System GND                                    |
| 14          |          | NC                  | For future use                                |
| 15          | I/O      | FC\_NET\_RX-        | Ethernet RX-, Auto-MDIX support               |
| 16          |          | NC                  | For future use                                |
| 17          |          | GND                 | System GND                                    |
| 18          |          | NC                  | For future use                                |
| 19          | O        | FC\_NET\_LEDY       | Link speed LED indication                     |
| 20          |          | NC                  | For future use                                |
| 21          | O        | FC\_NET\_LEDG       | Ethernet link activity LED indication         |
| 22          |          | NC                  | For future use                                |
| 23          | I        | FC\_NET\_VCC        | Ethernet 3.3V power in                        |
| 24          |          | NC                  | For future use                                |
| 25          | I        | Timestamp rtc       | Timestamp RTC                                 |
| 26          |          | NC                  | For future use                                |
| 27          |          | GND                 | System GND                                    |
| 28          |          | NC                  | For future use                                |
| 29          | I/O      | CAN\_L\_1           | CAN bus low signal driver                     |
| 30          |          | NC                  | For future use                                |
| 31          | I/O      | CAN\_H\_1           | CAN bus high signal driver                    |
| 32          |          | NC                  | For future use                                |
| 33          | I/O      | CAN\_L\_2           | CAN bus low signal driver                     |
| 34          |          | NC                  | For future use                                |
| 35          | I/O      | CAN\_H\_2           | CAN bus high signal driver                    |
| 36          |          | NC                  | For future use                                |
| 37          | I/O      | CAN\_L\_3           | CAN bus low signal driver                     |
| 38          |          | NC                  | For future use                                |
| 39          | I/O      | CAN\_H\_3           | CAN bus high signal driver                    |
| 40          |          | NC                  | For future use                                |
| 41          |          | GND                 | System GND                                    |
| 42          |          | NC                  | For future use                                |
| 43          | I        | UART8\_RX           | IO UART 8 RX (receive data)                   |
| 44          |          | NC                  | For future use                                |
| 45          | O        | UART8\_TX           | IO UART 8 TX (transmit data)                  |
| 46          |          | NC                  | For future use                                |
| 47          |          | GND                 | System GND                                    |
| 48          |          | NC                  | For future use                                |
| 49          | O        | DSI\_CKP            | MIPI DSI host clock postive                   |
| 50          |          | NC                  | For future use                                |
| 51          | O        | DSI\_CKN            | MIPI DSI host clock negative                  |
| 52          |          | NC                  | For future use                                |
| 53          |          | GND                 | System GND                                    |
| 54          |          | NC                  | For future use                                |
| 55          | O        | DSI\_D0P            | MIPI DSI host DATA0 postive                   |
| 56          |          | NC                  | For future use                                |
| 57          | O        | DSI\_D0N            | MIPI DSI host DATA0 negative                  |
| 58          |          | NC                  | For future use                                |
| 59          |          | GND                 | System GND                                    |
| 60          |          | NC                  | For future use                                |
| 61          | O        | DSI\_D1P            | MIPI DSI host DATA1 postive                   |
| 62          |          | NC                  | For future use                                |
| 63          | O        | DSI\_D1N            | MIPI DSI host DATA1 negative                  |
| 64          |          | NC                  | For future use                                |
| 65          |          | GND                 | System GND                                    |
| 66          |          | NC                  | For future use                                |
| 67          | O        | FMU\_DAC            | FMU analog output                             |
| 68          |          | NC                  | For future use                                |
| 69          | O        | IO\_DAC             | IO analog output                              |
| 70          |          | NC                  | For future use                                |
| 71          |          | GND                 | System GND                                    |
| 72          |          | NC                  | For future use                                |
| 73          | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 74          |          | NC                  | For future use                                |
| 75          | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 76          |          | NC                  | For future use                                |
| 77          | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 78          |          | NC                  | For future use                                |
| 79          | I        | VDD\_5V\_IN\_backup | Main power (5V) into FMU from power selection |
| 80          |          | NC                  | For future use                                |


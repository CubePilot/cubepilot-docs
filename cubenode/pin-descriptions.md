# Pin Descriptions

{% hint style="warning" %}
* If using Ethernet, do not use pin67, pin56, pin41, pin52, pin63, and pin40.
* If using SDMMC2, do not use pin11, pin48, and pin59.&#x20;
* Depending on the CubeNode version, the IMU may not be available.&#x20;
* Do not use pin12, pin85-pin95, pin98-pin100, pin103-pin105, pin108, and pin109. They are reserved for future use.
{% endhint %}

<figure><img src="../.gitbook/assets/CubeNode Pin descriptions.jpg" alt=""><figcaption></figcaption></figure>

| Pin Number | Pin Type | Pin Name      | Function      | Addtional Functions                                                        |
| ---------- | -------- | ------------- | ------------- | -------------------------------------------------------------------------- |
| 1          | I/O      | CAN1\_L       | CAN1\_L       |                                                                            |
| 2          | I/O      | CAN1\_H       | CAN1\_H       |                                                                            |
| 3          | I/O      | PE1           | UART8\_TX     | EVENTOUT                                                                   |
| 4          | I/O      | PE0           | UART8\_RX     | EVENTOUT                                                                   |
| 5          | I/O      | PB8           | I2C1\_SCL     | TIM16\_CH1,TIM4\_CH3,UART4\_RX,EVENTOUT                                    |
| 6          | I/O      | PB7           | I2C1\_SDA     | TIM17\_CH1N,TIM4\_CH2,USART1\_RX,EVENTOUT                                  |
| 7          | I/O      | PC10          | SPI3\_SCK     | USART3\_TX,UART4\_TX,EVENTOUT                                              |
| 8          | I/O      | PC11          | SPI3\_MISO    | USART3\_RX,UART4\_RX,EVENTOUT                                              |
| 9          | I/O      | PC12          | SPI3\_MOSI    | UART5\_TX,EVENTOUT                                                         |
| 10         | I/O      | PA10/PA8      | SPI3\_CS      | TIM1\_CH1,I2C3\_SCL,EVENTOUT                                               |
| 11         | I/O      | PB14          | UBLEDOUT      | TIM1\_CH2N,TIM12\_CH1,TIM8,CH2N,USART1\_TX,SPI2\_MISO,OTG\_HS\_DM,EVENTOUT |
| 12         |          | NC            | NC            |                                                                            |
| 13         | P        | VDD\_3V3      | VDD\_3V3      |                                                                            |
| 14         | I/O      | CAN2\_L       | CAN2\_L       |                                                                            |
| 15         | I/O      | CAN2\_H       | CAN2\_H       |                                                                            |
| 16         | I/O      | PA14          | SWCLK         |                                                                            |
| 17         | I/O      | PA13          | SWDIO         |                                                                            |
| 18         | I        | NRST          | NRST          |                                                                            |
| 19         | I        | BOOT0         | BOOT0         |                                                                            |
| 20         | I/O      | PE2           | GPIO\_PE2     | SPI4\_SCK,EVENTOUT                                                         |
| 21         | I/O      | PE10          | GPIO\_PE10    | TIM1\_CH2N,EVENTOUT                                                        |
| 22         | I/O      | PE8           | UART7\_TX     | TIM1\_CH1N,EVENTOUT                                                        |
| 23         | I/O      | PE7           | UART7\_RX     | EVENTOUT.                                                                  |
| 24         | P        | GND           | GND           |                                                                            |
| 25         | I/O      | PF3           | ADC3\_INP5    | EVENTOUT                                                                   |
| 26         | I/O      | PF5           | ADC3\_INP4    | EVENTOUT                                                                   |
| 27         | I/O      | PC3\_C        | ADC3\_INP1    | EVENTOUT                                                                   |
| 28         | I/O      | PC2\_C        | ADC3\_INP0    | SPI2\_MISO,ADC3\_INN1,EVENTOUT                                             |
| 29         | P        | GND           | GND           |                                                                            |
| 30         | I/O      | PC9           | TIM8\_CH4     | TIM3\_CH4,I2C3\_SDA,EVENTOUT                                               |
| 31         | I/O      | PC8           | TIM8\_CH3     | TIM3\_CH3,EVENTOUT                                                         |
| 32         | I/O      | PD15          | TIM4\_CH4     | EVENTOUT                                                                   |
| 33         | I/O      | PD14          | TIM4\_CH3     | EVENTOUT                                                                   |
| 34         | I/O      | PD13          | TIM4\_CH2     | I2C4\_SDA,EVENTOUT                                                         |
| 35         | I/O      | PD12          | TIM4\_CH1     | I2C4\_SCL,EVENTOUT                                                         |
| 36         | P        | GND           | GND           |                                                                            |
| 37         | I/O      | PF4           | ADC3\_INP9    | ADC3\_INN5,ADC3\_INP9,EVENTOUT                                             |
| 38         | I/O      | PF14          | ADC2\_INP6    | I2C4\_SCL,ADC2\_INN2,ADC2\_INP6,EVENTOUT                                   |
| 39         | I/O      | PF13          | ADC2\_INP2    | EVENTOUT                                                                   |
| 40         | I/O      | PC5           | ADC2\_INP8    | ADC12\_INN4,EVENTOUT                                                       |
| 41         | I/O      | PA7           | ADC2\_INP7    | TIM3\_CH2,TIM1\_CH1N,SPI1\_MOSI,TIM14\_CH1,EVENTOUT                        |
| 42         | P        | GND           | GND           |                                                                            |
| 43         | I/O      | PC7           | TIM8\_CH2     | USART6\_RX,TIM3\_CH2,EVENTOUT                                              |
| 44         | I/O      | PC6           | TIM8\_CH1     | USART6\_TX,TIM3\_CH1,EVENTOUT                                              |
| 45         | I/O      | PB1           | TIM3\_CH4     | TIM1\_CH3N,TIM8\_CH3N,TIM8\_CH3N,EVENTOUT                                  |
| 46         | I/O      | PB0           | TIM3\_CH3     | TIM1\_CH2N,TIM8\_CH2N,ADC12\_INN5,ADC12\_INP9,EVENTOUT                     |
| 47         | I/O      | PE6           | TIM15\_CH2    | SPI4\_MOSI,EVENTOUT                                                        |
| 48         | I/O      | PB4           | TIM3\_CH1     | SPI1\_MISO,EVENTOUT                                                        |
| 49         | P        | GND           | GND           |                                                                            |
| 50         | I/O      | PA5           | ADC1\_INP19   | TIM2\_CH1,TIM8\_CH1N,SPI1\_SCK,EVENTOUT                                    |
| 51         | I/O      | PA4           | ADC1\_INP18   | DAC1\_OUT1,EVENTOUT                                                        |
| 52         | I/O      | PC1           | ADC1\_INP11   | SPI2\_MOSI,EVENTOUT                                                        |
| 53         | I/O      | PC0           | ADC1\_INP10   | EVENTOUT                                                                   |
| 54         | P        | GND           | GND           |                                                                            |
| 55         | I/O      | PA3           | TIM5\_CH4     | TIM2\_CH4,TIM15\_CH2,USART2\_RX,ADC12\_INP15,EVENTOUT                      |
| 56         | I/O      | PA2           | TIM5\_CH3     | TIM2\_CH3,TIM15\_CH1,USART2\_TX,ADC12\_INP14,EVENTOUT                      |
| 57         | I/O      | PE5           | TIM15\_CH1    | SPI4\_MISO,EVENTOUT                                                        |
| 58         | I/O      | PB10          | TIM2\_CH3     | I2C2\_SCL,SPI2\_SCK,USART3\_TX,EVENTOUT                                    |
| 59         | I/O      | PB3           | TIM2\_CH2     | SPI1\_SCK,EVENTOUT                                                         |
| 60         | I/O      | PA15          | TIM2\_CH1     | EVENTOUT                                                                   |
| 61         | P        | GND           | GND           |                                                                            |
| 62         | I/O      | PF12          | ADC1\_INP6    | ADC1\_INN2,EVENTOUT                                                        |
| 63         | I/O      | PC4           | ADC1\_INP4    | EVENTOUT                                                                   |
| 64         | I/O      | PA6           | ADC1\_INP3    | TIM3\_CH1,SPI1\_MISO,TIM13\_CH1,EVENTOUT                                   |
| 65         | I/O      | PF11          | ADC1\_INP2    | ADC1\_INP2,EVENTOUT                                                        |
| 66         | P        | GND           | GND           |                                                                            |
| 67         | I/O      | PA1           | TIM5\_CH2     | TIM2\_CH2,UART4\_RX,ADC1\_INN16,ADC1\_INP17,EVENTOUT                       |
| 68         | I/O      | PA0           | TIM5\_CH1     | TIM2\_CH1,UART4\_TX,ADC1\_INP16,EVENTOUT                                   |
| 69         | I/O      | PE14          | TIM1\_CH4     | SPI4\_MOSI,EVENTOUT                                                        |
| 70         | I/O      | PE13          | TIM1\_CH3     | SPI4\_MISO,EVENTOUT                                                        |
| 71         | I/O      | PE11          | TIM1\_CH2     | EVENTOUT                                                                   |
| 72         | I/O      | PE9           | TIM1\_CH1     | EVENTOUT                                                                   |
| 73         | P        | GND           | GND           |                                                                            |
| 74         | P        | GND           | GND           |                                                                            |
| 75         | I/O      | PA12          | OTG\_FS\_DP   | UART4\_TX,EVENTOUT                                                         |
| 76         | I/O      | PA11          | OTG\_FS\_DM   | TIM1\_CH4,UART4\_RX,EVENTOUT                                               |
| 77         | P        | PA9           | VBUS          |                                                                            |
| 78         | P        | VDD\_5V       | VDD\_5V       |                                                                            |
| 79         | I/O      | ETHERNET\_TX- | ETHERNET\_TX- |                                                                            |
| 80         | I/O      | ETHERNET\_TX+ | ETHERNET\_TX+ |                                                                            |
| 81         | I/O      | ETHERNET\_RX- | ETHERNET\_RX- |                                                                            |
| 82         | I/O      | ETHERNET\_RX+ | ETHERNET\_RX+ |                                                                            |
| 83-84      | P        | GND           | GND           |                                                                            |
| 85-95      |          | NC            | NC            |                                                                            |
| 96-97      | P        | GND           | GND           |                                                                            |
| 98-100     |          | NC            | NC            |                                                                            |
| 101        | I/O      | PB15          | SDMMC2\_D1    | TIM1\_CH3N,TIM12\_CH2,TIM8\_CH3N,USART1\_RX,OTG\_HS\_DP,EVENTOUT           |
| 102        | I/O      | PB14          | SDMMC2\_D0    | TIM1\_CH2N,TIM12\_CH1,TIM8,CH2N,USART1\_TX,SPI2\_MISO,OTG\_HS\_DM,EVENTOUT |
| 103-105    |          | NC            | NC            |                                                                            |
| 106        | I/O      | PB3           | SDMMC2\_D2    | TIM2\_CH2,SPI1\_SCK,EVENTOUT                                               |
| 107        | I/O      | PB4           | SDMMC2\_D3    | TIM3\_CH1,SPI1\_MISO,EVENTOUT                                              |
| 108-109    |          | NC            | NC            |                                                                            |
| 110        | I/O      | PD6           | SDMMC2\_CK    | USART2\_RX,EVENTOUT                                                        |
| 111        | I/O      | PD7           | SDMMC2\_CMD   | SPI1\_MOSI,EVENTOUT                                                        |

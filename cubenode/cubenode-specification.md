# CubeNode Specification

## Dual core

* 32-bit Arm® Cortex®-M7 core with double precision FPU and L1 cache: 16 Kbytes of data and 16 Kbytes of instruction cache; frequency up to 480 MHz, MPU, 1027 DMIPS/2.14 DMIPS /MHz (Dhrystone 2.1), and DSP instructions
* 32-bit Arm® 32-bit Cortex®-M4 core with FPU, Adaptive real-time accelerator (ART AcceleratorTM) for internal Flash memory and external memories, frequency up to 240 MHz, MPU, 300 DMIPS/1.25 DMIPS /MHz (Dhrystone 2.1), and DSP instruction

## Memories

* Up to 2 Mbytes of Flash memory with readwhile-write support
* 1 Mbyte of RAM: 192 Kbytes of TCM RAM (inc. 64 Kbytes of ITCM RAM + 128 Kbytes of DTCM RAM for time critical routines), 864 Kbytes of user SRAM, and 4 Kbytes of SRAM in Backup domain
* CRC calculation unit

## Security

* ROP,PC-ROP, active tamper, secure firmware upgrade support, Secure access mode

## Communication peripherals

* 2 x CANFD
* 2 x UARTs/USARTs
* 1 x 10/100Mb Ethernet Phy
* 1 x SPI
* 1 x I2C
* 1 x USB
* 1 x SDMMC
* 3 axis Accelerometer
* 3 axis Gyroscope

## Contents

**1.Description**\
**2.Functional overview**\
**2.1 Dual Arm® Cortex® cores**\
**2.2 Memory protection unit (MPU)**\
**2.3 Embedded Flash memory**\
**2.4 Boot modes**\
**2.5 Reset and clock controller (RCC)**\
**2.5.1 System reset sources**\
**2.6 General-purpose input/outputs (GPIOs)**\
**2.7 Analog-to-digital converters (ADCs)**\
**2.8 Inter-integrated circuit interface (I2C)**\
**2.9 Universal asynchronous receiver transmitter (UART)**\
**2.10 Controller area network (FDCAN1, FDCAN2)**\
**2.11 USB**\
**2.12 3 axis Accelerometer**\
**2.13 3 axis Gyroscope**\
**2.14 Ethernet interface**\
**3.Pin descriptions**

## 1 Description

CubeNode are based on the high-performance Arm® Cortex®-M7 and Cortex®- M4 32-bit RISC cores.The Cortex®-M7 core operates at up to 480 MHz and the Cortex®- M4 core at up to 240 MHz. Both cores feature a floating point unit (FPU) which supports Arm® single- and double- precision (Cortex®-M7 core) operations and conversions (IEEE 754 compliant), including a full set of DSP instructions and a memory protection unit (MPU) to enhance application security.

CubeNode incorporate high-speed embedded memories with a dual-bank Flash memory of 2 Mbytes, up to 1 Mbyte of RAM (including 192 Kbytes of TCM RAM, up to 864 Kbytes of user SRAM and 4 Kbytes of backup SRAM), as well as an extensive range of enhanced I/O.

* **Standard peripherals** \
  One I2C\
  Two CANFD\
  One UART, One USART\
  One Ethernet\
  One SPI\
  One USB\
  One SDMMC

## 2 Functional overview&#x20;

### 2.1 Dual Arm® Cortex® cores

The dual-core CubeNode embed two Arm® cores, a Cortex®-M7 and a\
Cortex®-M4 offers optimal performance for real-time applications while the Cortex®-M7 core can execute high-performance tasks in parallel. The two cores belong to separate power domains. This allows designing gradual highpower efficiency solutions in combination with the low-power modes.

### 2.2 Memory protection unit (MPU)

The devices feature two memory protection units. Each MPU manages the CPU access rights and the attributes of the system resources. It has to be programmed and enabled before use. Its main purposes are to prevent an untrusted user program to accidentally corrupt data used by the OS and/or by a privileged task, but also to protect data processes or read-protect memory regions. The MPU defines access rules for privileged accesses and user program accesses. It allows defining up to 16 protected regions that can in turn be divided into up to 8 independent subregions, where region address, size, and attributes can be configured. The protection area ranges from 32 bytes to 4 Gbytes of addressable memory. When an unauthorized access is performed, a memory management exception is generated.

### 2.3 Embedded Flash memory

The CubeNode embed 2 Mbytes of Flash memory that can be used for storing programs and data. The Flash memory is organized as 266-bit Flash words memory that can be used for storing both code and data constants. Each word consists of:

One Flash word (8 words, 32 bytes or 256 bits)\
10 ECC bits.

The Flash memory is divided into two independent banks. Each bank is organized as follows:

1 Mbyte of user Flash memory block containing eight user sectors of 128 Kbytes (4 K Flash memory words) • 128 Kbytes of System Flash memory from which the device can boot\
2 Kbytes (64 Flash words) of user option bytes for user configuration

### 2.5 Reset and clock controller (RCC)

The RCC manages the generation of all the clocks, as well as the clock gating and the control of the system and peripheral resets. It provides a high flexibility in the choice of clock sources and allows to apply clock ratios to improve the power consumption. In addition, on some communication peripherals that are capable to work with two different clock domains (either a bus interface clock or a kernel peripheral clock), the system frequency can be changed without modifying the baudrate.

Cortex®-M4. The

#### 2.5.1 System reset sources

Power-on reset initializes all registers while system reset reinitializes the system except for the debug, part of the RCC and power controller status registers, as well as the backup power domain.

A system reset is generated in the following cases:

Power-on reset (pwr\_por\_rst)\
Brownout reset\
Low level on NRST pin (external reset)\
Independent watchdog 1 (from D1 domain)\
Independent watchdog 2 (from D2 domain)\
Window watchdog 1\
Window watchdog 2\
Software reset\
Low-power mode security reset\
Exit from Standby

### 2.6 General-purpose input/outputs (GPIOs)

Each of the GPIO pins can be configured by software as output (push-pull or open-drain, with or without pull-up or pull-down), as input (floating, with or without pull-up or pull-down) or as peripheral alternate function. Most of the GPIO pins are shared with digital or analog alternate functions. All GPIOs are high-current-capable and have speed selection to better manage internal noise, power consumption and electromagnetic emission. After reset, all GPIOs (except debug pins) are in Analog mode to reduce power consumption (refer to GPIOs register reset values in the device reference manual). The I/O configuration can be locked if needed by following a specific sequence in order to avoid spurious writing to the I/Os registers.

### 2.7 Analog-to-digital converters (ADCs)

The STM32H757xI devices embed three analog-to-digital converters, which resolution can be configured to 16, 14, 12, 10 or 8 bits.

Additional logic functions embedded in the ADC interface allow:

* Simultaneous sample and hold
* Interleaved sample and hold

The ADC can be served by the DMA controller, thus allowing to automatically transfer ADC converted values to a destination location without any software action.

In addition, an analog watchdog feature can accurately monitor the converted voltage of one, some or all selected channels. An interrupt is generated when the converted voltage is outside the programmed thresholds.

### 2.8 Inter-integrated circuit interface (I2C)

CubeNode embed one I2C interface.

The I2C bus interface handles communications between the microcontroller and the serial I2C bus. It controls all I2C bus-specific sequencing, protocol, arbitration and timing.

The I2C peripheral supports:

* I2C-bus specification and user manual rev. 5 compatibility:

\- Slave and Master modes, multimaster capability\
\-  Standard-mode (Sm), with a bitrate up to 100 kbit/s\
\-  Fast-mode (Fm), with a bitrate up to 400 kbit/s\
\-  Fast-mode Plus (Fm+), with a bitrate up to 1 Mbit/s and 20 mA output drive I/Os\
\-  7-bit and 10-bit addressing mode, multiple 7-bit slave addresses\
\-  Programmable setup and hold times\
\-  Optional clock stretching

* System Management Bus (SMBus) specification rev 2.0 compatibility:

\-  Hardware PEC (Packet Error Checking) generation and verification with ACK control\
\-  Address resolution protocol (ARP) support\
\-  SMBus alert

Power System Management Protocol (PMBus) specification rev 1.1 compatibility

Independent clock: a choice of independent clock sources allowing the I2C communication speed to be independent from the PCLK reprogramming.\
\
Wakeup from Stop mode on address match\
\
Programmable analog and digital noise filters\
\
1-byte buffer with DMA capability

### 2.9 Universal asynchronous receiver transmitter (USART)

CubeNode have two embedded universal asynchronou receiver transmitters (UART7 and UART8)

### 2.10 Controller area network (FDCAN1, FDCAN2)

The controller area network (CAN) subsystem consists of two CAN modules, a shared message RAM memory and a clock calibration unit.

It have the features:

* Supports CAN 2.0 and CAN with Flexible Data-Rate (CAN FD) Physical Layer Transceiver Requirements
* Optimized for CAN FD at 2, 5 and 8 Mbps Operation:

\-  Maximum propagation delay: 120 ns

\-  Loop delay symmetry: -10%/+10% (2 Mbps)

* Qualified According to AEC-Q100 Rev. G&#x20;
* Automatic Thermal Shutdown Protection
* Detection of Ground Fault:

\-  Permanent dominant detection on TXD

\-  Permanent dominant detection on bus

* Automatic Thermal Shutdown Protection
* Suitable for 12V and 24V Systems

### 2.11 USB

The CubeNode embed an USB OTG full-speed device/host/OTG peripheral with integrated transceivers. The USB OTG FS peripheral is compliant with the USB 2.0 specification.

### 2.12 3 axis Accelerometer

The CubeNode includes industry first 20-bits data format support in FIFO for high-data resolution. This FIFO format encapsulates 18- bits of accelerometer data.

* User selectable Accelerometer Full-scale range (g): ± 2/4/8/16.

### 2.13 3 axis Gyroscope

The CubeNode includes industry first 20-bits data format support in FIFO for high-data resolution. This FIFO format encapsulates 19-bits of gyroscope data.

User selectable Gyro Full-scale range (dps): ± 15.6/31.2/62.5/125/250/500/1000/2000.

### 2.14 Ethernet interface

The CubeNode include high-performance 10/100 Ethernet transceiver.It have the features:

* Compliant with IEEE802.3/802.3u (Fast Ethernet)
* Compliant with ISO 802-3/IEEE 802.3 (10BASE-T)&#x20;
* Loop-back modes
* Auto-negotiation
* Automatic polarity detection and correction
* Vendor specific register functions
* HP Auto-MDIX support
* Integrated power-on reset circuit

## 3.Pin descriptions

<figure><img src="../.gitbook/assets/CubeNode Pin descriptions.jpg" alt=""><figcaption></figcaption></figure>

<table><thead><tr><th width="110">Num Pins</th><th width="81">Pin Type</th><th width="102">Pin Name</th><th width="117">Function</th><th>Addtional Functions</th></tr></thead><tbody><tr><td>1</td><td>I/O</td><td>CAN1_L</td><td>CAN1_L</td><td></td></tr><tr><td>2</td><td>I/O</td><td>CAN1_H</td><td>CAN1_H</td><td></td></tr><tr><td>3</td><td>I/O</td><td>PE1</td><td>UART8_TX</td><td>EVENTOUT</td></tr><tr><td>4</td><td>I/O</td><td>PE0</td><td>UART8_RX</td><td>EVENTOUT</td></tr><tr><td>5</td><td>I/O</td><td>PB8</td><td>I2C1_SCL</td><td>TIM16_CH1,TIM4_CH3,UART4_RX,EVENTOUT</td></tr><tr><td>6</td><td>I/O</td><td>PB7</td><td>I2C1_SDA</td><td>TIM17_CH1N,TIM4_CH2,USART1_RX,EVENTOUT</td></tr><tr><td>7</td><td>I/O</td><td>PC10</td><td>SPI3_SCK</td><td>USART3_TX,UART4_TX,EVENTOUT</td></tr><tr><td>8</td><td>I/O</td><td>PC11</td><td>SPI3_MISO</td><td>USART3_RX,UART4_RX,EVENTOUT</td></tr><tr><td>9</td><td>I/O</td><td>PC12</td><td>SPI3_MOSI</td><td>UART5_TX,EVENTOUT</td></tr><tr><td>10</td><td>I/O</td><td>PA10/PA8</td><td>SPI3_CS</td><td>TIM1_CH1,I2C3_SCL,EVENTOUT</td></tr><tr><td>11</td><td>I/O</td><td>PB14</td><td>UBLEDOUT</td><td>TIM1_CH2N,TIM12_CH1,TIM8,CH2N,USART1_TX,SPI2_MISO,OTG_HS_DM,EVENTOUT</td></tr><tr><td>12</td><td></td><td>NC</td><td>NC</td><td></td></tr><tr><td>13</td><td>P</td><td>VDD_3V3</td><td>VDD_3V3</td><td></td></tr><tr><td>14</td><td>I/O</td><td>CAN2_L</td><td>CAN2_L</td><td></td></tr><tr><td>15</td><td>I/O</td><td>CAN2_H</td><td>CAN2_H</td><td></td></tr><tr><td>16</td><td>I/O</td><td>PA14</td><td>SWCLK</td><td></td></tr><tr><td>17</td><td>I/O</td><td>PA13</td><td>SWDIO</td><td></td></tr><tr><td>18</td><td>I</td><td>NRST</td><td>NRST</td><td></td></tr><tr><td>19</td><td>I</td><td>BOOT0</td><td>BOOT0</td><td></td></tr><tr><td>20</td><td>I/O</td><td>PE2</td><td>GPIO_PE2</td><td>SPI4_SCK,EVENTOUT</td></tr><tr><td>21</td><td>I/O</td><td>PE10</td><td>GPIO_PE10</td><td>TIM1_CH2N,EVENTOUT</td></tr><tr><td>22</td><td>I/O</td><td>PE8</td><td>UART7_TX</td><td>TIM1_CH1N,EVENTOUT</td></tr><tr><td>23</td><td>I/O</td><td>PE7</td><td>UART7_RX</td><td>EVENTOUT.</td></tr><tr><td>24</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>25</td><td>I/O</td><td>PF3</td><td>ADC3_INP5</td><td>EVENTOUT</td></tr><tr><td>26</td><td>I/O</td><td>PF5</td><td>ADC3_INP4</td><td>EVENTOUT</td></tr><tr><td>27</td><td>I/O</td><td>PC3_C</td><td>ADC3_INP1</td><td>EVENTOUT</td></tr><tr><td>28</td><td>I/O</td><td>PC2_C</td><td>ADC3_INP0</td><td>SPI2_MISO,ADC3_INN1,EVENTOUT</td></tr><tr><td>29</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>30</td><td>I/O</td><td>PC9</td><td>TIM8_CH4</td><td>TIM3_CH4,I2C3_SDA,EVENTOUT</td></tr><tr><td>31</td><td>I/O</td><td>PC8</td><td>TIM8_CH3</td><td>TIM3_CH3,EVENTOUT</td></tr><tr><td>32</td><td>I/O</td><td>PD15</td><td>TIM4_CH4</td><td>EVENTOUT</td></tr><tr><td>33</td><td>I/O</td><td>PD14</td><td>TIM4_CH3</td><td>EVENTOUT</td></tr><tr><td>34</td><td>I/O</td><td>PD13</td><td>TIM4_CH2</td><td>I2C4_SDA,EVENTOUT</td></tr><tr><td>35</td><td>I/O</td><td>PD12</td><td>TIM4_CH1</td><td>I2C4_SCL,EVENTOUT</td></tr><tr><td>36</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>37</td><td>I/O</td><td>PF4</td><td>ADC3_INP9</td><td>ADC3_INN5,ADC3_INP9,EVENTOUT</td></tr><tr><td>38</td><td>I/O</td><td>PF14</td><td>ADC2_INP6</td><td>I2C4_SCL,ADC2_INN2,ADC2_INP6,EVENTOUT</td></tr><tr><td>39</td><td>I/O</td><td>PF13</td><td>ADC2_INP2</td><td>EVENTOUT</td></tr><tr><td>40</td><td>I/O</td><td>PC5</td><td>ADC2_INP8</td><td>ADC12_INN4,EVENTOUT</td></tr><tr><td>41</td><td>I/O</td><td>PA7</td><td>ADC2_INP7</td><td>TIM3_CH2,TIM1_CH1N,SPI1_MOSI,TIM14_CH1,EVENTOUT</td></tr><tr><td>42</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>43</td><td>I/O</td><td>PC7</td><td>TIM8_CH2</td><td>USART6_RX,TIM3_CH2,EVENTOUT</td></tr><tr><td>44</td><td>I/O</td><td>PC6</td><td>TIM8_CH1</td><td>USART6_TX,TIM3_CH1,EVENTOUT</td></tr><tr><td>45</td><td>I/O</td><td>PB1</td><td>TIM3_CH4</td><td>TIM1_CH3N,TIM8_CH3N,TIM8_CH3N,EVENTOUT</td></tr><tr><td>46</td><td>I/O</td><td>PB0</td><td>TIM3_CH3</td><td>TIM1_CH2N,TIM8_CH2N,ADC12_INN5,ADC12_INP9,EVENTOUT</td></tr><tr><td>47</td><td>I/O</td><td>PE6</td><td>TIM15_CH2</td><td>SPI4_MOSI,EVENTOUT</td></tr><tr><td>48</td><td>I/O</td><td>PB4</td><td>TIM3_CH1</td><td>SPI1_MISO,EVENTOUT</td></tr><tr><td>49</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>50</td><td>I/O</td><td>PA5</td><td>ADC1_INP19</td><td>TIM2_CH1,TIM8_CH1N,SPI1_SCK,EVENTOUT</td></tr><tr><td>51</td><td>I/O</td><td>PA4</td><td>ADC1_INP18</td><td>DAC1_OUT1,EVENTOUT</td></tr><tr><td>52</td><td>I/O</td><td>PC1</td><td>ADC1_INP11</td><td>SPI2_MOSI,EVENTOUT</td></tr><tr><td>53</td><td>I/O</td><td>PC0</td><td>ADC1_INP10</td><td>EVENTOUT</td></tr><tr><td>54</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>55</td><td>I/O</td><td>PA3</td><td>TIM5_CH4</td><td>TIM2_CH4,TIM15_CH2,USART2_RX,ADC12_INP15,EVENTOUT</td></tr><tr><td>56</td><td>I/O</td><td>PA2</td><td>TIM5_CH3</td><td>TIM2_CH3,TIM15_CH1,USART2_TX,ADC12_INP14,EVENTOUT</td></tr><tr><td>57</td><td>I/O</td><td>PE5</td><td>TIM15_CH1</td><td>SPI4_MISO,EVENTOUT</td></tr><tr><td>58</td><td>I/O</td><td>PB10</td><td>TIM2_CH3</td><td>I2C2_SCL,SPI2_SCK,USART3_TX,EVENTOUT</td></tr><tr><td>59</td><td>I/O</td><td>PB3</td><td>TIM2_CH2</td><td>SPI1_SCK,EVENTOUT</td></tr><tr><td>60</td><td>I/O</td><td>PA15</td><td>TIM2_CH1</td><td>EVENTOUT</td></tr><tr><td>61</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>62</td><td>I/O</td><td>PF12</td><td>ADC1_INP6</td><td>ADC1_INN2,EVENTOUT</td></tr><tr><td>63</td><td>I/O</td><td>PC4</td><td>ADC1_INP4</td><td>EVENTOUT</td></tr><tr><td>64</td><td>I/O</td><td>PA6</td><td>ADC1_INP3</td><td>TIM3_CH1,SPI1_MISO,TIM13_CH1,EVENTOUT</td></tr><tr><td>65</td><td>I/O</td><td>PF11</td><td>ADC1_INP2</td><td>ADC1_INP2,EVENTOUT</td></tr><tr><td>66</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>67</td><td>I/O</td><td>PA1</td><td>TIM5_CH2</td><td>TIM2_CH2,UART4_RX,ADC1_INN16,ADC1_INP17,EVENTOUT</td></tr><tr><td>68</td><td>I/O</td><td>PA0</td><td>TIM5_CH1</td><td>TIM2_CH1,UART4_TX,ADC1_INP16,EVENTOUT</td></tr><tr><td>69</td><td>I/O</td><td>PE14</td><td>TIM1_CH4</td><td>SPI4_MOSI,EVENTOUT</td></tr><tr><td>70</td><td>I/O</td><td>PE13</td><td>TIM1_CH3</td><td>SPI4_MISO,EVENTOUT</td></tr><tr><td>71</td><td>I/O</td><td>PE11</td><td>TIM1_CH2</td><td>EVENTOUT</td></tr><tr><td>72</td><td>I/O</td><td>PE9</td><td>TIM1_CH1</td><td>EVENTOUT</td></tr><tr><td>73</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>74</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>75</td><td>I/O</td><td>PA12</td><td>OTG_FS_DP</td><td>UART4_TX,EVENTOUT</td></tr><tr><td>76</td><td>I/O</td><td>PA11</td><td>OTG_FS_DM</td><td>TIM1_CH4,UART4_RX,EVENTOUT</td></tr><tr><td>77</td><td>P</td><td>PA9</td><td>VBUS</td><td></td></tr><tr><td>78</td><td>P</td><td>VDD_5V</td><td>VDD_5V</td><td></td></tr><tr><td>79</td><td>I/O</td><td>ETHERNET_TX-</td><td>ETHERNET_TX-</td><td></td></tr><tr><td>80</td><td>I/O</td><td>ETHERNET_TX+</td><td>ETHERNET_TX+</td><td></td></tr><tr><td>81</td><td>I/O</td><td>ETHERNET_RX-</td><td>ETHERNET_RX-</td><td></td></tr><tr><td>82</td><td>I/O</td><td>ETHERNET_RX+</td><td>ETHERNET_RX+</td><td></td></tr><tr><td>83-84</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>85-95</td><td></td><td>NC</td><td>NC</td><td></td></tr><tr><td>96-97</td><td>P</td><td>GND</td><td>GND</td><td></td></tr><tr><td>98-100</td><td></td><td>NC</td><td>NC</td><td></td></tr><tr><td>101</td><td>I/O</td><td>PB15</td><td>SDMMC2_D1</td><td>TIM1_CH3N,TIM12_CH2,TIM8_CH3N,USART1_RX,OTG_HS_DP,EVENTOUT</td></tr><tr><td>102</td><td>I/O</td><td>PB14</td><td>SDMMC2_D0</td><td>TIM1_CH2N,TIM12_CH1,TIM8,CH2N,USART1_TX,SPI2_MISO,OTG_HS_DM,EVENTOUT</td></tr><tr><td>103-105</td><td></td><td>NC</td><td>NC</td><td></td></tr><tr><td>106</td><td>I/O</td><td>PB3</td><td>SDMMC2_D2</td><td>TIM2_CH2,SPI1_SCK,EVENTOUT</td></tr><tr><td>107</td><td>I/O</td><td>PB4</td><td>SDMMC2_D3</td><td>TIM3_CH1,SPI1_MISO,EVENTOUT</td></tr><tr><td>108-109</td><td></td><td>NC</td><td>NC</td><td></td></tr><tr><td>110</td><td>I/O</td><td>PD6</td><td>SDMMC2_CK</td><td>USART2_RX,EVENTOUT</td></tr><tr><td>111</td><td>I/O</td><td>PD7</td><td>SDMMC2_CMD</td><td>SPI1_MOSI,EVENTOUT</td></tr></tbody></table>

\*If using Ethernet,do not use pin67,pin56,pin41,pin52,pin63,pin40

\*If using SDMMC2,please do not use pin11,pin48,pin59&#x20;

\*The CubeNode would not have IMU in first batch&#x20;

\*The Pin83-pin111 would not have in the first batch&#x20;

\*Pin85-pin95,pin96-pin100,pin103-105,pin108-109. please do not connect..It is for future use

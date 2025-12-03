# Specifications

The CubeNode provides a platform to develop, create, test, and refine components such as navigation systems, communication modules, sensors, payloads, and more.&#x20;

{% hint style="info" %}
Depending on the CubeNode version, some features may be unavailable.&#x20;
{% endhint %}

{% hint style="info" %}
The CubeNode should undergo reflow soldering only once. For a two-sided assembly, ensure the device is soldered during the second pass through the line. If it is unable to run through the second pass, use reflow-safe underfill. Failure to comply may result in permanent damage to the device. &#x20;
{% endhint %}

The following lists the CubeNode specification.&#x20;

## **Microcontroller (Dual-Core)**

### 32-bit Arm® Cortex®-M7 core

* Double precision FPU
* L1 cache: 16 Kbytes of data cache and 16 Kbytes of instruction cache&#x20;
* Frequency: Up to 480 MHz&#x20;
* Memory Protection Unit (MPU)&#x20;
* 1027 DMIPS/2.14 DMIPS/MHz (Dhrystone 2.1) DSP instructions

### 32-bit Arm® 32-bit Cortex®-M4 core

* FPU&#x20;
* Adaptive real-time accelerator for internal Flash memory and external memory&#x20;
* Frequency: Up to 240 MHz&#x20;
* MPU&#x20;
* 300 DMIPS/1.25 DMIPS /MHz (Dhrystone 2.1) DSP instructions

## Memory

* 2 Mbytes of Flash memory with read / write support
* 1 Mbyte of RAM&#x20;
  * 192 Kbytes of TCM RAM (including 64 Kbytes of ITCM RAM + 128 Kbytes of DTCM RAM for time critical routines), 864 Kbytes of SRAM, and 4 Kbytes of backup SRAM
* Cyclic redundancy check (CRC) calculation unit

## Security

* Read-out protection (ROP) &#x20;
* Proprietary code read-out protection (PC-ROP)
* Active tamper
* Secure firmware upgrade support&#x20;
* Secure access mode

## Communication Peripherals

* 2 x CAN FD
* 1 x USB
* 1 x SDMMC
* 1 x 10/100BaseT Ethernet
* Up to 7 UART / USARTs
* Up to 4 SPIs
* Up to 3 I2Cs
* Up to 24 Timer Channels
* Up to 17 Analog Channels
* Up to 66 General Purpose I/O

## Recommended Operating Conditions

| Parameter                               | Description    |
| --------------------------------------- | -------------- |
| Standard Operating Voltage              | 4.5V \~ 5.5V   |
| Standard Operating Voltage (HV\_IN pin) | 5.5V \~ 30V    |
| Operating Ambient Temperature           | -40°C \~ 85°C  |
| Operating Junction Temperature          | -40°C \~ 125°C |

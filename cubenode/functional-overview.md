# Functional Overview

### Dual Arm® Cortex® Cores

CubeNode integrates two Arm® cores:&#x20;

* 1 x Cortex®-M7: Can execute high-performance tasks in parallel
* 1 x Cortex®-M4: Offers optimal performance for real-time applications

The two cores belong to separate power domains, which allow the designing of gradual high-power efficiency solutions in combination with low-power modes.

### Memory Protection Unit (MPU)

Two MPUs are included, where each manages CPU access rights and system resource attributes. These MPUs must be programmed and enabled before use. Their primary function is to prevent untrusted user programs from accidentally corrupting OS data or privileged tasks and to protect data processes and read-protect memory regions.&#x20;

Each MPU defines access rules for up to 16 protected regions, which can be subdivided into eight independent sub-regions. Configuration options include region address, size, and attributes, with protection ranging from 32 bytes to 4 Gbytes of addressable memory. Unauthorized access triggers a memory management exception.

### Embedded Flash Memory

Two Mbytes of Flash memory is embedded for storing programs and data. The memory is organized as 266 bit Flash word memory that can be used to store both code and data constants. Each word consists of one Flash word (8 words, 32 bytes or 256 bits) 10 ECC bits.

The Flash memory is divided into two independent banks. Each bank is organized as follows:

* 1 Mbyte of user Flash memory block containing eight user sectors of 128 Kbytes (4 K Flash memory words)
* 128 KB of System Flash memory from which the device can boot
* 2 KB (64 Flash words) of user option bytes for user configuration

### General-Purpose I/O (GPIO)

Each of the GPIO pins can be configured by software as output (push-pull or open-drain, with or without pull-up or pull-down), as input (floating, with or without pull-up or pull-down), or as a peripheral alternate function. Most of the GPIO pins are shared with digital or analog alternate functions. All GPIOs are high-current-capable and have speed selection to manage better internal noise, power consumption, and electromagnetic emissions. After reset, all GPIOs (except the debug pins) are in Analog Mode to reduce power consumption (refer to the GPIOs register reset values in the device reference manual). The I/O configurations can be locked by following a specific sequence to avoid spurious writing to the I/O registers.

### Analog-to-Digital Converter (ADC)

The microcontroller embeds three analog-to-digital converters, where the resolution can be configured to 16, 14, 12, 10, or 8 bits.

Additional logic functions embedded in the ADC interface allow:

* Simultaneous sample and hold
* Interleaved sample and hold

The ADC can be served by the DMA controller, thus allowing to automatically transfer ADC converted values to a destination location without any software action. In addition, an analog watchdog feature can accurately monitor the converted voltage of one, some, or all selected channels. An interrupt is generated when the converted voltage is outside the programmed thresholds.

### Inter-Integrated Circuit Interface (I2C)

CubeNode includes up to three I2C interfaces.

The I2C bus interface handles communications between the microcontroller and the serial I2C bus. It controls all I2C bus-specific sequencing, protocol, arbitration, and timing.

The I2C peripheral supports:

* I2C-bus specification and user manual ver. 5 compatibility:
  * Slave and Master modes, multimaster capability
  * Standard-mode (Sm), with a bitrate up to 100 kbit/s
  * Fast-mode (Fm), with a bitrate up to 400 kbit/s
  * Fast-mode Plus (Fm+), with a bitrate up to 1 Mbit/s and 20 mA output drive I/Os
  * 7-bit and 10-bit addressing mode, multiple 7-bit slave addresses
  * Programmable setup and hold times
  * Optional clock stretching
* System Management Bus (SMBus) specification ver. 2.0 compatibility:
  * Hardware Packet Error Checking (PEC) generation and verification with ACK control
  * Address resolution protocol (ARP) support
  * SMBus alerts
* Power System Management Protocol (PMBus) specification ver. 1.1 compatibility:
  * Independent clock: Selection of independent clock sources allows the I2C communication speed to be independent of PCLK reprogramming
  * Wakeup from Stop Mode on address match
  * Programmable analog and digital noise filters
  * 1-byte buffer with DMA capability

### Universal Asynchronous Receiver Transmitter (UART)

The Cubenode has three embedded universal asynchronous receiver transmitters  (UART4, UART7, and UART8).

### Universal Synchronous Receiver Transmitter (USART)

The CubeNode has four embedded universal synchronous receiver transmitters (USART1, USART2, USART3, and USART6).&#x20;

{% hint style="info" %}
If the Ethernet port is used, USART2 will be unavailable, because it shares the same control pin with the Ethernet port.
{% endhint %}

### Controller Area Network (FDCAN1, FDCAN2)

The controller area network (CAN) subsystem consists of two CAN modules, a shared message RAM memory, and a clock calibration unit.

The following features are provided:

* Supports CAN 2.0 and CAN with Flexible Data-Rate (CAN FD) Physical Layer Transceiver Requirements
* Optimized for CAN FD at 2, 5, and 8 Mbps operation
* Maximum propagation delay: 120 ns
* Loop delay symmetry: -10%/+10% (2 Mbps)
* Qualified according to AEC-Q100 Rev. G&#x20;
* Automatic thermal shutdown protection
* Detection of ground fault
* Permanent dominant detection on TXD
* Permanent dominant detection on bus
* Automatic thermal shutdown protection
* Suitable for 12V and 24V systems

### USB

A USB On-The-Go (OTG) full-speed device/host/OTG peripheral with integrated transceivers is provided. It is compliant with the USB 2.0 specification.

### Three Axis Accelerometer (Optional)

The CubeNode features IMU with 20-bit data format with 19 bits of real data support in FIFO for high-data resolution. This FIFO format encapsulates 18-bits of accelerometer data.&#x20;

* User-selectable accelerometer full-scale range (g): ± 2/4/8/16

### Three Axis Gyroscope (Optional)

The CubeNode features IMU with 20-bit data format support in FIFO for high-data resolution. This FIFO format encapsulates 19-bits of gyroscope data.

* User-selectable Gyro Full-scale range (dps): ±15.6/31.2/62.5/125/250/500/1000/2000

### Ethernet Interface

A high-performance 10/100BaseT Ethernet transceiver is included, which has the following features:

* Compliant with IEEE802.3/802.3u (Fast Ethernet)
* Compliant with ISO 802-3/IEEE 802.3 (10BASE-T)&#x20;
* Loop-back modes
* Auto-negotiation
* Automatic polarity detection and correction
* Vendor specific register functions
* HP Auto-MDIX support
* Integrated power-on reset circuit

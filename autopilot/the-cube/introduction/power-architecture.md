# Power Architecture

The Cube has removed the power management from the FMU. Thus, the servo rail is no longer the primary backup power source for the FMU. It remains there as a failsafe for I/O functions.&#x20;

<figure><img src="../../../.gitbook/assets/System Power Distribution (1).svg" alt=""><figcaption></figcaption></figure>

### Power Management Module (separate from the FMU)

Key features of The Cube power architecture:

* Single, independent 5V supply for the flight controller and peripherals.
* Integration with two power bricks or compatible alternatives, including current and voltage sensing.
* Low power consumption and heat dissipation.
* Power distribution and monitoring for peripheral devices.
* Protection against common wiring faults; under/over-voltage protection, overcurrent protection, and thermal protection.
* Brown-out resilience and detection.

### FMU and I/O Power Supplies

Both the FMU and I/O operate at 3.3V, where each has its private dual-channel regulator. As in The Cube, each regulator features a power-on reset output tied to the regulator’s internal power-up and drop-out sequencing.

### Power Sources

Power may be supplied to The Cube via USB, the power brick port, or the second brick port. Each power source is protected against reverse-polarity connections and back-powering from other sources.

Cube F4 series

* FMU + IO power budget, which includes all the LEDs and the Piezo buzzer, is 450mA.
* &#x20;The total peripheral power is limited to 2.5A.&#x20;

Cube F7 and H7 series

* FMU + IO power budget, which includes all LEDs and the Piezo buzzer, is 550mA.&#x20;
* Peripheral power is limited to 2.5A.

<mark style="color:orange;">**Cube Orange**</mark>

* The power budget increase is due to the improved heater.

{% hint style="warning" %}
USB is not recommended in flight on Nuttx code.
{% endhint %}

### Power Brick Port

The brick port is the preferred power source for The Cube. It will be selected by default when available.&#x20;

### Servo Power

The Cube supports both standard (5V) and high-voltage (up to 10V) servo power with some restrictions.

The I/O will accept power from the servo connector reaching up to 10V. This allows the I/O to failover to servo power when the main power supply is lost or interrupted.

{% hint style="info" %}
The FMU and peripherals will not accept power from the servo connector.
{% endhint %}

### Aux Power

The Cube backup power port is configured the same as the primary power input.&#x20;

When the input voltage exceeds 5.7V, the power is locked out. The Cube and its peripherals may draw up to 2.75A in total when operating on Aux power, provided that the Brick or other power source can supply the required current.

{% hint style="info" %}
The Cube never supplies power to the servos.
{% endhint %}

### Servo Rail

The I/O chip can draw power reaching up to 10.5V from the servo rail.&#x20;

The servo rail can be used to revert to manual mode when the other two main power sources fail. This is only useful for planes and when the I/O chip has been mapped correctly.

### USB Power

USB power can be used for software updates, testing, and development purposes. It can also be supplied to the peripheral ports for testing. However, the total current consumption (including the peripherals) must typically be limited to 500mA to avoid overloading the host USB port.

### Multiple Power Sources

When more than one power source is connected, The Cube will draw power from the highest-priority source with a valid input voltage.

In most cases, the FMU should be powered by the power brick or a compatible off-board regulator via the brick port or auxiliary power rail.

For desktop testing scenarios, power drawn from the USB avoids the need for a BEC or similar servo power source. However, the servos themselves will still require external power.

### Input Voltage Range

The input voltage range that each component can accept is shown below.

|                 | **Brick port**   | **Aux port**     | **USB port**     | **Servo rail** |
| --------------- | ---------------- | ---------------- | ---------------- | -------------- |
| **FMU**         | 4 - 5.7V         | 4 - 5.7V         | 4 - 5.7V         | NIL            |
| **I/O**         | 4 - 5.7V         | 4 - 5.7V         | 4 - 5.7V         | 4 - 10.5V      |
| **Peripherals** | 4 - 5.7 2.5A max | 4 - 5.7 2.5A max | 4 - 5.7 2.5A max | NIL            |

### Power Management Peripherals

The Cube provides power routing, over/under voltage detection and protection, filtering, switching, current-limiting and transient suppression for peripherals. Power outputs to peripherals feature ESD and EMI filtering, which ensures that no more than 5.5V is supplied to the peripheral devices.&#x20;

Power is disconnected from the peripherals when the following occurs:

* Available supply voltage falls below 2.7V
* Available supply voltage rises above approximately 5.7V.

### Peripheral Power Groups

The peripheral power is divided into two groups:

**Serial 1** (TELEM 1) has a private 1.5A current limit intended for powering low-power peripherals. This output has separate EMI filtering and draws power directly from the USB or Brick inputs. The peak power drawn from this port should not exceed 1.5A.

{% hint style="danger" %}
Never power the telemetry from this port under any circumstances.
{% endhint %}

All other peripherals share a 1A current limit and a single power switch. The peak power drawn from this port should not exceed 1.5A. Each group is individually switched by software control.

### Spektrum/DSM R/C Interface

The Spektrum/DSM R/C interface draws power from its own regulator, and not from the two peripheral groups mentioned above. This port is switched by software control, allowing Spektrum/DSM binding to be implemented. Spektrum receivers generally draw roughly 25mA.

### S.Bus and CPPM Receivers

S.Bus and CPPM receivers are powered by a dedicated power supply.&#x20;

{% hint style="warning" %}
Do not connect any servos to this power supply. It only provides power to the RX.&#x20;
{% endhint %}

### Capacitor Backup

Both the FMU and I/O microcontrollers feature capacitor-backed real-time clocks and SRAM. The on-board backup capacitor has sufficient capacity to allow orderly recovery from unintended power loss or in-air restarts.&#x20;

The capacitors can be recharged from the FMU 3.3V rail if software is included to support this feature.

### Voltage, Current, and Fault Sensing

The battery voltage and current reported by both bricks can be measured by the FMU. In addition, the 5V unregulated supply rail can be measured (to detect brown-out conditions). The I/O can measure the servo power rail voltage.

Over-current conditions on the peripheral power ports can be detected by the FMU. Hardware lock-out prevents damage due to persistent short circuits on these ports. The lock-out can be reset by the FMU software. The under/over voltage supervisor for the FMU provides an output that is used to hold the FMU in reset during brown-out events.

### EMI Filtering and Transient Protection (applies to the normal base board)

EMI filtering is provided at key areas in the system using high-insertion-loss pass-through filters. These filters are paired with TVS diodes at the peripheral connectors to suppress power transients.

Reverse polarity protection is provided at each of the power inputs. USB signals are filtered and terminated with a combined termination/TVS array.

Most digital peripheral signals (all PWM outputs, serial ports, and I2C ports) are driven using ESD-enhanced buffers and have series blocking resistors to reduce the risk of damage from transients or misconnections.

{% hint style="info" %}
Ensure adequate ESD protection is provided to the externally supplied base boards.
{% endhint %}

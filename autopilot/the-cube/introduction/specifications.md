# Specifications

The following shows the key specifications of The Cube.

**Three IMUs (applies to all The Cubes)**

* Two on the IMU board.
* &#x20;One fixed on the FMU.

**Two onboard compasses** (**Cube Black**, <mark style="color:green;">**Cube Green**</mark>, and <mark style="color:blue;">**Cube Blue**</mark>)

* One on the IMU board.
* One fixed on the FMU.

**One onboard compass** (<mark style="color:orange;">**Cube Orange**</mark> and <mark style="color:yellow;">**Cube Yellow**</mark>)

**Two Barometers (applies to all The Cubes)**

* One on the IMU.
* One on the FMU.

**Dual Power Input (applies to all The Cubes)**

* Redundancy option from the servo rail removed and replaced with a dedicated second power plug.
* A dedicated power protection Zener diode and Fet added for protection against voltages over 5.6V being applied to Aux input 2.
* Available only on the "PRO" carrier board. The mini carrier board still draws the backup power from the servo rail.

**Dual External I2C (applies to all The Cubes)**

* Allows connection to either I2C port, potentially allowing two GPS/Mag units to be plugged in without the Mags conflicting.

**Power Monitoring (applies to all The Cubes)**

* Power monitoring pins are routed to the I/O chip. This allows power event logging during an inflight reboot.
* Brick OK, Backup OK, and FMU 3.3V are all connected to a digital pin on the I/O via a 220Ohm resister.

**I/O Ports (applies to all The Cubes excluding the CAN Bus interface)**

* 14 PWM servo outputs (eight from I/O and six from FMU).
* R/C inputs for CPPM, Spektrum/DSM, and S.Bus.
* Analog/PWM RSSI input.
* S.Bus servo output.
* Five general-purpose serial ports; two with full flow control.
* Two I2C ports.
* One SPI port (un-buffered, not recommended for use as it is only for short cables).
* Two CAN Bus interfaces.

{% hint style="info" %}
The <mark style="color:blue;">**Cube BlueH7**</mark> and <mark style="color:orange;">**Cube Orange**</mark> are equipped with the CAN FD interface.
{% endhint %}

* Three analog inputs.
* High-powered piezo buzzer driver on expansion board.
* High-power RGB LED (I2C driver compatible; only connected externally).
* Safety switch/LED.

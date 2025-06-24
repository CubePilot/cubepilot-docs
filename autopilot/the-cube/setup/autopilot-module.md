# AutoPilot Module

## Mounting

Use the 3M double-layered tape and screws from the package to mount The Cube as close as possible to the unmanned aerial vehicle's (UAV) center of gravity. The carrier board screws are designed for 1.8 mm boards. The length of the customized M2.5 screws should be around 6 mm to 7.55 mm in order to mount The Cube onto the board.&#x20;

{% hint style="info" %}
Ensure that the arrow on The Cube is pointing towards the front of the UAV.
{% endhint %}

<figure><img src="../../../.gitbook/assets/Photo%20-%2001-R.jpg" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
The Cube can be mounted in reverse or upside-down. For such situations, the parameters related to the orientation of The Cube may need to be modified accordingly.
{% endhint %}

{% hint style="warning" %}
The Cube is not waterproof. Ensure it is adequately protected when operating in a rainy or humid environment.&#x20;
{% endhint %}

## Peripheral Connection

According to the peripheral type, size, dynamic structure, and load, the installation and parameter settings may vary. See the following for details.&#x20;

{% hint style="warning" %}
Connect the GPS, sensors, telemetry, etc. to The Cube according to the connector pinout. Check the wiring order carefully, as most peripheral malfunctions are due to incorrect wiring. Since there are limitations on every interface on The Cube, connect your high-power peripheral to an external BEC.
{% endhint %}

### Installing the  MicroSD Card

Data flash logs are stored on the MicroSD card, which is inserted in the left slot of The Cube. It is recommended to use a Class 4 or higher MicroSD card.

{% hint style="info" %}
The Cube cannot arm the UAV without a MicroSD card. An alarm with one high tone and two low tones will be played when The Cube arms the UAV.&#x20;
{% endhint %}

<figure><img src="../../../.gitbook/assets/27.png" alt="" width="563"><figcaption></figcaption></figure>

### Power Supply

The Cube supports three different power sources, which include the following:

* Power module
* Servo rail
* USB cable

When more than one power source is connected, power is drawn from the highest-priority source with a valid input voltage.&#x20;

<table><thead><tr><th width="157">Power Source</th><th width="120">Priority</th><th width="152">Regular Range</th><th width="141">Limit</th><th>Protection Range</th></tr></thead><tbody><tr><td>Power Module Input</td><td>High</td><td>4.8 V - 5.4 V</td><td>4.1 V - 5.7 V</td><td>0 V - 20 V</td></tr><tr><td>Servo Rail Input</td><td>Medium</td><td>4.8 V - 5.4 V</td><td>4.1 V - 10 V</td><td>0 V - 20 V</td></tr><tr><td>USB Cable Input</td><td>Low</td><td>4.8 V - 5.4 V</td><td>4.1 V - 5.7 V</td><td>0 V - 6 V</td></tr></tbody></table>

The I/O will accept power from the servo connector reaching up to 10V for manual override. The system will be unpowered when the servo input is above 5.7 V and the power module input is absent. The FMU and peripherals will not accept power from the servo rail.

### Power Module Connection

Connect the power module to the POWER1 port via the power cable. If there is a second battery monitor, connect it to the POWER2 port. The Cube will be turned on immediately after the battery is connected. Connect the XT60 on the other side of the power module to the motor system and loads.

![](<../../../.gitbook/assets/Photo - 04.jpg>)

### Connecting Electronic Speed Controllers (ESC) and Motors

Connect the power (+), ground (-), and signal (s) wires for each ESC to The Cube’s main output pins by the motor number. Find the corresponding frame type below to determine the assigned order of the motors.

ECS malfunction is usually caused by incorrect wiring. Thus, always check the ESC model to ensure that the +5 V cable is connected correctly. On the APM2.x, the ground pin of the power supply can be used as the APM feedback signal. For The Cube, the signal pin and ground pin must be connected to operate the ESC.

### Motor Order Diagrams

The figures below show the motor order for each frame type. The numbers indicate which output pin from The Cube should be connected to each motor/propeller. The propeller direction is shown in green (clockwise, CW) or blue (counter-clockwise, CCW). Connect the cable from the ESC to the MAIN OUT port on The Cube.

![](<../../../.gitbook/assets/Photo - 05-1.jpg>)

![](<../../../.gitbook/assets/Photo - 05-2.jpg>)

![](<../../../.gitbook/assets/Photo - 05-3.jpg>)

![](<../../../.gitbook/assets/Photo - 05-4.jpg>)

## Sensors Connection

### Mounting the GPS Module

Follow these guidelines to ensure the GPS module always operates in an optimal environment:

* Mount the GPS module on the exterior of the UAV, ideally in an elevated position with a clear view of the sky. Ensure it is placed as far as possible from the motors and ESCs, with the arrow facing forward.
* Ensure the module is positioned at least 10cm away from the DC power wiring and batteries. Using a GPS mast is highly recommended.
* Avoid placing the module near metallic objects that contain iron.
* Twist the power and ground wires when possible.

A GPS module working in an outdoor environment with sufficient sky coverage will receive better satellite signals, which significantly improves the safety of autonomous missions.

{% hint style="danger" %}
Some high power wireless devices may interfere with the compass and GPS signal. Position these high power wireless devices as far as possible from the GPS module.
{% endhint %}

### GPS Modes

Single GPS

Use the 8-pin DF13 connector to connect the GPS module to the GPS1 port on The Cube. Most modules are plug-and-play. If the module includes a compass, it may need additional calibration.

### RC System Connection

The Cube supports the following signal receivers. Each signal type corresponds to a specific port on the carrier board.

#### PWM/PPM/Futaba S.bus Receiver

* PWM Receiver: The Cube cannot directly process PWM signals. A PPM encoder is needed to encode multi-channel PWM to single-channel PPM signals. Thus, connect the PPM encoder to the RCIN port on The Cube.
* PPM RC Receiver/Futaba S.Bus Receiver: These receivers are plugged into the RCIN port.

#### Spektrum DSM/DSM2/DSM-X Satellite Receiver

For the Spektrum DSM, DSM2, or DSM-X Satellite receivers, they should be connected to the SPKT port on The Cube.

### Telemetry Connection

The function of the wireless telemetry is to establish two-way communication between the autopilot and ground control station (GCS). This enables real-time data to be displayed and the unmanned aerial vehicle (UAV) to be controlled by the GCS.

#### **Telemetry Requirement: Mavlink protocol, Passthrough protocol, or TTL serial interface**

Ensure that the pin assignment of the cable matches the pinout of TELEM1 on The Cube.&#x20;

After confirming, the telemetry cable can be connected to either the TELEM1 or TELEM2 port. Connect the other end of the cable to one of the COM ports on the GCS. The baud rate is typically 57600.

{% hint style="info" %}
The default baud rate of TELEM1 port is 57600. It must match the telemetry baud rate.
{% endhint %}



Last Update: 11th June 2019

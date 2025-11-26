# CubeID™

Overview

CubeID™ is a small size (25mm \* 13.75mm \* 3.5mm) Remote ID that broadcasts information about UAVs in flight through a Bluetooth 5.2 dual-mode unit, supporting both CAN and serial protocols.

Users can write different codes with a single CubeID to adapt to multiple UAVs based on their requirements.

CubeID™ is FCC and CE certified.

## Hardware Specification

### **CubeID**™ **Specification**

<table><thead><tr><th>Type</th><th>Parameter</th><th data-hidden></th></tr></thead><tbody><tr><td><strong>Bluetooth Chip</strong></td><td>Nordic NRF52840 (Bluetooth 5.2 )</td><td></td></tr><tr><td><strong>Frequency</strong></td><td>2402MHz ~ 2480MHz</td><td></td></tr><tr><td><strong>Operation Temperature</strong></td><td>-40°C ~ 85°C</td><td></td></tr><tr><td><strong>Dimension</strong></td><td>25mm * 13.75mm * 3.5mm</td><td></td></tr><tr><td><strong>Weight</strong></td><td>10g (with cable and antenna)</td><td></td></tr><tr><td><strong>Protocol</strong></td><td>Serial</td><td></td></tr></tbody></table>

### **Cube ID**™**\_CAN Specification**

<table><thead><tr><th>Type</th><th>Parameter</th><th data-hidden></th></tr></thead><tbody><tr><td><strong>Bluetooth Chip</strong></td><td>Nordic NRF52840 (Bluetooth 5.2 )</td><td></td></tr><tr><td><strong>Frequency</strong></td><td>2402MHz ~ 2480MHz</td><td></td></tr><tr><td><strong>Operation Temperature</strong></td><td>-40°C ~ 85°C</td><td></td></tr><tr><td><strong>Dimension</strong></td><td>25mm * 13.75mm * 3.5mm</td><td></td></tr><tr><td><strong>Weight</strong></td><td>10g (with cable and antenna)</td><td></td></tr><tr><td><strong>Protocol</strong></td><td>CAN &#x26; Serial</td><td></td></tr></tbody></table>

## Pinout

### CAN

<figure><img src="../.gitbook/assets/CAN.jpg" alt=""><figcaption></figcaption></figure>

| Pin | Definition | Cable color |
| --- | ---------- | ----------- |
| 1   | VCC\_5V    | red         |
| 2   | CAN\_H     | red         |
| 3   | CAN\_L     | black       |
| 4   | GND        | black       |

### Serial

<figure><img src="../.gitbook/assets/Serial.jpg" alt=""><figcaption></figcaption></figure>

| Pin | Definition | Cable color |
| --- | ---------- | ----------- |
| 1   | VCC\_5V    | red         |
| 2   | TX         | black       |
| 3   | RX         | black       |
| 4   | GND        | black       |

## Installing the CubeID™

1. Use one of the following provided cables to connect the CubeID™ to The Cube:
   * 4-pin CAN cable
   * 6-pin Serial cable
   * 8-pin Serial cable
2. Attach the CubeID™ to the UAV using:
   * A regular adhesive sticker, or
   * A soft sticker to provide light vibration isolation

{% hint style="info" %}
Keep the antenna away from the propeller.
{% endhint %}

## Configuring the CubeID™

> Before configuring the CubeID™, make note of the following:
>
> * For OEM use, create your OEM OpenDroneID ArduPilot firmware. For details, refer to the following:
>   * [https://ardupilot.org/dev/docs/opendroneid.html#opendroneid](https://ardupilot.org/dev/docs/opendroneid.html#opendroneid)
>   * [https://www.youtube.com/watch?v=Az8v4Kx4hS0](https://www.youtube.com/watch?v=Az8v4Kx4hS0)
> * For regular use,  load the latest ArduPilot firmware. Ensure that the build you are using has OpenDroneID feature enabled. The easiest way to confirm this is to check whether the  `DID_*` parameters appear.

### Initial Settings

1. Connect The Cube to a computer via a USB cable.&#x20;
2. Launch the latest version of Mission Planner.&#x20;
3. Click **Load custom firmware** to install the OpenDroneID firmware.

<figure><img src="../.gitbook/assets/load_firmware.png" alt=""><figcaption></figcaption></figure>

4. Go to **Full Parameter List** and search for "DID\_ENABLE".&#x20;
5. Change the value to "1" to enable ODID.

<figure><img src="../.gitbook/assets/odid.png" alt=""><figcaption></figcaption></figure>

### CAN Settings

1. Go to "Full Parameter List" and search for "CAN\_P1\_DRIVER".&#x20;

<figure><img src="../.gitbook/assets/can.png" alt=""><figcaption></figcaption></figure>

2. Change the value to "1" to enable CAN.
3.  Modify the following parameter:

    **DID\_CANDRIVER: 1** (enables the corresponding CAN port)

<figure><img src="../.gitbook/assets/}L1NN5&#x60;KJKLVD]7&#x60;Z%1YD2-1691373851187-2.png" alt=""><figcaption></figcaption></figure>

### Serial Settings

1. Search for Serialx\_PROTOCAL and change it to Mavlink.

<figure><img src="../.gitbook/assets/serial.png" alt=""><figcaption></figcaption></figure>

2. Modify the following parameters:

* **DID\_CANDRIVER: 0** (disables the corresponding CAN port).
* **DID\_MAVPORT:** (Serial port number that will send OpenDroneID MAVLink messages; can be set to "-1" if using DroneCAN).

<figure><img src="../.gitbook/assets/serial (2).png" alt=""><figcaption></figcaption></figure>

### Mission Planner Settings

1. Launch Mission Planner.
2. Select **Drone ID** to set **(1) UAS ID\*** **(2) UAD ID Type** and **(3) UA Type**

<figure><img src="../.gitbook/assets/Droneid.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Droneid01.png" alt=""><figcaption></figcaption></figure>

3. Go to **Operations** to set **(1) Operator ID, (2) Oper ID Type, (3) Self ID DESC**, and **(4) Self ID Type.**

<figure><img src="../.gitbook/assets/Operation.png" alt=""><figcaption></figcaption></figure>

## Testing

Download the appropriate app based on your mobile operating system to detect and monitor nearby UAVs:

* iO&#x53;**: DroneScanner**&#x20;
* Android: **OpenDroneID** or **DroneScanner**&#x20;

These apps allow you to check the UAV’s location, ID, operator ID, distance from the operator, and other relevant information.

{% hint style="info" %}
For more information about Remote ID, refer to the following Wiki link:

[https://ardupilot.org/copter/docs/common-remoteid.html](https://ardupilot.org/copter/docs/common-remoteid.html)
{% endhint %}

## Persistent UAS ID

* To meet FAA requirements for manufacturers, a persistent ID needs to be recorded in the flight system.
* In a CubeID™ + Ardupilot setup, this is achieved using ArduPilot's persistent storage feature.
* The manufacturer needs to integrate the following changes depending on the ArduPilot release:
  * ArduPilot 4.3 releases ([https://github.com/ArduPilot/ardupilot/pull/24367](https://github.com/ArduPilot/ardupilot/pull/24367))
  * ArduPilot 4.4 releases ([https://github.com/ArduPilot/ardupilot/pull/24370](https://github.com/ArduPilot/ardupilot/pull/24370))
* The changes are merged into the latest master at the time of writing this document and are expected to be included in the stable 4.4.2 release.
* Once the firmware with said changes is loaded, parameter `DID_OPTIONS` must be set to "&#x34;**".**
* This can also be done as part of default.parms at the custom build stage to simplify the setup process.
* After the setting is applied, the first received Basic ID message - containing Drone ID and other details (from Mission Planner or any GCS) - will be persistently recorded. Note that once configured, the persistent parameters **cannot be rolled back**.
* The ID will be persistently linked with the The Cube.

## Updating

### CubeID™ CAN Module Update

1. Launch Mission Planner.
2. Go to **Setup > Optional Hardware > DroneCAN/UAVCAN** and establish the MAVCAN connection based on the CAN port being used.

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

2. Verify that CubeID™ appears as com.cubepilot.cubeid on the list.&#x20;
3. Click **Menu > Update** to start the update process. Mission Planner will retrieve the latest firmware binary automatically and start updating.

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
To use a different tool to update the CubeID™ CAN module, download the latest firmware from: [https://firmware.cubepilot.org/UAVCAN/com.cubepilot.cubeid/1.0/firmware.bin](https://firmware.cubepilot.org/UAVCAN/com.cubepilot.cubeid/1.0/firmware.bin)
{% endhint %}

### CubeID™ Serial Module Update&#x20;

> If the CubeID™ Update tab is not visible in Mission Planner, update Mission Planner to the latest beta version: [https://ardupilot.org/planner/docs/mission-planner-overview.html?highlight=beta#support](https://ardupilot.org/planner/docs/mission-planner-overview.html?highlight=beta#support)

1. Launch Mission Planner with the CubeID™ connected to one of the Telem ports of The Cube, and The Cube connected to the computer via USB. Ensure that the baud rate is set to 57600.
2. Select the Serial port number corresponding to the Telem port where the CubeID™ is connected (Telem1 is Serial 1 and Telem2 is Serial 2).

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

3. Select ODID TX RX device from the list in the upper left corner.&#x20;

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

4. Click **Update Firmware**. The firmware update may take a few minutes.

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

#### **Warning**

Caution: The user is cautioned that changes or modifications not expressly approved by the party responsible for compliance could void the user's authority to operate the equipment.

This device complies with Part 15 of the FCC Rules. Operation is subject to the following two conditions: (1) this device may not cause harmful interference, and (2) this device must accept any interference received, including interference that may cause undesired operation.

NOTE: This equipment has been tested and found to comply with the limits for a Class B digital device, pursuant to Part 15 of the FCC Rules. These limits are designed to provide reasonable protection against harmful interference in a residential installation. This equipment generates, uses and can radiate radio frequency energy and, if not installed and used in accordance with the instructions, may cause harmful interference to radio communications. However, there is no guarantee that interference will not occur in a particular installation.

If this equipment does cause harmful interference to radio or television reception, which can be determined by turning the equipment off and on, the user is encouraged to try to correct the

interference by one or more of the following measures:

\-- Reorient or relocate the receiving antenna.

\-- Increase the separation between the equipment and receiver.

\-- Connect the equipment into an outlet on a circuit different from that to which the receiver is connected.

\-- Consult the dealer or an experienced radio/TV technician for help.

_**\*FCC Radiation Exposure Statement\***_

This equipment complies with FCC radiation exposure limits set forth for an uncontrolled environment.

This equipment should be installed and operated with a minimum distance of 20cm between the radiator and your body.

This transmitter must not be co-located or operating in conjunction with any other antenna or transmitter.



Last modify: 14th March 2023

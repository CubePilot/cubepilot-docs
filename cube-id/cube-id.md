# Cube ID

Overview

Cube ID is small size (25mm \* 13.75mm \* 3.5mm ) Remote ID which broadcasting information about UAVs in flight through a Bluetooth 5.2 dual-mode unit, supports both CAN and serial protocols.

Users can write different codes with one Cube ID only, to adapt to multiple UAVs based on their needs.

CubeID is FCC and CE certified.



## Hardware Specification

### **Cube ID Specification**

<table><thead><tr><th>Type</th><th>Parameter</th><th data-hidden></th></tr></thead><tbody><tr><td><strong>Bluetooth chip</strong></td><td>Nordic NRF52840 (Bluetooth 5.2 )</td><td></td></tr><tr><td><strong>Frequency</strong></td><td>2402MHz ~ 2480MHz</td><td></td></tr><tr><td><strong>Operation Temperature</strong></td><td>-40°C ~ 85°C</td><td></td></tr><tr><td><strong>Dimension</strong></td><td>25mm * 13.75mm * 3.5mm</td><td></td></tr><tr><td><strong>Weight</strong></td><td>10g (with cable and antenna)</td><td></td></tr><tr><td><strong>Protocol</strong></td><td>Serial</td><td></td></tr></tbody></table>

### **Cube ID\_CAN Specification**

<table><thead><tr><th>Type</th><th>Parameter</th><th data-hidden></th></tr></thead><tbody><tr><td><strong>Bluetooth chip</strong></td><td>Nordic NRF52840 (Bluetooth 5.2 )</td><td></td></tr><tr><td><strong>Frequency</strong></td><td>2402MHz ~ 2480MHz</td><td></td></tr><tr><td><strong>Operation Temperature</strong></td><td>-40°C ~ 85°C</td><td></td></tr><tr><td><strong>Dimension</strong></td><td>25mm * 13.75mm * 3.5mm</td><td></td></tr><tr><td><strong>Weight</strong></td><td>10g (with cable and antenna)</td><td></td></tr><tr><td><strong>Protocol</strong></td><td>CAN &#x26; Serial</td><td></td></tr></tbody></table>

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

## Installation

Connect the CAN or Serial port on module and flight controller with the suitable cable(we provide 4 Pin CAN cable,6 Pin and 8 pin Serial cable) . Stick the module to UAV by regular sticker or soft sticker (with slightly vibration isolation).

_\*Keep the antenna away from the propeller._

## Settings

> For OEM use, you must create your OEM OpenDroneID Ardupilot firmware ，please check
>
> [https://ardupilot.org/dev/docs/opendroneid.html#opendroneid](https://ardupilot.org/dev/docs/opendroneid.html#opendroneid))
>
> [https://www.youtube.com/watch?v=Az8v4Kx4hS0](https://www.youtube.com/watch?v=Az8v4Kx4hS0)
>
>
>
> For normal user please load latest Ardupilot firmware. Do ensure that the build you are using has OpenDroneID feature enabled. Easiest way to tell is that `DID_*` parameters should appear.

1. Connect the flight controller to computer via USB cable. Open Mission Planner（latest version）. Install the OpenDroneID firmware firmware by "Load custom firmware".

<figure><img src="../.gitbook/assets/load_firmware.png" alt=""><figcaption></figcaption></figure>

2. Go to "Full Parameter List" and find "DID\_ENABLE". Change it to "1" to enable ODID.

<figure><img src="../.gitbook/assets/odid.png" alt=""><figcaption></figcaption></figure>

#### For CAN

1.Go to "Full Parameter List" and find "CAN\_P1\_DRIVER". Change it to "1" to enable CAN.

<figure><img src="../.gitbook/assets/can.png" alt=""><figcaption></figcaption></figure>

2.  Modify the following parameters:

    **DID\_CANDRIVER : 1** (enable relative CAN port)

<figure><img src="../.gitbook/assets/}L1NN5&#x60;KJKLVD]7&#x60;Z%1YD2-1691373851187-2.png" alt=""><figcaption></figcaption></figure>

**For Serial**

1.Find Serialx\_PROTOCAL and change it to mavlink）

<figure><img src="../.gitbook/assets/serial.png" alt=""><figcaption></figcaption></figure>

2.Modify the following parameters:

**DID\_CANDRIVER : 0** (disable relative CAN port)

**DID\_MAVPORT :** (Serial port number to send OpenDroneID MAVLink messages to. Can be -1 if using DroneCAN)

<figure><img src="../.gitbook/assets/serial (2).png" alt=""><figcaption></figcaption></figure>

Go to MissionPlanner homepage select **Drone ID** to set **(1)UAS ID\*** **(2)UAD ID Type** and **(3)UA Type**

<figure><img src="../.gitbook/assets/Droneid.png" alt=""><figcaption></figcaption></figure>

to set **(1)UAS ID** **(2)UAD ID Type** and **(3)UA Type**

<figure><img src="../.gitbook/assets/Droneid01.png" alt=""><figcaption></figcaption></figure>

Go to **Operation** to set **(1)Operator ID , (2)Oper ID Type , (3)Self ID DESC** and **(4)Self ID Type**

<figure><img src="../.gitbook/assets/Operation.png" alt=""><figcaption></figcaption></figure>

## Testing

***

Download **DroneScanner** for IOS， **OpenDroneID** or **DroneScanner** for Android to detect and monitor nearby UAVs.

Operator are able to check UAV's location, ID , operator ID, distance from operator , ect by using these APP.

#### Note

> For more information about Remote ID, you may check in Wiki:
>
> [https://ardupilot.org/copter/docs/common-remoteid.html](https://ardupilot.org/copter/docs/common-remoteid.html)

## Persistent UAS ID

* To meet FAA requirements for manufacturers, a persistent ID needs to be recorded in Flight system.
* To achieve this with CubeID + Ardupilot setup. Ardupilot's persistent storage feature is used.
* The Manufacturer needs to integrate following changes depending on which release they are on:
  * Ardupilot 4.3 Releases ([https://github.com/ArduPilot/ardupilot/pull/24367](https://github.com/ArduPilot/ardupilot/pull/24367))
  * Ardupilot 4.4 Releases ([https://github.com/ArduPilot/ardupilot/pull/24370](https://github.com/ArduPilot/ardupilot/pull/24370))
* The changes are merged into latest master at the time of writing this doc, and are expected to be added to stable release 4.4.2.
* Once the firmware with said changes is loaded, parameter `DID_OPTIONS` need to be set to **4**
* This can also be done as part of default.parms at custom build stage, to ease the setup process.
* After the setting, the first reception of Basic ID containing Drone ID and other details (from Mission Planner or any other GCS) will be persistently recorded. Please note that once set the persistent parameters can't be rolled back.
* The ID will be persistently linked with the Flight Controller.

## Updating

#### CubeID CAN module Update

* Inside Mission Planner Go to **Setup > Optional Hardware > DroneCAN/UAVCAN** and establish mavcan connection depending on which CAN port you are connected.

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

* CubeID should appear as com.cubepilot.cubeid in the list, click **Menu > Update** to start the update process, Mission Planner will fetch the latest firmware binary automatically and start the process

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

Note: If you want to use different tool to update CubeID CAN module, you can get the latest firmware from [https://firmware.cubepilot.org/UAVCAN/com.cubepilot.cubeid/1.0/firmware.bin](https://firmware.cubepilot.org/UAVCAN/com.cubepilot.cubeid/1.0/firmware.bin)

#### CubeID Serial module update&#x20;

> If you are not seeing CubeID Update tab in Mission Planner please update your mission planner to latest beta [https://ardupilot.org/planner/docs/mission-planner-overview.html?highlight=beta#support](https://ardupilot.org/planner/docs/mission-planner-overview.html?highlight=beta#support)

* Start Mission Planner with CubeID connected to one of the Telem ports of Cube and the cube connected via USB. Ensure that you start connection with Baud rate as 57600.
* Select Serial Port number where CubeID is connected (Telem1 is Serial 1 and Telem2 is Serial 2).

<figure><img src="../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

* Select ODID TX RX device from the Top left corner list.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

* Finally click Update Firmware. The firmware update can take few minutes.

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

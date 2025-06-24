# ADS-B IN Carrier Board

The <mark style="color:orange;">Cube Orange</mark> Standard Kit + ADS-B includes the new <mark style="color:orange;">Cube Orange</mark> autopilot and ADS-B IN-carrier board.

<figure><img src="../.gitbook/assets/The Cube Orange standard set-3 (1).jpg" alt="" width="563"><figcaption></figcaption></figure>

The ADS-B IN-carrier board is an updated version of the original board. The specifications and external connections remain the same, but with the following changes:

* Integration of uAvionix ADS-B IN receiver
* Built-in ADS-B antenna&#x20;
* Removal of Intel Edison bay and Debug USB ports
* New product design&#x20;
* Correct labeling of CAN ports&#x20;

## uAvionix ADS-B Receiver

The new carrier board has an integrated uAvionix 1090Mhz ADS-B IN receiver. This enables the detection of aircraft equipped with ADS-B OUT in the vicinity. The aircraft information, such as the position, altitude, speed, and ID, can be displayed on the connected ground station. Additionally, the alarm, sense, and avoid functions in ArduPilot can be configured.

The ADS-B receiver is connected to the internal serial 5 port. It is compatible with ArduPilot and PX4.

### Enabling the ADS-B function in ArduPilot

To enable the ADS-B function in ArduPilot, complete the following steps:

1. Open Mission Planner.&#x20;
2. Click **Setup** -> **Install Firmware**.
3. Install one of the **Plane** or **Copter-related** firmware.
4. Click **Config** -> **Full Parameter List.**&#x20;
5. Set the following parameters to the values shown in the table.

| Parameter                      | Value | Description                                                                                     |
| ------------------------------ | ----- | ----------------------------------------------------------------------------------------------- |
| SERIAL5\_BAUD                  | 57    | Sets the baud rate                                                                              |
| SERIAL5\_PROTOCOL              | 1     | Sets the protocol                                                                               |
| SR0\_ADSB                      | 2     | Sets ADSB stream rate to the ground station                                                     |
| <p>SR1_ADSB or<br>SR2_ADSB</p> | 2     | Enables the ground station to receive the detected aircraft information via Telem 1 or Telem 2. |

6. Click **Write Params**.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

### Enabling the ADS-B Alarm, Sense, and Avoid Functions

To enable the ADS-B alarm, sense, and avoid functions, complete the following steps:

1. Follow Steps 1\~4 in the "Enabling the ADS-B function in ArduPilot" section.
2. Set AVD\_Enable to "1".&#x20;
3. Click **Write Params**.&#x20;

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

4. Reboot The Cube.&#x20;
5. Click **Config** -> **Full Parameter List.**
6. Set the following parameters to the values shown in the table.

<table><thead><tr><th>Parameter</th><th width="191.33333333333331">Value</th><th>Description</th></tr></thead><tbody><tr><td>AVD_ENABLE</td><td>1</td><td>Enable alarm and avoidance using ADSB</td></tr><tr><td>AVD_W_ACTION</td><td>1</td><td>Enable warning<br><br>0: Disable<br>1: Enable</td></tr><tr><td>AVD_F_ACTION</td><td>1</td><td><p>Controls how the vehicle should respond to a projected near-miss </p><p></p><p>0: No response</p><p>1: Report </p><p>2: Climb or descend </p><p>3: Move horizontally </p><p>4: Move perpendicularly in 3D </p><p>5: RTL </p><p>6: Hover</p></td></tr><tr><td>AVD_F_RCVRY</td><td>3</td><td><p>Sets how the vehicle will behave after it has cleared the near-miss area. </p><p></p><p>0: Remain in EXCER_ADSB status</p><p>1: Resume previous flight mode</p><p>2: RTL</p><p>3: Resume if AUTO else Loiter</p></td></tr></tbody></table>

7. Click **Write Params**.

For more information on these settings, go to [http://ardupilot.org/plane/docs/common-ads-b-receiver.html](http://ardupilot.org/plane/docs/common-ads-b-receiver.html).

The following Github link can be used to revise and update the ADS-IN carrier board informatio&#x6E;**:** \
[https://github.com/CubePilot/cubepilot-docs/blob/master/carrier-boards/ads-b-carrier-board.md](ads-b-carrier-board.md)

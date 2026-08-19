---
description: This section explains how to resolve firmware-related issues.
---

# Recovering the Firmware

Recovering the firmware may be necessary if a firmware update fails or incompatible firmware is loaded. Attempt flashing the bootloader via the SWD port if the Here4 LEDs are solid white.

## Prerequisites

The following information is for J-Link devices, but it can also be applied to similar devices when using an ST-Link.<br>

* J-Link device:
  * [EDU Mini](https://www.segger.com/products/debug-probes/j-link/models/j-link-edu-mini/) V2, for personal/educational use (and an adapter board)
  * [BASE Compact](https://shop.segger.com/debug-trace-probes/debug-probes/j-link/j-link-base-compact), for commercial use
    * Pinout: [https://www.segger.com/products/debug-probes/j-link/technology/interface-description/](https://www.segger.com/products/debug-probes/j-link/technology/interface-description/)&#x20;
* **6-pin JST SUR** plug for SWD port
  * Refer here for SWD port pinout: [FMU Debug pinout](https://docs.cubepilot.org/user-guides/autopilot/the-cube/introduction/interface-specifications#fmu-debug)
* Download and install “J-Link Software and Documentation Pack” from [segger.com/downloads/jlink/](https://www.segger.com/downloads/jlink/)&#x20;
* Download the bootloader file for your flashing tool:
  * JLink: [Here4\_bl.hex](https://github.com/CubePilot/GNSSPeriph-release/raw/refs/heads/release/bootloaders/Here4_bl.hex)
  * STLink: [Here4\_bl.bin](https://github.com/CubePilot/GNSSPeriph-release/raw/refs/heads/release/bootloaders/Here4_bl.bin)
* De-cased Here4
  * Remove M3 bolt (2 mm hex head)
  * Gently separate the two housing parts, using a plastic tool to pry the clips apart
  * Images for reference:

{% columns %}
{% column %}
<figure><img src="../.gitbook/assets/unknown (2).jpeg" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (4).jpeg" alt=""><figcaption></figcaption></figure>
{% endcolumn %}

{% column valign="bottom" %}
<figure><img src="../.gitbook/assets/unknown (3).jpeg" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/unknown (5).jpeg" alt=""><figcaption></figcaption></figure>
{% endcolumn %}
{% endcolumns %}

## Procedures

### J-Link with J-Flash Lite

1. Plug Here4 into CAN port of a Cube (for power).
2. Plug J-Link into the SWD port on the Here4.

<img src="../.gitbook/assets/unknown (3).png" alt="" height="279" width="279">

3. Connect J-Link to PC over USB.
4. Open **J-Flash Lite** (JFlashLite.exe).
5. Use the following parameters:

<img src="../.gitbook/assets/unknown (4).png" alt="" height="252" width="292">

6. Click **OK**.
7. Plug the Cube into power, power up the Here4, and click **Erase Chip**.

<img src="../.gitbook/assets/unknown (5).png" alt="" height="275" width="356">

8. Click the button under Data File and open the **Here4\_bl.hex** file.
9. Click **Program Device**.
10. Check the log for the following output:

<img src="../.gitbook/assets/unknown (6).png" alt="" height="134" width="354">

11. Unplug the power and SWD connections.
12. Plug in Cube, connect to Mission Planner and verify Here4 shows up in DroneCAN (in **MAINTENANCE** mode).
13. Update the Here4 (**Menu** -> **Update** -> **Yes, search the internet for updates**).
14. Verify Here4 shows up in **OPERATIONAL** mode.

## Connect Programming Devices

This section contains the pinout on either side to assist in connecting the J-Link or ST-Link device to the SWD port. The **same pinout is used for J-Link and ST-Link devices** with 20-pin connectors.

Solder or crimp the 6-pin JST SUR wires onto 2.54 mm female header plugs (if using programming devices with header pins).

<table><thead><tr><th width="154.2000732421875">Pin Number
(SWD port)</th><th width="210.4000244140625">Name
(SWD port)</th><th width="153.7999267578125">Pin Number
(JTAG Interface)</th><th width="210.39990234375">Name
(JTAG Interface)</th></tr></thead><tbody><tr><td><strong>1</strong></td><td>VDD 5V PEIPH</td><td><strong>1</strong></td><td>VTref</td></tr><tr><td><strong>2</strong></td><td>FMU_TX (SERIAL 5)</td><td>Not Connected</td><td>Not Connected</td></tr><tr><td><strong>3</strong></td><td>FMU_RX (SERIAL 5)</td><td>Not Connected</td><td>Not Connected</td></tr><tr><td><strong>4</strong></td><td>FMU-SWDIO</td><td><strong>7</strong></td><td>SWDIO</td></tr><tr><td><strong>5</strong></td><td>FMU-SWCLK</td><td><strong>9</strong></td><td>SWCLK</td></tr><tr><td><strong>6</strong></td><td>GND</td><td><strong>4</strong></td><td>GND</td></tr></tbody></table>

* [SWD port pinout](https://docs.cubepilot.org/autopilot/the-cube/introduction/interface-specifications#fmu-debug)
* [J-Link pinout](https://www.segger.com/products/debug-probes/j-link/technology/interface-description/) ('SWD Connector Pinout' section)
* [ST-Link pinout](https://www.utmel.com/components/stlinkv2-in-circuit-debugger-pinout-datasheet-and-programming?id=237#cat2)




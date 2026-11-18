---
description: >-
  All-band RTK GNSS receiver with an external antenna. HereX Single and HereX
  Dual.
---

# HereX Manual

## Overview

HereX is an all-band (L1, L2, L5, L6) RTK GNSS receiver that takes an external antenna on an SMA port. It comes in two versions:

|                                       | HereX Single    | HereX Dual                                           |
| ------------------------------------- | --------------- | ---------------------------------------------------- |
| Receiver                              | u-blox ZED-X20P | u-blox ZED-X20D                                      |
| Antenna ports                         | 1               | 2                                                    |
| Heading from GNSS (no compass needed) | No              | Yes, see [HereX Dual Heading](herex-dual-heading.md) |

HereX connects to the flight controller over serial.

{% hint style="info" %}
Setup on this page is documented for **Cube Orange+** with ArduPilot.
{% endhint %}

## Features

* RTK with RTCM 3.4 corrections in, and RTCM 3.4 output
* PPP-RTK with SPARTN 2.0.2 corrections
* Jamming and spoofing detection, Galileo OSNMA
* Powered SMA antenna port (see [Antennas](herex.md#antennas) for the differences between HereX Single and HereX Dual)
* 10-pin locking connector, USB-C, backup cell for hot starts
* Castellated edges, so the module can be soldered onto your own PCB

## Specifications

| Item                              | HereX Single                                                                                                   | HereX Dual                                                            |
| --------------------------------- | -------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| Bands                             | L1, L2, L5, L6                                                                                                 | L1, L2, L5, L6                                                        |
| Main signals                      | GPS L1C/A, L2C, L5; Galileo E1, E5a, E6; BeiDou B1I, B1C, B2a, B3I; QZSS L1C/A, L1C/B, L2C, L5; NavIC L5; SBAS | Same, plus GLONASS L1OF, L2OF (restricted in some areas) and QZSS L1S |
| RTK accuracy (horizontal CEP)     | 0.6 cm + 1 ppm                                                                                                 | 0.6 cm + 1 ppm                                                        |
| RTK accuracy (vertical, median)   | 1 cm + 1 ppm                                                                                                   | 1 cm + 1 ppm                                                          |
| PPP-RTK accuracy (horizontal CEP) | < 6 cm                                                                                                         | < 6 cm                                                                |
| Convergence time                  | RTK < 7 s; PPP-RTK < 40 s                                                                                      | RTK < 7 s; PPP-RTK < 40 s                                             |
| Navigation update rate            | up to 25 Hz                                                                                                    | up to 20 Hz (RTK)                                                     |
| Time to first fix                 | cold 25 s; hot 2 s                                                                                             | cold 25 s; hot 2 s                                                    |
| Heading accuracy                  | –                                                                                                              | 0.1° RMS at 1 m baseline                                              |
| Heading update rate               | –                                                                                                              | up to 20 Hz                                                           |
| Protocols                         | NMEA, UBX, RTCM 3.4, SPARTN 2.0.2                                                                              | NMEA, UBX, RTCM 3.4, SPARTN 2.0.2                                     |
| Time pulse accuracy               | 20 ns RMS                                                                                                      | 20 ns RMS                                                             |
| Supply                            | 5 V                                                                                                            | 5 V                                                                   |

Performance figures are typical values from the u-blox ZED-X20P and ZED-X20D data sheets (both R06). They depend on antenna, baseline length, sky view and atmospheric conditions.

## Connectors

![](<../.gitbook/assets/herex-case-top (3).png>)

The connector and antenna positions above are viewed from above with the logo upright. On HereX Single the secondary antenna opening is capped.

### 10-pin connector

The drawing above shows each pin number: odd pins on the row nearer the case edge, even pins on the row towards the logo.

| Pin | Signal               | Direction (HereX side) | Receiver pin |
| --- | -------------------- | ---------------------- | ------------ |
| 1   | 5 V                  | Power in               | –            |
| 2   | UART1 RX             | In                     | 43 RXD       |
| 3   | UART1 TX             | Out                    | 42 TXD       |
| 4   | UART2 RX             | In                     | 26 RXD2      |
| 5   | UART2 TX             | Out                    | 27 TXD2      |
| 6   | LED clock            | In                     | –            |
| 7   | LED data             | In                     | –            |
| 8   | PPS (time pulse)     | Out                    | 53 TIMEPULSE |
| 9   | EXTINT (event input) | In                     | 51 EXTINT    |
| 10  | GND                  | –                      | –            |

RX and TX are named from the receiver's side: UART1 RX connects to the flight controller's TX.

### USB-C

USB-C connects the receiver to a computer for configuration and receiver firmware updates with u-blox u-center 2.

### Connector part numbers

| Connector    | On the unit (header, male)                                         | Mates with (cable side, female)                                        |
| ------------ | ------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| HereX 10-pin | Molex Micro-Lock Plus 1.25 mm dual-row vertical header 505433-1051 | Molex 505432-1001 receptacle housing with Molex 505431 crimp terminals |

## Wiring to Cube Orange+

![HereX to Cube Orange+ wiring](<../.gitbook/assets/herex-wiring-cube-orange-plus (4).png>)

The supplied cable connects HereX to the Cube Orange+ **GPS1** port. The drawing shows the signal mapping. The PPS and EXTINT leads are optional; HereX works without them.

* **PPS:** ArduPilot on Cube Orange+ does not use a GPS PPS signal. Leave the PPS lead unconnected.
* **EXTINT:** see [Event input (EXTINT)](herex.md#event-input-extint).

## Antennas

For best performance, use an **active** antenna that meets the minimum requirements below. Tested antennas: Calian helical antennas (active) and a Kyocera all-band antenna (passive, on HereX Single).

### Active antenna minimum requirements

| Requirement                                           | Value                                                          |
| ----------------------------------------------------- | -------------------------------------------------------------- |
| Supply voltage                                        | Runs from 3.3 V, the voltage HereX puts on the centre pin      |
| Gain seen by the receiver (normal-gain mode, default) | 17 dB to 40 dB                                                 |
| Gain seen by the receiver (low-gain mode)             | 20 dB to 50 dB                                                 |
| Noise figure                                          | < 3.5 dB                                                       |
| Polarization                                          | RHCP                                                           |
| Bands                                                 | L1, L2, L5 and L6 (E6, B3) to use all the signals HereX tracks |
| Group delay variation in-band                         | < 10 ns typical                                                |
| Out-of-band rejection                                 | 40 dB typical                                                  |
| Phase centre variation, all directions                | < 10 mm                                                        |

The gain figures include losses in cables, connectors and filters between the antenna and HereX. An antenna that covers fewer bands works, but HereX then tracks only the signals in those bands. Values are from the u-blox ZED-X20P and ZED-X20D integration manuals (antenna specifications).

### Passive antennas

A **passive** antenna can be used when all of these apply:

* the connection between the antenna and the module is low-loss: an on-board or patch antenna a few cm of trace away from the module, or a short cable to the antenna;
* the antenna has an open view of the sky;
* you need only a position fix, not RTK or heading.

The u-blox receiver in HereX has its own internal gain: low-noise amplifiers (LNAs) and programmable gain amplifiers (PGAs) in each RF block, so a passive antenna works. The 17 dB minimum in the table above is the extra gain specified from an active antenna. A passive antenna adds none, so performance is lower than with an active antenna.

### Antenna power

|                           | HereX Single                | HereX Dual                  |
| ------------------------- | --------------------------- | --------------------------- |
| Ports                     | Primary only                | Primary and Secondary       |
| Voltage on the centre pin | about 3.3 V                 | Treat both ports as powered |
| Short-circuit protection  | Yes, current limited (10 Ω) | **No**                      |

### Settings (u-center 2)

These are u-blox receiver settings. Change them in u-center 2 over USB-C and save them to the receiver's flash. ArduPilot's automatic configuration (`GPS_AUTO_CONFIG = 1`) does not include these settings.

**High-gain antennas:** the receiver accepts 17 dB to 40 dB of external gain in its default normal-gain mode, and 20 dB to 50 dB in low-gain mode, measured at the receiver input after cable and connector losses. If the gain is above 40 dB, set the receiver to low-gain mode, then reset the receiver. Low-gain mode raises the receiver's own noise figure (L1: 6.5 dB normal, 11 dB low gain), so use it only when the gain needs it. Above 50 dB is outside both modes; exceeding the maximum external gain degrades the receiver's performance.

| Key                           | Value |
| ----------------------------- | ----- |
| `CFG-HW-RF1_LNA_MODE_LOWGAIN` | 1     |
| `CFG-HW-RF2_LNA_MODE_LOWGAIN` | 1     |
| `CFG-HW-RF3_LNA_MODE_LOWGAIN` | 1     |

{% hint style="warning" %}
`GPS_AUTO_CONFIG = 3` resets the receiver to its defaults before ArduPilot applies its own settings, which removes these u-center changes. Use `GPS_AUTO_CONFIG = 1` (default).
{% endhint %}

## ArduPilot setup (Cube Orange+)

HereX is supported from **ArduPilot 4.7.0**.

HereX Dual Heading setup should only be completed for the HereX Dual.&#x20;

| Parameter                  | Value                                                            |
| -------------------------- | ---------------------------------------------------------------- |
| `SERIAL3_PROTOCOL` (GPS1)  | 5 (GPS)                                                          |
| `GPS1_TYPE`                | 2 (u-blox)                                                       |
| `GPS_AUTO_CONFIG`          | 1                                                                |
| `GPS1_POS_X` / `_Y` / `_Z` | antenna position from the vehicle's centre of gravity, in metres |

Check it works:

* Outdoors, the ground station reports a 3D fix.
* After corrections are sent, it reports RTK Float, then RTK Fixed.

### Status LED

HereX has a status LED that ArduPilot drives as a notification LED (ProfiLED). The supplied cable carries the LED clock and data on GPS1 pins 6 and 7, and the Cube's IO processor sends the LED signal on them (ProfiLED\_IOMCU). The status LED will not work prior to ArduPilot 4.7.0.

| Parameter          | Value                                                                                |
| ------------------ | ------------------------------------------------------------------------------------ |
| `BRD_OPTIONS`      | add bit 9, "Use safety pins as profiled" (value 512), then reboot                    |
| `NTF_LED_TYPES`    | include bit 19 (ProfiLED\_IOMCU); on by default on Cube Orange+ from ArduPilot 4.7.0 |
| `BRD_SAFETY_DEFLT` | 0, so the vehicle starts with safety off                                             |

GPS1 pins 6 and 7 are the port's safety-switch pins. With the HereX LED on them, the safety state is set from the ground station or by `BRD_SAFETY_DEFLT`, not by a safety switch on GPS1.

### HereX Dual Heading

HereX Dual heading needs ArduPilot 4.8 or later (4.7.x once the backport is released) and receiver firmware HDG 2.00 or later. Set the parameters above, plus:

| Parameter                     | Value                                                                                                       |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------- |
| `GPS1_MB_TYPE`                | 1 (RelativeToCustomBase)                                                                                    |
| `GPS1_MB_OFS_X` / `_Y` / `_Z` | position of the Primary antenna measured from the Secondary antenna, in metres (X forward, Y right, Z down) |
| `EK3_SRC1_YAW`                | 3 (GPS with compass fallback), or 2 (GPS only)                                                              |

`GPS_AUTO_CONFIG = 1` turns on the heading output. Keep `GPS1_TYPE = 2`; do not use the moving-baseline base or rover GPS types. For antenna placement, offset examples and checks, see [HereX Dual Heading](herex-dual-heading.md).

## RTK corrections

Send RTCM 3.4 corrections from a base station or network through a ground station that forwards them to the vehicle over MAVLink (`GPS_RTCM_DATA`). ArduPilot passes them to HereX.

## Event input (EXTINT)

EXTINT lets the receiver timestamp an event, such as a camera trigger, in GNSS time.

1. Set the camera trigger on an AUX output: `CAM1_TYPE = 1` and `SERVOx_FUNCTION = 10` (camera trigger) on that output.
2. Wire the same AUX signal to the HereX EXTINT lead as well as to the camera.
3. In u-center 2, enable the UBX-TIM-TM2 message on UART1 and save it to flash.

ArduPilot logs UBX-TIM-TM2 messages it receives as `UBXT` log messages.

## Castellated pads

![HereX castellated pads, top view](<../.gitbook/assets/herex-castellation (7).png>)

**Left edge (chamfered-corner side), from the 10-pin end**

| Pad              | Function                                                 |
| ---------------- | -------------------------------------------------------- |
| VDD\_5V          | 5 V supply in (same as 10-pin pin 1)                     |
| VDD\_3V3         | 3.3 V receiver supply, from the on-board regulator       |
| VBKUP            | Backup supply, connected to the on-board backup cell     |
| VBUS             | USB 5 V; supplies the receiver's USB through a regulator |
| USB\_DP          | USB data +, through an ESD filter                        |
| USB\_DM          | USB data −, through an ESD filter                        |
| S̅A̅F̅E̅B̅O̅O̅T̅ | Safeboot input, active low                               |
| EXTINT           | Event input                                              |
| PPS              | Time pulse output                                        |
| GND              | Ground                                                   |

**Right edge, from the 10-pin end**

| Pad            | Function                                                             |
| -------------- | -------------------------------------------------------------------- |
| GPS\_TX        | UART1 output (same as 10-pin pin 3)                                  |
| GPS\_RX        | UART1 input (same as 10-pin pin 2)                                   |
| GPS\_TX2       | UART2 output (same as 10-pin pin 5)                                  |
| GPS\_RX2       | UART2 input (same as 10-pin pin 4)                                   |
| R̅E̅S̅E̅T̅     | Reset input, active low                                              |
| RTK\_STAT      | RTK status output                                                    |
| GEO/HEAD\_STAT | Geofence status (HereX Single) or heading status (HereX Dual) output |
| LED\_DAT       | Status LED data (same as 10-pin pin 7)                               |
| LED\_CLK       | Status LED clock (same as 10-pin pin 6)                              |
| GND            | Ground                                                               |

Pads: 10 per side, 2.54 mm (100 mil) pitch, the standard spacing used in the industry, plated hole 1 mm, centred on the board edge. The board is 31.0 × 40.0 mm, with four 2.4 mm mounting holes, one in each corner (centres 27.39 mm apart across the board and 36.60 mm along it). A PCB footprint for HereX will be available soon.

## Downloads

* [HereX case, top and bottom assembled (STEP, zipped)](../.gitbook/assets/herex-case-step.zip)

## Receiver firmware

Download the latest receiver firmware from u-blox:

* HereX Single (ZED-X20P): [https://www.u-blox.com/en/product/zed-x20p-module](https://www.u-blox.com/en/product/zed-x20p-module)
* HereX Dual (ZED-X20D): [https://www.u-blox.com/en/product/zed-x20d-module](https://www.u-blox.com/en/product/zed-x20d-module)

Update it with u-center 2 over USB-C.

## Troubleshooting

| Symptom                                                  | Check                                                                                                                                                                                                         |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| No fix                                                   | Antenna connected to the Primary port; open sky. Active antenna: it runs from 3.3 V (some need 5 V and stay off). Passive antenna: see [Passive antennas](herex.md#passive-antennas) for when one can be used |
| HereX Dual: receiver resets when an antenna is connected | The antenna path may be shorting the centre pin to ground. Disconnect it, check for a DC short, and add a DC block if needed                                                                                  |
| HereX LED stays off                                      | `BRD_OPTIONS` bit 9 is set and the autopilot was rebooted; `NTF_LED_TYPES` includes bit 19 (ProfiLED\_IOMCU); see [Status LED](herex.md#status-led)                                                           |

---
description: GNSS heading from one HereX Dual with two antennas, no compass needed.
---

# HereX Dual Heading

## How it works

HereX Dual (u-blox ZED-X20D) has one receiver and two antenna ports. The receiver measures the direction from **Antenna 1** (Primary) to **Antenna 2** (Secondary) and sends it to ArduPilot, which uses it as the vehicle's yaw. Heading works with the vehicle at rest.

This is different from moving-baseline setups that use two separate GPS units: there is no second GPS and no correction link between units.

|                                                    | Value                    |
| -------------------------------------------------- | ------------------------ |
| Heading accuracy                                   | 0.1° RMS at 1 m baseline |
| Heading update rate                                | up to 20 Hz              |
| Minimum antenna separation, horizontal (ArduPilot) | 0.05 m                   |

## Requirements

* HereX Dual connected to Cube Orange+ GPS1 (see [HereX Manual](herex.md#wiring-to-cube-orange)).
* ArduPilot 4.8 and later. ArduPilot 4.7.x gets heading once the backport is released.
* Receiver firmware HDG 2.00 or later. Download it from [u-blox](https://www.u-blox.com/en/product/zed-x20d-module).
* Two active antennas that run from 3.3 V, with clear sky view. Identical antennas, mounted the same way on the same plane, are recommended.

## Antenna ports

![](<../.gitbook/assets/herex-case-top (3).png>)

With the HereX logo upright, viewed from above, the antenna ports are at the top: the **Primary (Antenna 1)** port is the top-right one and the **Secondary (Antenna 2)** port is the top-left one.

## Antenna placement and offsets

![Dual antenna placement, top view of vehicle](<../.gitbook/assets/herex-antenna-offsets (3).png>)

`GPS1_MB_OFS_X`, `GPS1_MB_OFS_Y` and `GPS1_MB_OFS_Z` give the position of the **Primary** antenna measured from the **Secondary** antenna, in metres, in the vehicle's body frame: X forward, Y right, Z down.

| Antenna layout                                      | `GPS1_MB_OFS_X` | `GPS1_MB_OFS_Y` | `GPS1_MB_OFS_Z` |
| --------------------------------------------------- | --------------- | --------------- | --------------- |
| Across the vehicle, Primary 1.0 m left of Secondary | 0               | -1.0            | 0               |
| Along the vehicle, Primary 1.0 m ahead of Secondary | 1.0             | 0               | 0               |

{% hint style="warning" %}
For the horizontal layouts above, a reversed offset sign makes the heading 180° out, and ArduPilot does not detect it. Check the heading against a known direction before flight.
{% endhint %}

ArduPilot also rejects the heading if the measured distance between the antennas and the length of the offset you set differ by more than 20 % of the smaller of the two, so measure the offsets accurately. Mount the antennas mainly horizontal to each other.

## Parameters

| Parameter                     | Value                                                                                                           |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------- |
| `SERIAL3_PROTOCOL` (GPS1)     | 5 (GPS)                                                                                                         |
| `GPS1_TYPE`                   | 2 (u-blox)                                                                                                      |
| `GPS_AUTO_CONFIG`             | 1 (turns on the heading output)                                                                                 |
| `GPS1_MB_TYPE`                | 1 (RelativeToCustomBase)                                                                                        |
| `GPS1_MB_OFS_X` / `_Y` / `_Z` | see above                                                                                                       |
| `GPS1_POS_X` / `_Y` / `_Z`    | Primary antenna position from the vehicle's body-frame origin, in metres                                        |
| `INS_POS1_X` / `_Y` / `_Z`    | Cube (IMU) position from the vehicle's body-frame origin, in metres; 0 (default) when the Cube is at the origin |
| `EK3_SRC1_YAW`                | 3 (GPS with compass fallback), or 2 (GPS only)                                                                  |

Use `GPS1_MB_TYPE = 1`, `EK3_SRC1_YAW = 3` and `GPS1_TYPE = 2`. Do not use the moving-baseline base or rover GPS types with HereX Dual.

## Check it works

* Outdoors with clear sky, wait for the receiver to get a fixed solution between its two antennas. Heading is only used while this solution is fixed. This does not need RTK corrections; the position's RTK Fixed status is separate and does need corrections.
* In the flight log, `GPYW.OK = 1` means ArduPilot accepted that GPS heading sample. Compare `ATT.Yaw` with the GPS heading only while `GPYW.OK` is 1.
* Rotate the vehicle and check the heading in the ground station turns the same way and matches a known direction.

## Limits and troubleshooting

| Symptom                                      | Check                                                                                                                        |
| -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| No GPS heading                               | Antennas at least 0.05 m apart horizontally; clear sky at both antennas; `GPS1_MB_TYPE = 1`; offsets set                     |
| Heading rejected                             | Offset length and measured antenna distance differ by more than 20 % of the smaller one                                      |
| Heading 180° out                             | Offset sign: the offsets describe the Primary antenna's position measured from the Secondary                                 |
| Heading drops out                            | ArduPilot stops using GPS heading if it has had no valid heading for 400 ms, then falls back as `EK3_SRC1_YAW` allows        |
| Receiver resets when an antenna is connected | The antenna path may be shorting the centre pin to ground. Disconnect it, check for a DC short, and add a DC block if needed |

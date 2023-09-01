# SB\_0000004 Limited power capacity of the RCIN power rail on Pixhawk Autopilots

**Latest update please refer to:**\
[SB\_0000004Limited power capacity of the RCIN power rail on Pixhawk Autopilots](https://discuss.cubepilot.org/t/sb-0000004limited-power-capacity-of-the-rcin-power-rail-on-pixhawk-autopilots/1853)

This bulletin applies to ALL Pixhawk and Pixhawk related hardware including all genuine boards (3DR and CubePilot) as well as all clones and derivatives.

DO NOT POWER anything off the RCIN power pin other than a traditional RC Receiver, and do not connect any servos to the RCIN pin, nor to the Receiver itself.

Companion Computers like HereLink, Raspberry Pi, Nvidia Jetson etc (and any others) should not be powered from this pin. They should be powered separately from the Autopilot.

Failure to follow this safety Bulletin could cause loss of control of your vehicle.

This applies to ALL Autopilots that run PX4 or Ardupilot.

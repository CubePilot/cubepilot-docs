# SB\_0000005 I2C Storm can cause Inflight Reboots, Chibios ONLY, not Nuttx (all The Cube hardware)

**For the latest updates, refer to the following link:**\
[SB\_0000005 I2C Storm can cause inflight reboots, Chibios ONLY, not Nuttx (all The Cube hardware)](https://discuss.cubepilot.org/t/sb-0000005-i2c-storm-can-cause-inflight-reboots-chibios-only-not-nuttx-all-cube-and-pixhawk-hardware-including-clones-and-derivatives/2419)

**CRITICAL**

**Update ALL CHIBIOS Copter USERS MUST USE 3.6.12 or cease flight**.

Critical Safety Update is in Copter 3.6.12\
Update Friday, 13th December. This is a Chibios only issue. Old hardware running old custom or stock Nuttx firmware is not affected by this SB.

Due to an issue with a bug in the I2C system for ArduCopter for 3.6.10 version and earlier and Arduplane before 4.0.

Ground any vehicles that have not BEEN updated to Arduplane 4.0 or 3.6.11 for Arducopter or later.

This issue has lead to aircraft failing mid flight, and the details can be found in the Ardupilot release notes for 3.6.11.

A rare case can still occur in 3.6.11, 3.6.12 will be released shortly, and as soon as it is, this notice will be updated.

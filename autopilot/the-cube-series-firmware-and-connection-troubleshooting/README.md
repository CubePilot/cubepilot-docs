# The Cube - Firmware Installation & Connection Troubleshooting

## The Cube Autopilot All Models Out The Box

All Cube Autopilot models now come with no autopilot software installed from the factory and as such you will need to install your chosen firmware such as Ardupilor or PX4 before you can use it.

### Supported Ardupilot Versions

The Cube Black, Purple and Blue models are compatible with older versions of Ardupilot and PX4 software however the Cube Orange and Cube Yellow modes are using the STM32F7 and the STM32H7 microcontrollers that require you are using the latest drivers and software to use these models.

**Note** It is strongly advised to use the latest stable release of Ardupilot at all times to ensure you are uptosdate with any bug and feature updates.

### Cube Black, Blue and Purple

These Cube models are supported in older versions of Ardupilot however its strogly advised to use Arducopter 3.6.12 or Arduplane 3.9.11 or later due to a critical I2C Storm bug fixes.

More Information on this specific issue can be found in the Cubepilot bulitins or Ardupilot forum.

Cubepilot Bulletin's [https://discuss.cubepilot.org/t/sb-0000005-i2c-storm-can-cause-inflight-reboots-chibios-only-not-nuttx-all-cube-and-pixhawk-hardware-including-clones-and-derivatives/2419](https://discuss.cubepilot.org/t/sb-0000005-i2c-storm-can-cause-inflight-reboots-chibios-only-not-nuttx-all-cube-and-pixhawk-hardware-including-clones-and-derivatives/2419)

Ardupilot forums [https://discuss.ardupilot.org/t/copter-3-6-12-has-been-released-critical-safety-update-if-you-are-flying-3-6-10-or-older/50130](https://discuss.ardupilot.org/t/copter-3-6-12-has-been-released-critical-safety-update-if-you-are-flying-3-6-10-or-older/50130)

### The Cube Orange and Cube Yellow

These models are supported in Arducopter, Rover and Plane version 4.0 and later only.

**Note** Its strongly advised to be using ChibiOS versions of Ardupilot with all Cube models unless you have a specific reasons otherwise.

##

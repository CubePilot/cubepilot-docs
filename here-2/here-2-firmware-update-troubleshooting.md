# Here 2 Firmware Update Troubleshooting

Most issues updating the HERE 2 are related to not following the update process exsactly or not leaving enough time before rebooting after updaing the bootloader, some issues that have been see are

* Here 2 not showing in SLCAN
* Here 2 No showing in SLCAN after updating bootloader step
* LED's stuck solid green

If you are having trouble updating you Here 2 firmware or your Here 2 is not showing in SLCAN check the following

## Check CAN Port

On some early standard carrier board models including the Intel Edision verison the CAN ports were incorrectly labled and swapped around, this could result in CAN 1 and CAN 2 showing reversed in SLCAN.

## Latest Mission Planner

Make sure you are using the latest release of mission planner, you can download this from [https://firmware.ardupilot.org/Tools/MissionPlanner/](https://firmware.ardupilot.org/Tools/MissionPlanner/)

If you are still having issues with SLCAN now showing the Here 2 try using the Beta verions of Mission Planner, you can download this from the help page.

## Ardupilot

You should have the latest verions of Ardupilot on your Cube when trying to update your Here 2 GPS, if your having prblems getitng the Here 2 to show in SLCAN make sure you have updated your Cube.

If your still having issues try flashing your cube to the latest version of a diferent vehicle such as Plane or Rover if your using Copter.

### Boot Delay

If the above does not help try increasing the boot delay pram in ardupilot as follows

BRD\_BOOT\_DELAY = 7000

**Note**: You should return this to the default value after updating is complete

## Solid Green LED's

If your Here 2 has solid green led after updating its likely the full process has not competed, you must update both the bootloader and then the application, the update must be completed in full as per the instructions.


# Instructions for Connecting the Here 2 to CAN and Using the UAVCAN Interface in Mission Planner to Update the Here 2 Bootloader

## Step 1: Switching the Here 2 to CAN mode

<a href='https://drive.google.com/file/d/1OyvX74LAcSg1MsAmUDkUtQ-vBFe5V8Xl/view?usp=drive_open&amp;usp=embed_facebook&source=ctrlq.org'><img src='https://lh4.googleusercontent.com/VXlIAYaEPQgbGGoqJB24UemMIfHjaE6vIj0zicG4SXb9sD1KcQ4O1ogB7Hs=w1500' /></a>

* Remove the case from the Here 2. 

* Unplug the 8-wire cable and replace it with the included 4-wire CAN cable. 

* Move the switch from the I2C position to the CAN position.

**Note: This step is only required if your Here 2 has the 8-wire Serial/I2C cable which plugs in to the GPS 2 connector on the carrier board. If your Here 2 already has the 4-wire CAN cable attached, you can skip this step.**

## Step 2: Connect to the Cube

<a href='https://drive.google.com/file/d/10SOJZlBlrhWcQqYUFbbiRgwPjovZQtfA/view?usp=drive_open&amp;usp=embed_facebook&source=ctrlq.org'><img src='https://lh6.googleusercontent.com/WAZxtXilm_2EEQDALRvZUOS0OBuOHA0w89yxyB4wUvh2-k-bvoPSpoRvAZo=w1500' /></a>

* Connect the CAN cable to the CAN 1 connector on the carrier board, as shown in the image to the left.

**Note: On standard carrier boards manufactured before June 2019, this connector is mislabeled as CAN 2. Connect as shown in the image to the left.**

## Step 3: Connect USB

* Using the supplied USB cable, connect the Cube to your computer.

## Step 4: Install or update Mission Planner

* The required version of mission planner is 1.3.66 or later. Mission planner can be retrieved from http://firmware.ardupilot.org

## Step 5: Download ArduCopter master

* Released versions of ArduCopter do not have support for SLCAN as of this writing. Download the latest master from http://firmware.ardupilot.org. The file that you need is called arducopter.apj Direct link: http://firmware.ardupilot.org/Copter/latest/CubeBlack/arducopter.apj

## Step 6: Flash ArduCopter master

<a href='https://drive.google.com/file/d/113KiFeolq_bNjWCn6MdYgKpcd1esJPVP/view?usp=drive_open&amp;usp=embed_facebook&source=ctrlq.org'><img src='https://lh6.googleusercontent.com/VZavPp8TkIx_6273zuAPG1XPn4bNlGHtzAWrpb9HyD9roN8_hfib3NLIIkU=w1500' /></a>

* Launch Mission Planner. Click “Initial Setup,” then “Load custom firmware.” Navigate to the arducopter.apj file that you downloaded and select it.

## Step 7: Enable CAN

<a href='https://drive.google.com/file/d/1AEvbAlRDUShnEx669_xhDqGHRVI8qhzk/view?usp=drive_open&amp;usp=embed_facebook&source=ctrlq.org'><img src='https://lh3.googleusercontent.com/6c2BEvCvsJygUrk17jkPod-IOjgB7AT6sp3H4_DyFNFxYTCFuhkVlJARvoQ=w1500' /></a>

* Click “Config/Tuning,” then “Full Parameter List,” then search for “CAN_,” change CAN_P1_DRIVER to 1 and click “Write Params.”

## Step 8: Reboot the cube

* Unplug the USB cable, plug it back in and reconnect Mission Planner.

## Step 9: Using the Mission Planner SLCAN interface

<a href='https://drive.google.com/file/d/1Udtt0dx3uayLZXv9QwfYUtYOvo0AM3ap/view?usp=drive_open&amp;usp=embed_facebook&source=ctrlq.org'><img src='https://lh6.googleusercontent.com/cDaMdU75-mAk8jqwjNwrrmLPV5Zt9sNwQ1wEffs-RnO62kdkIOzrD32j2WQ=w1500' /></a>

* Click “Initial Setup,” then “Optional Hardware,” then UAVCAN, then “SLCan Mode CAN1.” Connected CAN devices (in this case, a Here 2) will be listed.

## Step 10: Flash the bootloader updater

<a href='https://drive.google.com/file/d/16fujVXni65MIUFjo7r-Ah8joPcM4FvC4/view?usp=drive_open&amp;usp=embed_facebook&source=ctrlq.org'><img src='https://lh4.googleusercontent.com/VnOcw-GtvGVlsShzFpAs1XjmgXWveJvuD4l3ZGKVBV42ArOgIcfcyupXos4=w1500' /></a>

* The bootloader updater performs the procedure listed to the left, which will start immediately after the firmware update completes.

* On the Here 2 entry in the list, select “Update,” navigate to the bootloader_updater file and open it. 

**After this point, DO NOT DISCONNECT POWER UNTIL THE LEDS ARE EITHER GREEN OR YELLOW, OR 3 MINUTES HAVE ELAPSED.**

## Step 11: Flash the application

* Follow the same procedure as in Step 10, but select the file Here2_com.hex.here_2.1 file instead.

# Mission Planner

Mission Planner is a ground control software that is used to configure and control the UAV. The following section explains how to download, set up, or update Mission Planner.

### Installing Mission Planner

To download Mission Planner, complete the following steps:

1. Go to the following website [https://ardupilot.org/planner/docs/mission-planner-installation.html](https://ardupilot.org/planner/docs/mission-planner-installation.html).

<figure><img src="../../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-x-prod.appspot.com_o_spaces_2F-LUhw7cdLeWVORgnTA3i_2Fuploads_2FTbWK6IL5BQ6YIK22gGZn_2Fimage.avif" alt=""><figcaption></figcaption></figure>

2. Download the MSI Installer and run it. During the process, various drivers will be installed.&#x20;

{% hint style="info" %}
For older Mission Planner versions, the drivers need to be downloaded and installed separately. The drivers can be downloaded from the following link: [https://firmware.ardupilot.org/Tools/MissionPlanner/](https://firmware.ardupilot.org/Tools/MissionPlanner/)
{% endhint %}

### Connecting Mission Planner to The Cube

To connect Mission Planner to The Cube, select one of the following options:

**USB Cable**

1. Open Mission Planner.
2. Connect one end of the USB cable to the USB port of The Cube, and the other end to the USB port (not a USB hub) of the ground-based computer.
3. Select the corresponding COM port from the drop-down list and choose 11200 for the baud rate. If **Auto** is chosen, the baud date will be automatically chosen.
4. Click **Connect**.

**USB Telemetry**

1. Open Mission Planner.
2. Install The Cube to a carrier board.
3. The USB telemetry module typically features both a TELEM port and a USB port. Depending on the setup, choose one of the following options:
   * **Connect the TELEM port**: Use a telemetry cable to link the TELEM port on the module to the TELEM 1 or TELEM 2 port on the carrier board.
   * **Use the USB port**: Plug the module directly into the USB port of the ground-based computer and use the RF link.
4. Select the corresponding COM port from the drop-down list and choose 57600 for the baud rate. If **Auto** is chosen, the baud date will be automatically chosen.
5. Click **Connect**.

**WiFi Telemetry**

1. Open Mission Planner.
2. Add Ethernet support to The Cube. See the CubeNode ETH section for details.

{% content-ref url="/broken/pages/wpM2wNIaCUm6YWw2bNUI" %}
[Broken link](/broken/pages/wpM2wNIaCUm6YWw2bNUI)
{% endcontent-ref %}

2. Use an Ethernet cable to connect The Cube to a router.
3. Pair the GCS to the same router.
4. Select **UDP** or **TCP** for the port.
5. Click **Connect** and enter 14550 for the port number.

**Bluetooth Telemetry**

1. Open Mission Planner.
2. Install The Cube to a carrier board.
3. Connect a Bluetooth data link module such as the HC-06 module to the Telem 1 or Telem 2 port on The Cube.
4. Select the corresponding COM port from the drop-down list and choose 57600 for the baud rate. If **Auto** is chosen, the baud date will be automatically chosen.
5. Click **Connect**.

### Updating Mission Planner and its Drivers

To update the Mission Planner version, complete the following steps:

1. Open Mission Planner.
2. Click **Help** -> **Check for Updates.**

![Mission Planner Updates Screen](../../../.gitbook/assets/mission-planner-updates.JPG)

After updating Mission Planner, complete the following steps to update the drivers:&#x20;

1. Disconnect The Cube from the USB port.&#x20;
2. Open Mission Planner.
3. Press CTRL-F and click **Driver Clean** to remove the old drivers.

<figure><img src="../../../.gitbook/assets/https___files.gitbook.com_v0_b_gitbook-x-prod.appspot.com_o_spaces_2F-LUhw7cdLeWVORgnTA3i_2Fuploads_2FgVHIjWwe2lIkvq2Opfcy_2FScreenshot_202024-10-23_20124515.avif" alt=""><figcaption></figcaption></figure>

4. Download the latest drivers from the following website: [https://firmware.ardupilot.org/Tools/MissionPlanner/](https://firmware.ardupilot.org/Tools/MissionPlanner/)
5. Run the MSI Installer.
6. When the installation is complete, reboot the system and reconnect The Cube to the GCS to install the drivers.&#x20;

# The Cube FAQ

## 1. How do I Reset the Drivers on a Windows 10 when Attempting to Connect to The Cube?&#x20;

1. Open Mission Planner.&#x20;
2. Press Ctrl + F; then, click **Driver Clean** to remove the previously installed drivers.&#x20;

<figure><img src="../.gitbook/assets/image (32).png" alt=""><figcaption></figcaption></figure>

3. Close Mission Planner.&#x20;
4. Download and install the drivers again from the following link: [https://firmware.ardupilot.org/Tools/MissionPlanner/](https://firmware.ardupilot.org/Tools/MissionPlanner/).
5. Reboot Windows.
6. Connect The Cube to the System via a USB port and wait for the drivers to be uploaded.&#x20;
7. Open **Device Manager** and verify that both COM ports are correct. The following screenshot uses the <mark style="color:orange;">**CubeOrange**</mark> as an example.

![](<../.gitbook/assets/Cube Orange - Windows 10 - Chris_Goodall.jpeg>)

For additional details, refer to the following link:\
[https://discuss.cubepilot.org/t/cube-orange-on-win10/3655/14](https://discuss.cubepilot.org/t/cube-orange-on-win10/3655/14)

## 2. How do I Resolve USB Connection Issues between The Cube and Mission Planner?

Most USB connection issues are caused by outdated software or firmware. See below for the steps on how to resolve the problem:

**1.** Update Mission Planner and its drivers. For details, see the **Installing ArduPilot** section. If this does not work, go to the next step.

{% content-ref url="/broken/pages/PRGNYT96ktfizjUFGJYk" %}
[Broken link](/broken/pages/PRGNYT96ktfizjUFGJYk)
{% endcontent-ref %}

2. Update the Windows operating system to Windows 10 or above. If this does not work, go to the next step.
3. Open **Device Manager** and verify if the connected COM ports are correct. If not, reinstall the drivers from the following link: [https://firmware.ardupilot.org/Tools/MissionPlanner/](https://firmware.ardupilot.org/Tools/MissionPlanner/). The following shows the correct COM port connections for the different Cubes.&#x20;

* The **Cube Black**, <mark style="color:purple;">**Cube Purple,**</mark> and <mark style="color:blue;">**Cube Blue**</mark> should show a single COM port. The following screenshot uses the **Cube Black** as an example.

![Cube Black Com Ports in Device Manager ](../.gitbook/assets/cube-black-device-manager-port.jpg)

* Other colored Cubes should show two connected com ports. The following screenshot uses the <mark style="color:orange;">**CubeOrange**</mark> as an example.

![Cube Orange Com Ports in Device Manager ](../.gitbook/assets/cube-orange-device-manager-ports.jpg)

### 3. How do I Resolve the Driver Installation Issues for the Dual USB endpoint Cube Modules on a Windows 7 GCS?

Excluding the **Cube Black** and <mark style="color:purple;">**Cube Purple,**</mark> some issues could occur when installing drivers for dual USB endpoint Cube modules on a Windows 7 GCS. Using the <mark style="color:orange;">**Cube Orange**</mark> as an example, see below on how to resolve the problem:

1. Connect The Cube to the GCS.&#x20;
2. Open **Device Manager**.
3. Delete "CubePilot CUBE H7/F7" and then disconnect The Cube from the GCS.
4. Uninstall and reinstall the latest Cube drivers. The drivers can be downloaded from the following link: [https://firmware.ardupilot.org/Tools/MissionPlanner/](https://firmware.ardupilot.org/Tools/MissionPlanner/)
5. Reconnect the Cube to the GCS. The cube should appear as "CubeOrange-BL" in **Other Devices**.
6. Verify if the top entry changes to Cube and that Windows notifies you it is currently installing the device drivers.
7. Verify that "CubeOrange-BL" moves to **Ports** and is renamed as "Cube Orange Mavlink (COMx)".
8. If “CubeOrange-BL” does not move from **Other Devices** to **Ports,** right-click the mouse and go to **Properties**.&#x20;
9. Click the driver icon in **Properties** and verify if the driver has moved to **Ports** and is named "Cube Orange SLCAN (COMx)".&#x20;

{% hint style="info" %}
It is highly recommended to run Mission Planner on Windows 10 or later.
{% endhint %}

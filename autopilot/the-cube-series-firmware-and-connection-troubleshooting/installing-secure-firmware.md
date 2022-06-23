# Installing Secure Firmware

CAUTION: This can potentially render your hardware unusable, so do this process at your own risk.



This feature is currently only supported on Cubepilot autopilots including and released after CubeOrange. Currently this process is still in pilot mode, i.e. we don't disable the SWD on the hardware, this way if a module gets into unrecoverable state, it can be put back to original state using STLink or similar debug probes.

## Steps to put Secure Bootloader

* Ensure that you have an account at [https://discuss.cubepilot.org](https://discuss.cubepilot.org) . If not please create one, as the account will be used to secure your cube, which means, only the users with credentials will be able to load the firmware once secured.
* To load the secure bootloader, you will need Beta Mission Planner installed on your system.

![](<../../.gitbook/assets/image (3).png>)

* &#x20;Setup > Secure > Login

![](<../../.gitbook/assets/image (8).png>)

* Once logged in select Enter Bootloader Mode

![](<../../.gitbook/assets/image (6).png>)

* You should see Cube Serial Number show up on the window after repowering your Cube, once done, click Enter DFU Mode. This will put the cube in DFU bootloader, from where we can load secure bootloader.

![](<../../.gitbook/assets/image (5).png>)

* Next click Get Bootloader, this will flash the secure bootloader, and from henceforth only way to upload firmware is to sign them with your CubePilot login.

![](<../../.gitbook/assets/image (17).png>)

* Now every time you want to update firmware, you will need to do it through this page, updating through standard firmware update will not work.

![](<../../.gitbook/assets/image (4).png>)

{% hint style="info" %}
To recover back to stock bootloader, you will need to sign and upload apj downloaded from here [https://firmware.ardupilot.org](https://firmware.ardupilot.org) using the above process, repower and then connect using Mission Planner and update bootloader.
{% endhint %}


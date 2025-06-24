# Installing Secure Firmware

Securing firmware involves signing both the bootloader and firmware using the ECC Prime256v1 keypair. The keypair’s private key is securely generated and stored on CubePilot's server. Once a signed bootloader is installed, only firmware signed with an authorized public-private key pair can run on the autopilot. Any unsigned firmware will be blocked from being loaded.

{% hint style="danger" %}
Failure to follow the secure firmware installation steps could result in the hardware malfunctioning.
{% endhint %}

To install the secure bootloader, complete the following steps:

1. Ensure the ArduPilot firmware build environment is installed using Linux or Windows WSL. For details, refer to the following website: [https://ardupilot.org/dev/docs/building-the-code.html](https://ardupilot.org/dev/docs/building-the-code.html#building-the-code)
2. Ensure the latest MAVProxy has been installed. For details, refer to the following website: [https://ardupilot.org/mavproxy/docs/getting\_started/download\_and\_installation.html#mavproxy-downloadinstall](https://ardupilot.org/mavproxy/docs/getting_started/download_and_installation.html#mavproxy-downloadinstall)
3. Create a branch to develop the firmware locally.
4. Open Mission Planner.
5. Click **Setup** -> **Secure**.
6. Click **Generate Key** to create a public-private key pair.

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-11-15 095105.png" alt=""><figcaption></figcaption></figure>

7. Build a securely signed bootloader for the autopilot via the instructions in the following link: [https://github.com/ArduPilot/ardupilot/tree/master/Tools/scripts/signing](https://github.com/ArduPilot/ardupilot/tree/master/Tools/scripts/signing)

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-11-04 165831.png" alt="" width="563"><figcaption></figcaption></figure>

8. Build a securely signed firmware and load it onto the autopilot via the instructions in the following link: [https://github.com/ArduPilot/ardupilot/tree/master/Tools/scripts/signing](https://github.com/ArduPilot/ardupilot/tree/master/Tools/scripts/signing)

<figure><img src="../../../../.gitbook/assets/Screenshot 2024-11-04 165629.png" alt="" width="563"><figcaption></figcaption></figure>

9. Use MAVProxy to flash the securely signed bootloader as the new bootloader.
10. Verify that the new secure bootloader has been installed.

For more details, refer to the following link: [https://ardupilot.org/dev/docs/secure-firmware.html](https://ardupilot.org/dev/docs/secure-firmware.html)

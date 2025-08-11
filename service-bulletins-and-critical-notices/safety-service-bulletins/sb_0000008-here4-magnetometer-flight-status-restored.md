# SB\_0000008 Here4 Magnetometer (Flight Status Restored)

**For the latest updates, refer to the following link:**\
[SB\_0000008 Here4 magnetometer (Flight status Restored)](https://discuss.cubepilot.org/t/sb-0000008-here4-magnetometer-flight-status-restored/13378)

Edit 9th of July, 2024: All should please update your Here4 unit using Mission planner DroneCAN/UAVCAN panel, select download from the internet. Software Version should be 1.14.FE92DFEF or later. DO NOT UPDATE UBLOX FIRMWARE

This fixes an issue that can cause momentary loss of gps after 1 hour of use

Edit: 3rd of July: Flight status RESTORED. After much testing, it is confirmed that the failure mode is 100% predictable, and if it happens in flight, Ardupilot has no issues handling this. Testing with the here4 as a flight controller with no other assistance is underway, and we will update on the tests asap

Thanks to [@sidbh](https://discuss.cubepilot.org/u/sidbh) and Paul Riseborough for their efforts in devising the tests to verify return to flight status.

This doesn’t mean your mag will not fail, but it does mean that if it happens in flight, it by itself will not be the cause of an accident.

This has occured to less than 0.1% of units.

Edit: 15th June 2024: we have 3 confirmed customers with this situation, all returned units labelled as faulty exhibit this failure mode. Break is not visible on 3D X-ray.

Firmware update has been issued for Here4, this will ensure the module behaves correctly in this failure mode.

Flight with Dual Here4 is acceptable (or any other backup magnetometer

————————

Here4 magnetometer issue under investigation.

Reports of magnetometer losses in Here4 have been reported to Cubepilot staff by a few customers now. We are unsure as to how widespread this issue is, as such we have put a hold on sales of Here4 GPS’s as of the 20th of May 2024.

We are investigating this matter at the moment to get a root cause and will add information to this bulletin as information comes to light.

In the meantime, please verify your magnetometer fallback on your vehicle, ensure you have effective redundancy to this sensor.

In the reported cases, once the error occurs, the mag never comes back. Thus preflight checks will prevent further flight. We will obviously replace any affected units, but replacements will only happen once we have a proper solution.

We appreciate your patience on this matter and apologize for the inconvenience this brings.

Thanks\
Philip and the Cubepilot team

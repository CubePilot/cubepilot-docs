# SB\_0000002 Critical service bulletin for Cubes Purchased between JAN 2019 to JUL 2019. DO NOT FLY

**Latest update please refer to:**  
[SB\_0000002 Critical service bulletin for Cubes Purchased between January 2019 to July 2019. DO NOT FLY](https://discuss.cubepilot.org/t/sb-0000002-critical-service-bulletin-for-cubes-purchased-between-january-2019-to-july-2019-do-not-fly/406)

[Cube Blue \(made in USA\) is not affected by safety Bulletin 2  
](https://discuss.cubepilot.org/t/cube-blue-is-not-affected-by-safety-bulletin-2/631)  
\*\*Edit 3 April 2020  
This issue is fully resolved by 3.6.12 but many updates have come since. Please keep up to date as this SB only relates to the IMU matter.  
Please see Ardupilot release notes for other Ardupilot matters covered in each release

**EDIT 11th December 2019**  
Due to SB\_0000005 I’m updating this to ensure that you use 3.6.11 as a minimum  
No other changes

**Edit 28th July 2019**  
Please ensure you are using at least Arducopter 3.6.10  
SB\_0000002 Critical service bulletin for Cubes Purchased between January 2019 to present.  
**flight is possible under the following conditions** :

1.You MUST run Latest Ardupilot RELEASE **CUBE BLACK** code.

2.You must use latest Mission Planner or Latest QGC

3.Set the following parameters  
[CUBE\_BLACK.param 32](https://discuss.cubepilot.org/uploads/default/original/1X/d4ace0149f9bfbabac84c30cdff2d53ec98879de.param) \(98 Bytes\)

> BRD\_TYPE == 3   
> EK2\_IMU\_MASK == 7   
> \(or EK3\_IMU\_MASK == 7 if using EKF3\)   
> INS\_USE == 1   
> INS\_USE2 == 1   
> INS\_USE3 == 1

4.Save the parametersReboot the cube

5.reconnect mission planner

6.If Mission planner flags your code, contact your local re-seller, and log the issue. DO NOT FLY TILL I HAVE PERSONALLY CHECKED YOUR LOGS, and either given the go ahead, or, organised what we will do next in your case.

7.Further flight is only to be conducted where you have carried out a full risk assessment on the implications of a failure occurring, the new code is good… but it should not be relied upon as your only means of protection. You must not fly over people, you must not fly over critical infrastructure, you must also take responsibility for your payload and vehicle.

**Failure to comply with these requirements may lead to serious damage, injury, or death.**

**EDIT: 02nd of May 2019:**  
In addition to following the instructions on the 27th of April, ensure that the following parameters are set.

> EK2\_IMU\_MASK == 7 \(or EK3 if using EKF3\)   
> INS\_USE == 1   
> INS\_USE2 == 1   
> INS\_USE3 == 1

**EDIT: 27th of April 2019**: Ardupilot has now added detection, prearm checking, and inflight checking and failover to the redundant sensors. This is now in Release Copter and Release Plane.  
Detection of the fault has also been added to Mission Planner, and QGC latest. Mission planner now collects information on this fault if you are willing to send it to us.

As such, we are reducing this service bulletin to **flight is possible under the following conditions**:  
1. You MUST run Latest Ardupilot RELEASE **CUBE BLACK** code.  
2. You must use latest Mission Planner or Latest QGC  
3. If QGC or Mission planner flags your code, contact your local re-seller, and log the issue. DO NOT FLY TILL I HAVE PERSONALLY CHECKED YOUR LOGS, and either given the go ahead, or, organised what we will do next in your case.  
4.Further flight is only to be conducted where you have carried out a full risk assessment on the implications of a failure occurring, the new code is good… but it should not be relied upon as your only means of protection. You must not fly over people, you must not fly over critical infrastructure, you must also take responsibility for your payload and vehicle.

**Failure to comply with these requirements may lead to serious damage, injury, or death.**

Original notice:

It has come to our attention, that there is an anomaly with sensor readings on some recent cubes. This notification will be modified multiple times a day!!! Please check often.

This is an unfolding investigation, more details will be added as they come to light.

**If your vehicle is fitted with a CUBE BLACK, DO NOT FLY. Wait for further instructions.**

Your Cube is fitted with Three Gyros, Three Accelerometers, two Barometers, two internal Compasses.

to tell what is fitted…

Open mission planner and connect to your cube.  
go to the full parameter list.

Please keep an eye on this notice for further instructions. There will be an update to mission planner, and to Ardupilot coming to assist in determining if your Cube is affected by this fault.

We are sorry about this situation, and will endeavour to follow up with solutions as soon as possible  
Thank you

**NEW MISSION PLANNER BETA RELEASED TODAY! PLEASE UPDATE MISSION PLANNER TO ADD a test of AUTO DETECTION OF THIS ISSUE** . please let us know if you get the following error…

“Your board has a Critical service bulletin please see \[link;[https://discuss.cubepilot.org/t/sb-0000002-critical-service-bulletin-for-cubes-purchased-between-january-2019-to-present;Click 728](https://discuss.cubepilot.org/t/sb-0000002-critical-service-bulletin-for-cubes-purchased-between-january-2019-to-present;Click) here\]”

Failure to get the mission planner notification is NOT an indication that it is safe to fly.

All advice given will assume your device is running MASTER ARDUPILOT FOR CUBE BLACK, unless otherwise stated.

Philip Rowse




# SB\_0000003 Flight with arming checks set anything other than 1 prohibited

**Latest update please refer to:**\
[SB\_0000003 Flight with arming checks set to anything other than 1 prohibited](https://discuss.cubepilot.org/t/sb-0000003-flight-with-arming-checks-set-to-anything-other-than-1-prohibited/857)

We are seeing too many logs where arming checks are set at either 0, or at a value other than 1.

If your vehicle will not arm, you need to investigate why! do not take off until you have solved the issue that is causing the arming checks to fail.

The arming checks are there for your safety, and the safety of those around you.

the following parameters are NOT OPTIONAL on Cube Black, Green, Blue, Yellow, Orange\
\#NOTE: CUBE\_BLACK\
BRD\_TYPE,3 #sets the board type to the three IMU board\
EK2\_IMU\_MASK,7 # makes sure that 3 EKF’s run\
INS\_USE,1 #the following three parameters enable the IMUs\
INS\_USE2,1\
INS\_USE3,1\
LOG\_DISARMED,1 #ensures you can get a log that includes pre-arm information\
ARMING\_CHECK,1 #Ensures that you run all the arming checks. Your safety comes first

[CUBE\_BLACK.param](https://discuss.cubepilot.org/uploads/default/original/1X/a70e1ea4cd6ad8cf37436a06cb709a3308c8894a.param) (114 Bytes)

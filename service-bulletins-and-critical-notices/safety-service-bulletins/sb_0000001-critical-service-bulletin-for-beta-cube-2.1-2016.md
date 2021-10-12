# SB\_0000001 Critical service bulletin for Beta Cube 2.1 (2016)

**Latest update please refer to:**\
****[SB\_0000001 Critical service bulletin for Beta Cube 2.1 (2016)](https://discuss.cubepilot.org/t/sb-0000001-critical-service-bulletin-for-beta-cube-2-1-2016/405)

### If you have a Pixhawk 2.1 _**Delivered in 2016**_, please follow these instructions before further flight.

\*\*

This does NOT affect the Alpha boards, it does not affect 2.0 boards (SOLO) and does not affect made in 2017 boards

I/O channel 1 can be affected by over torquing the mounting screws holding the cube to the carrier board.\
There is no preflight check that can be done to stop the aircraft arming if this is the case.

There are two solutions to this issue.

1. As short term, software fix to keep you in the air…

Please move channel one to channel 5 by setting the following parameters.\
Firmware 3.4 set RC5\_FUNCTION=33\
Firmware 3.5 set SERVO5\_FUNCTION=33\


![](../../.gitbook/assets/sb\_0000001-photo-01.jpeg)

After you have made these changes, please leave I/O channel 1 disconnected… plug Aileron / ESC1 to I/O5

2.We will be sending all affected users a mod kit. This will involve a insulating sticker that will fit in the corner of the board.

![SB\_0000001 Photo-02 PH2 ch 1-4](../../.gitbook/assets/sb\_0000001-photo-02-ph2-ch-1-4.jpeg)

![SB\_0000001 Photo-03 PH2 short](../../.gitbook/assets/sb\_0000001-photo-03-ph2-short.jpeg)

![SB\_0000001 Photo-04 PWM CH1 Fix](../../.gitbook/assets/sb\_0000001-photo-04-pwm-ch1-fix.png)

As a third thing, I am working with Michael Oborne to make a service bulletin section in mission planner. this will identify your board, and list any known issues, and give you any information you need to maintain safe flight.\
Please keep mission planner up to date to take advantage of this service.

the modification is a user mod, and instructions will be posted for these.


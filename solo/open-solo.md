# Open Solo

## OPEN SOLO 4.0.0 has landed!

[![@Pedals2Paddles](https://avatars2.githubusercontent.com/u/8234496?s=40&v=4)](https://github.com/Pedals2Paddles) [Pedals2Paddles](https://github.com/Pedals2Paddles) released this on 1 Jan 2020

**This is the stable release of Open Solo 4.0.0, including ArduCopter 4.0.0 on December 29, 2019. This version of Open Solo and ArduCopter is now fully compatible with all Solos!** All the bugs and compatibility issues have been resolved. The slew rate limiting is working, making it safe for stock cubes. Everyone gets everything.

**NEW WIKI:** In this new consolidated repository, the instructions are now located in the github wiki. This makes it much easier to navigate and edit. Click the wiki button in the nav bar up at the top. Or if you don't want to look up, click here: [https://github.com/OpenSolo/OpenSolo/wiki](https://github.com/OpenSolo/OpenSolo/wiki)

**BRIEF FEATURE UPDATE FROM v3:** Many new things are in Open Solo 4. See the Wiki for complete details.

* ArduCopter 4 now fully compatible with all Solos. Everyone gets all features of the latest and greatest ArduCopter now and forever. ChibiOS compatibility changes are working great.
* Improved Fly Mode \(loiter mode\) is way smoother
* Installer improvements, way more robust with anti-bricking changes
* Short holding home button activates SmartRTL... safely retraces it's own 3D path home
* Battery cell health monitoring & alert \(cell voltage low, cell voltage differential, unhealthy capacity\)
* GoPro date/time set automatically
* GoPro power on/off works properly \(GoPro firmware v3 only, we can't fix v4 & v5\)
* Use ArduCopter camera shutter function if no GoPro connected for alternate cameras
* Automatic landing gear retract and deploy based on altitude
* Harmonic notch filtering improves stability and position holding by filtering out vibration
* Can be installed on a factory reset solo or NIB solo. No initial update with 3DR app needed!

**INSTALL:** Reading the install instructions in the wiki is required. The process is different from Open Solo 3, and consequently much more stable and reliable. [https://github.com/OpenSolo/OpenSolo/wiki/Install-Open-Solo](https://github.com/OpenSolo/OpenSolo/wiki/Install-Open-Solo)

* This should be hitting Solex and SidePilot for easy installation by Monday 12/30/2019.
* Files attached to this release are from this build if you wish to install manually using SSH/SFTP
* There are no SD card images at this time.

**Green Cubes:** If you have a green cube, you can install the ArduCopter version for the Green Cube after the Open Solo install is complete. The Green Cube version of ArduCopter has the Green Cube's required default parameters. You do not _need_ to do this if you don't want to. The ArduCopter version for the stock cube that comes with Open Solo will work fine on the green cube too.

_Note: The old 3DR app is barely compatible with any of this. It is not recommended, and no support is available for it. The 3DR app will not install any of this. Solex and SidePilot are the recommended and current apps._

_**Assets**_  
[3dr-controller.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4.0.0/3dr-controller.tar.gz)  
[3dr-controller.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4.0.0/3dr-controller.tar.gz.md5)  
[3dr-solo.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4.0.0/3dr-solo.tar.gz)  
[3dr-solo.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4.0.0/3dr-solo.tar.gz.md5)  
[arducopter.apj](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4.0.0/arducopter.apj)  
[artoo\_2019-12-31\_01-33.bin](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4.0.0/artoo_2019-12-31_01-33.bin)  
[Source code\(zip\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-4.0.0.zip)  
[Source code\(tar.gz\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-4.0.0.tar.gz)  


## Open Solo 4-dev 2019-09-28

[![@Pedals2Paddles](https://avatars2.githubusercontent.com/u/8234496?s=40&v=4)](https://github.com/Pedals2Paddles) [Pedals2Paddles](https://github.com/Pedals2Paddles) released this on 29 Sep 2019 · [9 commits](https://github.com/OpenSolo/OpenSolo/compare/OpenSolo-4dev2...master) to master since this release

**\(Updated 2019-09-28** to fix the controller's Artoo STM32 firmware and added the Open Solo 4 boot graphic to the controller. Otherwise, no functional changes from previous dev release.\)

**Assets**  
[3dr-controller.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev2/3dr-controller.tar.gz)  
[3dr-controller.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev2/3dr-controller.tar.gz.md5)  
[3dr-solo.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev2/3dr-solo.tar.gz)  
[3dr-solo.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev2/3dr-solo.tar.gz.md5)  
[arducopter.apj](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev2/arducopter.apj)  
[artoo\_2019-09-29\_01-59.bin](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev2/artoo_2019-09-29_01-59.bin)  
[Source code\(zip\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-4dev2.zip)  
[Source code\(tar.gz\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-4dev2.tar.gz)

## Open Solo 4-Dev

[![@Pedals2Paddles](https://avatars2.githubusercontent.com/u/8234496?s=40&v=4)](https://github.com/Pedals2Paddles) [Pedals2Paddles](https://github.com/Pedals2Paddles) released this on 23 Sep 2019 · [9 commits](https://github.com/OpenSolo/OpenSolo/compare/OpenSolo-4dev...master) to master since this release

**First pre-release of Open Solo 4, including ArduCopter 4-dev \(master\) as of Sept 22, 2019 that is now fully compatible with all Solos!** All the bugs and compatibility issues have been resolved. The slew rate limiting is working, making it safe for stock cubes. Everyone gets everything. A more complete list of features coming soon.

**NEW WIKI:** In this new consolidated repository, the instructions are now located in the github wiki. This makes it much easier to navigate and edit. Click the wiki button in the nav bar up at the top. Or if you don't want to look up, click here: [https://github.com/OpenSolo/OpenSolo/wiki](https://github.com/OpenSolo/OpenSolo/wiki)

**BRIEF FEATURE UPDATE FROM v3:** Many new things are in Open Solo 4. See the Wiki for complete details.

* ArduCopter 4-dev \(master\) now fully compatible with all Solos. Everyone gets all features of the latest and greatest ArduCopter features now and forever. ChibiOS compatibility changes are working great.
* Installer improvements, way more robust with anti-bricking changes
* Short holding home button activates SmartRTL... safely retraces it's own 3D path home
* Battery cell health monitoring & alert \(cell voltage low, cell voltage differential, unhealthy capacity\)
* GoPro date/time set automatically
* GoPro power on/off works properly \(GoPro firmware v3 only, we can't fix v4 & v5\)
* Use ArduCopter camera shutter function if no GoPro connected for alternate cameras

**INSTALL:** Reading the install instructions in the wiki is required. The process is different from Open Solo 3, and consequently much more stable and reliable. [https://github.com/OpenSolo/OpenSolo/wiki/Install-Open-Solo](https://github.com/OpenSolo/OpenSolo/wiki/Install-Open-Solo)

* This should be hitting Solex and SidePilot for easy installation by Monday evening 9/23/2019.
* Files attached to this release are from this build if you wish to install manually using SSH/SFTP
* There are no SD card images at this time.

_Note: The old 3DR app is barely compatible with any of this. It is not recommended, and no support is available for it. The 3DR app will not install any of this. Solex and SidePilot are the recommended and current apps._

**Assets**  
[3dr-controller.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev/3dr-controller.tar.gz)  
[3dr-controller.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev/3dr-controller.tar.gz.md5)  
[3dr-solo.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev/3dr-solo.tar.gz)  
[3dr-solo.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev/3dr-solo.tar.gz.md5)  
[arducopter\_2019-09-22.apj](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev/arducopter_2019-09-22.apj)  
[artoo\_2019-09-22.bin](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-4dev/artoo_2019-09-22.bin)  
[Source code\(zip\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-4dev.zip)  
[Source code\(tar.gz\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-4dev.tar.gz)

## Open Solo 3.0.0 - January 1, 2018

[![@Pedals2Paddles](https://avatars2.githubusercontent.com/u/8234496?s=40&v=4)](https://github.com/Pedals2Paddles) [Pedals2Paddles](https://github.com/Pedals2Paddles) released this on 5 May 2019 · [235 commits](https://github.com/OpenSolo/OpenSolo/compare/OpenSolo-3.0.0...master) to master since this release

## OPEN SOLO 3.0.0

This is the first stable production release \(non-beta\) of Open Solo! Since 3DR open sourced the Solo and controller, many new possibilities have opened up. Combined with the continued development of ArduPilot, the Solex App, and SidePilot App, the solo is now growing even more!

### Stock Solos vs Green Cube Solos

This is fully compatible with both totally stock Solos and green cube solos! You do not need to pick and choose, and we don't need multiple release versions for the different hardware. The code will auto-detect which cube you have, and use that information to auto install the correct version of ArduCopter on it.

#### STOCK SOLO SPECIFIC UPDATES: The following applies only to stock solo Pixhawk cubes and does not apply to Green Cube solos.

* **ArduCopter Solo 1.5.4** upgrading you from the 3DR stock 1.3.1 version from about 2yrs ago.
  * **Distance based battery failsafe:** Triggers RTH to be on the ground at approx 10% remaining. If you want to adjust this yourself, you can manually tweak parameter `FS_BATT_CUR_RTL`. A value of 22 gets you on the ground with about 10% remaining. A higher value will RTH sooner leaving a higher % remaining.
  * **Improved landing detection:** This greatly improves the solo's ability to detect it has landed. In the past, it could get confused by a rough, fast, or jerky landing. This results in it refusing to disarm or and sometimes flipping over. The new landing detection algorithm is greatly enhanced. You will notice it now takes and extra second or so to disarm once you're on the ground. And you may see a little twitch in the throttle. It is literally testing the ground. It works quite nicely.
  * **Low battery thrust priority:** If the battery is getting dangerously low, it will allow itself to sacrifice yaw \(rotation\) control to increase thrust to prevent a crash. This could give you the thrust you need to land softly rather than dropping out of the sky.
  * **Smart shot altitude priority:** Will not lose altitude by going too fast in Follow Mode! In Smart Shots, the solo will not allow itself to go "too fast" causing a loss of altitude.
  * **No more 3DR:** This version was compiled by the Open Solo team in the Open Solo repositories. It cuts the cord from 3DR's firmware server for Pixhawk firmware.
  * **Corrected parameters:** 3DR's last release was 1.5.3 and only for commercial site scan solos. The Open Solo version 1.5.4 has corrected parameters that account for the consumer solo being much lighter weight.

#### GREEN CUBE SPECIFIC UPDATES: The following applies to Green Cube equipped solos and does not apply to stock Solos.

* **The most recent stable production release of ArduCopter, which today is ArduCopter 3.5.4**
  * Boat mode! You can arm and take off from moving vehicles/vessels
  * Improved landing detection: This greatly improves the solo's ability to detect it has landed. In the past, it could get confused by a rough, fast, or jerky landing. This results in it refusing to disarm or and sometimes flipping over. The new landing detection algorithm is greatly enhanced. You will notice it now takes and extra second or so to disarm once you're on the ground. And you may see a little twitch in the throttle. It is literally testing the ground. It works quite nicely.
  * 3 improved IMUs in the green cube, 2 of which are vibration isolated and heated.
  * Ability to use RTK GPS for surveys, ADS-B aircraft avoidance, lidar laser altimeters, terrain awareness and following, IR precision landing, and even an “indoor GPS”.
  * Hundreds of enhancements since 2015, and continued development by the ArduPilot team.
  * Solo's required default parameters baked in. No parameter file loading needed!
* **NOTE:** If you are also doing a new Green Cube install, make sure you install Open Solo _before_ you install the green cube!!! It needs to be fully installed and functional on the solo with the stock cube before you install the green cube. See the new green cube install instructions link at the bottom of the release notes.

### AWESOMENESS FOR ALL

* **Single install package:** Added detection of which Cube you have installed in your solo. This will be used to install the proper version of ArduCopter. This is why there isn't a green cube vs stock version. One does it all.
* **Cut the cord from 3DR! Factory reset update:** This updates the factory reset \(recovery partition\) to no longer require 3DR servers or an internet update. If you factory reset, it will come back up with a clean installation of Open Solo that is fully operational! No internet needed. No update needed. Calibrate and fly.
* **Controller: short and long hold button functions:** Added short hold \(2-seconds\) and long hold \(3 seconds\) events to the A, B, Pause, camera preset, and camera trigger buttons. This allows you to assign and use functions based on short and long holding the buttons. The assignments can be edited in `/usr/bin/extSettings.conf`. The defaults are as follows:
  * A single press: Manual
  * A short hold: Stabilize
  * A long hold: Auto mode
  * B single press: Position Hold
  * B short hold: Drift
  * B long hold: Sport
  * Camera Preset top long hold: None
  * Camera Preset bottom long hold: None
  * Camera trigger long hold: Gimbal lock \("FPV race mode"\)
* **Controller: CH7 on/off improvement:** Long hold pause button to turn CH7 option on. Short hold pause to turn CH7 option off. This removes the conflict with the pause function, which still uses the normal single click. If you use landing gear, you should keep using this for now.
* **Controller display and haptic:** Updated numerous displayed messages and haptic feedback to be more useful and helpful to the user.
* **Safety & Mode Reliability:** Removed numerous unnecessary layers from communication between the controller and ArduCopter. The fly, home, and pause button functions now communicate directly to the Cube and ArduCopter rather than going through layers of handling in the smart shot manager. Also made mode changes better handle a smart shot that didn't properly close.
* **Smart shot cleanups and compatibility fixes**:
  * All the compatibility fixes needed for the green cube.
  * Standardized horizontal acceleration to 2/m/s/s across all shots for consistency and smoothing.
  * Entering shot reduces copter pitch/roll acceleration for smoothing and consistency, especially with green cube solos that have more power.
* Added compatibility with Solex geotagging functions
* Home button and RTH failsafe now use ArduCopter RTL Mode instead of the old "Return Home" smart shot. This is more reliable and eliminates numerous points of failure. They have the same end result.
* Newer version of some system files to make troubleshooting and recovery from problems easier.
* Factory reset will now reset the ArduCopter parameters on the pixhawk to default as well. This was always a troubleshooting problem, and eliminates unnecessary extra steps.
* _**Lost functionality:**_ Unfortunately, two things had to get sacrificed in this due to compatibility and incomplete development from 3DR. The impact should be rather minimal.
  * **Rewind** has been removed. The 3DR Solo app still has the option to turn it on/off, which also never worked right, and they will not do anything. This was a feature 3DR was in the middle of developing when they closed shop. It is not compatible with ArduCopter RTL mode. It is something that may be revised in the future as something that isn't connected to any failsafe and is executed with a button push. But not right now. -**Hover instead of landing in return to home or return to me** has been removed. This was intertwined with the rewind code and the old return home smart shot. It is not compatible with ArduCopter RTL mode. And it also was incomplete and not really safe to use anyway. This again is something I'd like to revisit in the future, since it has some use cases \(like boating\). But for now, it's only returns home \(or return to me\) and lands when it gets there.
  * **Alternative for now:** If you need the hover option, you can manually increase ArducCopter parameter `RTL_LOIT_TIME`. It is in milliseconds. It is the amount of time the copter will hover prior landing. If simply turn it up to several minutes or whatever suites you needs, you will have the same effect.

### Tech and Contributors

If you're the geeky type that wants to read all the commits to see what has been changed in Open Solo, they can all be found in the Open Solo github repositories.

* **The Build System** compiles all the code from all the repositories into functioning binaries to be loaded onto the Solo and Controller. This was a HUGE lift to make work outside of 3DR's environment. David Buzz \([@davidbuzz](https://github.com/davidbuzz)\) was the brains behind the move of _everything_ from 3DR, setup of new repos and servers, build system engineering, and a new AWS based auto-build system. The AWS system can compile from scratch in 1hr, whereas a home PC takes up to 5hrs.
  * [Meta-3DR](https://github.com/OpenSolo/meta-3dr/commits/master) is all the Yocto bitbake recipes.
  * [Solo-Builder](https://github.com/OpenSolo/solo-builder/commits/master) is the virtual machine and scripts to carry out the build.
* **The Flight Code** has numerous components that got fixes and new features. Matt Lawrence \([@Pedals2Paddles](https://github.com/Pedals2Paddles)\) worked most of these changes. Other contributors to the code were Tim \([@FLYBYME](https://github.com/FLYBYME)\), Morten Enholm \([@Spawn32](https://github.com/Spawn32)\), and Hugh Eaves \([@hugheaves](https://github.com/hugheaves)\),
  * [Sololink](https://github.com/OpenSolo/sololink/commits/master) is mostly behind the scenes stuff related to booting, networking connections, firmware loading, etc. This compiles into a version for both the Copter and Controller's IMX companion computers.
  * [Shotmanager](https://github.com/OpenSolo/shotmanager/commits/master) is all the smart shots, button and control handling, camera stuff, and most other user facing operational stuff. This compiles primarily into the Copter's IMX companion computer.
  * [Artoo](https://github.com/OpenSolo/artoo/commits/master) is the controller's STM32 firmware for the screen, buttons, and sticks.
  * [Mavlink-Solo](https://github.com/OpenSolo/mavlink-solo/commits/master) is a rather old fork of Mavlink. The flight modes were brought up to current enumerations.
  * [Sololink-python](https://github.com/OpenSolo/sololink-python/commits/master) is some misc helper python files.
  * [ArduPilot-solo](https://github.com/OpenSolo/ardupilot-solo/commits/master) is 3DR's fork of ArduCopter used on the stock Solo pixhawk 2.0 cube.

### Installation Instructions

The process for installing Open Solo is quite straightforward. The general steps are

1. Load install packages to copter and controller
2. Reboot copter and controller
3. Pair
4. Calibrate.
5. Fly.

#### Detailed Open Solo 3.0.0 instructions for each installation method can be found here:

[https://github.com/OpenSolo/documentation](https://github.com/OpenSolo/documentation)

**Assets**  
[3dr-controller.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-3.0.0/3dr-controller.tar.gz)  
[3dr-controller.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-3.0.0/3dr-controller.tar.gz.md5)  
[3dr-solo.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-3.0.0/3dr-solo.tar.gz)  
[3dr-solo.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-3.0.0/3dr-solo.tar.gz.md5)  
[arducopter\_1.5.4-solo.px4](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-3.0.0/arducopter_1.5.4-solo.px4)  
[arducopter\_3.5.4-solo.px4](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-3.0.0/arducopter_3.5.4-solo.px4)  
[artoo\_STM32-3.0.0.bin](https://github.com/OpenSolo/OpenSolo/releases/download/OpenSolo-3.0.0/artoo_STM32-3.0.0.bin)  
[Source code\(zip\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-3.0.0.zip)  
[Source code\(tar.gz\)](https://github.com/OpenSolo/OpenSolo/archive/OpenSolo-3.0.0.tar.gz)

## 3DR Final Release 2.4.2

[![@Pedals2Paddles](https://avatars2.githubusercontent.com/u/8234496?s=40&v=4)](https://github.com/Pedals2Paddles) [Pedals2Paddles](https://github.com/Pedals2Paddles) released this on 5 May 2019 · [268 commits](https://github.com/OpenSolo/OpenSolo/compare/3DR-2.4.2...master) to master since this release

3DR's final release version 2.4.2. The commits are not likely going to compile since they are as delivered from 3DR and not in a functional state. The attached firmware binaries are working as downloaded from the 3DR server.

**Warning:** _The ArduCopter-v2 firmware for the stock solo cube is not compatible with newer hardware \(Black and Green Cubes for example\). If you try to install this ArduCopter firmware on a newer cube, it will brick. This ArduCopter FW is only compatible with the old stock Solo cube._

**Assets**  
[ArduCopter-v2\_Solo1.3.1.px4](https://github.com/OpenSolo/OpenSolo/releases/download/3DR-2.4.2/ArduCopter-v2_Solo1.3.1.px4)  
[artoo\_stm32\_1.2.11.bin](https://github.com/OpenSolo/OpenSolo/releases/download/3DR-2.4.2/artoo_stm32_1.2.11.bin)  
[controller\_2.4.2.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/3DR-2.4.2/controller_2.4.2.tar.gz)  
[controller\_2.4.2.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/3DR-2.4.2/controller_2.4.2.tar.gz.md5)  
[solo\_2.4.2.tar.gz](https://github.com/OpenSolo/OpenSolo/releases/download/3DR-2.4.2/solo_2.4.2.tar.gz)  
[solo\_2.4.2.tar.gz.md5](https://github.com/OpenSolo/OpenSolo/releases/download/3DR-2.4.2/solo_2.4.2.tar.gz.md5)  
[Source code\(zip\)](https://github.com/OpenSolo/OpenSolo/archive/3DR-2.4.2.zip)  
[Source code\(tar.gz\)](https://github.com/OpenSolo/OpenSolo/archive/3DR-2.4.2.tar.gz)  



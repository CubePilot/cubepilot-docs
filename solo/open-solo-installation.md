# Open Solo Installation

## Announcements

**Open Solo 4.0.0 Soft Launch 12/29/2019:** Open Solo 4.0.0, built from this new consolidated repository, including ArduCopter 4.0.0, is available for installation in Solex, SidePilot, and SSH/SFTP. Please for the love of god, actually read the installation instructions. The install procedure is different from Open Solo 3 \(for the better\). Go to the [Install Open Solo](https://github.com/OpenSolo/OpenSolo/wiki/Install-Open-Solo) page to begin. I have not updated the SidePilot instructions yet. But if you're already familiar with SidePilot installs, the process is basically the same as the Solex instructions. SSH/SFTP instructions are updated as well for those who love their keyboards.

**Version Numbers Notes - ArduCopter 4.0 & Open Solo 4.0:** The fact that both are version 4 is completely coincidence, so don't read into that too much\*.

**Consolidated github repo and wiki are here:** \(Nerd notes. Most general users probably don't know or care what any of this means\) Many of the separate github repositories for the various aspects of Open Solo have been consolidated into one central repo, which is where you are now. Anything that wasn't a fork of another repo has been converted to a sub-directory of this repo. This includes sololink, shotmanager, solo-builder, artoo, sololink-python, stm32loader, meta-3dr, and yocto base. Conveniently, these are the repos that see the most ongoing development. As such, it will be much easier to manage that work in one place. Releases, tags, and branches will have some logic and consistency. The commit history from the old separate repos has been retained and all show up here still, so history is not lost or forgotten.

Mavproxy and mavlink-solo remain separate repos, included here as submodules. These are forks from ArduPilot, and shall remain in their repos for that reason. Ultimately, it would be great to just use the master ArduPilot repos, but the Solo's firmware is too old. So these forks are circa 2016. The imx6-linux and imx6-uboot are also still in their own repos. They are forks, and have tens of thousands of commits each. They also are untouched since 2016, and will probably remain so.

ArduPilot-solo is the repo for the old stock ArduCopter firmware from 3DR. It is a fork from ArduPilot, stale since 2016 other than one commit for Open Solo 3. This will as such be remaining its own repo, included here as a submodule for reference. ArduCopter 4.0 has made this old version obsolete and it is no longer used in Open Solo 4.0.

## INSTALL OPEN SOLO 4!

The team working on safe, reliable releases of Open Solo publishes them here. You can read all the details in the release notes, and link directly to installation instructions. These are the "official" instructions. These instructions supersede any other older instructions, videos, and wikis that came before Open Solo.

**Go to the** [**Install Open Solo**](https://github.com/OpenSolo/OpenSolo/wiki/Install-Open-Solo) **page to begin.**

## FEATURES & CHANGES

### **Open Solo 4 Changes from Open Solo 3**

* ArduCopter 4-dev compatible with all Solos. No green cube required!
* Home button short hold: New smart RTL mode!
* Unhealthy battery warnings: Monitors cell voltage differences to warn if one cell is getting lower than the others too fast. Also monitors battery's reported full charge capacity to warn the user if it is unhealthy \(below 3500mah\).
* GoPro clock set! Will automatically update the GoPro's clock to match the GPS set system clock. The GoPro clock setting requires editing /usr/bin/extSettings.conf. Change the timeOffsetHrs=none to whatever your offset is. For example, eastern time in the USA would be timeOffsetHrs=-5.
* Camera shutter trigger in ArduCopter if no GoPro is connected
* Can install on a NIB solo or from a factory reset state without requiring the initial 3DR update first
* Less annoying haptic \(vibration\) on the controller when compass is not calibrated yet
* Improved Fly Mode \(loiter mode\) is way smoother
* More installation improvements to prevent bricking
* Compatibility with ArduCopter's new ChibiOS RTOS and APJ file extensions
* Harmonic notch filtering to improve position hold stability by filtering out vibration
* Automatic landing gear retract and deploy based on altitude
* All improvements, new flight modes, and bugfixes through ArduCopter 3.5, 3.6, and 4.0.

### **Highlights from Open Solo 3**

All features from Open Solo 3 are still there. Listing some highlights here for new users.

* No more 3DR: This version was compiled by the Open Solo team in the Open Solo repositories. It cuts the cord from 3DR's firmware server completely. Can install without requiring the initial 3DR update first, and can install even from a factory reset state.
* Factory reset update: This updates the factory reset \(recovery partition\) to no longer require 3DR servers or an internet update. If you factory reset, it will come back up with a clean installation of Open Solo that is fully operational! No internet needed. No update needed. Calibrate and fly.
* Solo's required default parameters baked in. No parameter file loading needed!
* Botched installation protection helps prevent bricking.
* Improved landing detection: This greatly improves the solo's ability to detect it has landed. In the past, it could get confused by a rough, fast, or jerky landing. This results in it refusing to disarm or and sometimes flipping over. The new landing detection algorithm is greatly enhanced. You will notice it now takes and extra second or so to disarm once you're on the ground. And you may see a little twitch in the throttle. It is literally testing the ground. It works quite nicely.
* Low battery thrust priority: If the battery is getting dangerously low, it will allow itself to sacrifice yaw \(rotation\) control to increase thrust to prevent a crash. This could give you the thrust you need to land softly rather than dropping out of the sky.
* Smart shot altitude priority: Will not lose altitude by going too fast in Follow Mode! In Smart Shots, the solo will not allow itself to go "too fast" causing a loss of altitude.
* Boat mode! You can arm and take off from moving vehicles/vessels.
* Ability to use RTK GPS for surveys, ADS-B aircraft avoidance, lidar laser altimeters, terrain awareness and following, IR precision landing, and even an “indoor GPS”.
* Hundreds of enhancements since 2015, and continued development by the ArduPilot team.
* Controller: short and long hold button functions: Added short hold \(2-seconds\) and long hold \(3 seconds\) events to the A, B, Pause, camera preset, and camera trigger buttons. This allows you to assign and use functions based on short and long holding the buttons. The assignments can be edited in /usr/bin/extSettings.conf. The defaults are as follows:
  * A single press: Manual
  * A short hold: Stabilize
  * A long hold: Auto mode
  * B single press: Position Hold
  * B short hold: Drift
  * B long hold: Sport
  * Camera Preset top long hold: None
  * Camera Preset bottom long hold: None
  * Camera trigger long hold: Gimbal lock \("FPV race mode"\)
* Controller: CH7 on/off improvement: Long hold pause button to turn CH7 option on. Short hold pause to turn CH7 option off. This removes the conflict with the pause function, which still uses the normal single click. If you use landing gear, you should keep using this for now.
* Controller display and haptic: Updated numerous displayed messages and haptic feedback to be more useful and helpful to the user.
* Safety & Mode Reliability: Removed numerous unnecessary layers from communication between the controller and ArduCopter. The fly, home, and pause button functions now communicate directly to the Cube and ArduCopter rather than going through layers of handling in the smart shot manager. Also made mode changes better handle a smart shot that didn't properly close.
* Smart shot cleanups and compatibility fixes:
  * All the compatibility fixes needed for the green cube.
  * Standardized horizontal acceleration to 2/m/s/s across all shots for consistency and smoothing.
  * Entering shot reduces copter pitch/roll acceleration for smoothing and consistency, especially with green cube solos that have more power.
  * Added compatibility with Solex geotagging functions
  * Home button and RTH failsafe now use ArduCopter RTL Mode instead of the old "Return Home" smart shot. This is more reliable and eliminates numerous points of failure. They have the same end result.
* Newer version of some system files to make troubleshooting and recovery from problems easier.
* Factory reset will now reset the ArduCopter parameters on The Cube \(formerly known as Pixhawk\) to default as well. This was always a troubleshooting problem, and eliminates unnecessary extra steps.
* Lost functionality: Unfortunately, two things had to get sacrificed in this due to compatibility and incomplete development from 3DR. The impact should be rather minimal.
  * Rewind has been removed. The 3DR Solo app still has the option to turn it on/off, which also never worked right, and they will not do anything. This was a feature 3DR was in the middle of developing when they closed shop. It is not compatible with ArduCopter RTL mode. It is something that may be revised in the future as something that isn't connected to any failsafe and is executed with a button push. But not right now.
  * Hover instead of landing in return to home or return to me has been removed. This was intertwined with the rewind code and the old return home smart shot. It is not compatible with ArduCopter RTL mode. And it also was incomplete and not really safe to use anyway. This again is something I'd like to revisit in the future, since it has some use cases \(like boating\). But for now, it's only returns home \(or return to me\) and lands when it gets there. Alternative for now: If you need the hover option, you can manually increase ArducCopter parameter RTL\_LOIT\_TIME. It is in milliseconds. It is the amount of time the copter will hover prior landing. If simply turn it up to several minutes or whatever suites you needs, you will have the same effect.

## SUPPORT, SOCIAL MEDIA, & LINKS

* [Solo Beta Test](https://www.facebook.com/groups/617648671719759) group on Facebook \(primary Open Solo and Green Cube support group!!\)
* [Solo Mod Club](https://www.facebook.com/groups/3DRSOLOModClub) group on Facebook
* [Solex Users](https://www.facebook.com/groups/176789056089526) group on Facebook
* [Solex App](http://www.solexapp.com/) official website. This app is truely the future of Solo's user interface!
* [SidePilot Community](https://www.facebook.com/sidepilotapp) group on Facebook
* [Jester's Drones](http://jestersdrones.org/store/l) for the Green Cube and other cool gear
* [ArduPilot](http://ardupilot.org/) homepage
* [ArduCopter Full Parameter List](http://ardupilot.org/copter/docs/parameters.html) details all 800 something parameters in ArduCopter.
* [ArduCopter introduction](http://ardupilot.org/copter/docs/introduction.html): Learn what you're getting yourself into :\)
* [Mission Planner](http://ardupilot.org/planner/docs/common-install-mission-planner.html) ground station app for Windows
* [Filezilla](https://filezilla-project.org/download.php?type=client) for moving files to/from the companion computer
* [WinSCP](https://winscp.net/eng/download.php) for moving files to/from the companion computer

## Tech and Contributors

If you're the geeky type that wants to read all the commits to see what has been changed in Open Solo, they can all be found in the Open Solo github repositories.

* **The Build System** compiles all the code from all the repositories into functioning binaries to be loaded onto the Solo and Controller. This was a HUGE lift to make work outside of 3DR's environment. David Buzz \(@davidbuzz\) was the brains behind the move of everything from 3DR, setup of new repos and servers, build system engineering, and a new AWS based auto-build system. The AWS system can compile from scratch in 1hr, whereas a home PC takes up to 5hrs.
* **The Flight Code** has numerous components that got fixes and new features. Matt Lawrence \(@Pedals2Paddles\) worked most of these changes. Other contributors to the code were Tim \(@FLYBYME\), Morten Enholm \(@Spawn32\), and Hugh Eaves \(@hugheaves\),
  * **Sololink** is mostly behind the scenes stuff related to booting, networking connections, firmware loading, etc. This compiles into a version for both the Copter and Controller's IMX companion computers.
  * **Shotmanager** is all the smart shots, button and control handling, camera stuff, and most other user facing operational stuff. This compiles primarily into the Copter's IMX companion computer.
  * **Artoo** is the controller's STM32 firmware for the screen, buttons, and sticks.
  * **Mavlink-solo** is a rather old fork of Mavlink. The flight modes were brought up to current enumerations.
  * **Sololink-python** is some misc helper python files.
  * **ArduPilot-solo** is 3DR's fork of ArduCopter used on the stock Solo The Cube \(formerly known as Pixhawk\).

## For Developers

**Not for general users that just want to put Open Solo releases on their solo!!!**

* Visit the [Vagrant VM](https://github.com/OpenSolo/OpenSolo/wiki/Vagrant-VM) page for first time installation and initialization of the Vagrant VM.
* Visit [Solo Builder](https://github.com/OpenSolo/OpenSolo/wiki/Solo-Builder) for steps to build the complete copter and controller firmware.
* Visit [Artoo STM32](https://github.com/OpenSolo/OpenSolo/wiki/Artoo-STM32) for steps to build just the Artoo STM32 firmware

## How to get involved

This documentation is pretty empty right now. If you know how Solo or Artoo works \(or don't know!\) and want to get involved pull requests are welcome on this documentation and all of the sub projects. Most of the developers are hanging out on [gitter](https://gitter.im/ArduPilot/OpenSolo) and the social media groups listed above.

## Special Mentions!

All of this would not be possible without 3DR. They very generously open sourced most of their internal code and build tools to make this possible. You can see the official [3DR release statement here](https://3dr.com/blog/announcing-opensolo) and the [ArduPilot Team's statement here](https://discuss.ardupilot.org/t/opensolo-initiative-by-the-ardupilot-team). Special thanks to Buzz and Peter for making this happen, and everyone else who has contributed to make solo even better.

\*\*\*\*


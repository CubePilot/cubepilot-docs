# Airbot Mini Carrier Board Set User Guide

![](../../.gitbook/assets/airbot-mcb-diagram.png)

## Airbot Mini Carrier Board Set User Guide v1.1

### GENERAL

The Airbot Mini carrier board is one of the way to install a Cube on a drone. The Mini carrier board encapsulate all the wiring in a 50.5x57.5mm board, in order to save space and weight for applications which have size limits.

### DIMENSIONS

![](../../.gitbook/assets/airbot-mcb-dimension.jpg)

### FEATURES

●  Dual power inputs \(redundant power with automatic switch to the second power source when first one fails\)  
●  Easy to install on drone \(see the mounting pattern above\)  
●  Power distribution & voltage protection \(providing current to each connector\)  
●  Motor PWM signal distribution \(up to 8 motors - distributed on corners\)  
●  Standard 2.54mm servo PPM/S.BUS/Spectrum RC input \(+5v/+3.3v selectable power from carrier board\)  
●  AUX VCC pins are connected together. This allows powering the AUX rail externally.

### INTERFACES

| PORT | CONNECTOR ON BOARD | CONNECTOR TO PLUG IN |
| :--- | :--- | :--- |
| I2C\_2 - CAN1 - CAN2 | JST GH : BM04B-GHS-TBT | GHR-04V-S |
| USB - TELEM1 - TELEM2 - GPS2 | JST GH : BM06B-GHS-TBT | GHR-06V-S |
| GPS1 | JST GH : BM08B-GHS-TBT | GHR-08V-S |
| POWER1 - POWER2 | Molex CLIKMATE : 502443-0670 | 502439-0600 |

\*All connectors are the same as Cube Standard carrier board

### PINOUT

![](../../.gitbook/assets/airbot-mcb-detail-diagram.jpg)

### RC SIGNAL AND POWER SELECTION

![](../../.gitbook/assets/airbot-mcb-bottom.jpg)

### POWER DISTRIBUTION BOARD \(optional\)

The Airbot Power Distribution Board Set can be installed directly under Airbot Mini carrier board set. The PDB allows up to 180A through ESC interface and four pairs of low power pads \(2 on top/ 2 on bottom\). The mounting hole are aligned with Airbot carrier board, so the board can be stacked together while separated by small nylon spacers.

![](../../.gitbook/assets/airbot-mcb-pdb.jpg)

ATTENTION ! : The PDB can not be attached to any conductive materials. Beware to distance from any conductive material by

When using nylon spacers or insulations\(e.g PlastiDIP\), remember to leave enough spacing distance away from conductors.

### INSTALLATION DIAGRAM

![](../../.gitbook/assets/airbot-mcb-set-with-cube-orange-side.jpg)

August 16，2021

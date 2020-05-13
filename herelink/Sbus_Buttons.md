---
description: >-
  Herelink is fitted with six programmable buttons and one hardware wheel.  These can be configured to control SBUS channel outputs  from the air end’s dual sbus connector and to send Mavlink commands to the autopilot via Solex TX or QGC.
---

# Sbus Button Configuration

## Autopilot Mode Selection Important

{% hint style="info" %}
Autopilot mode selection must not be programmed to SBUS channels. Mode selection should be configured Mavlink commands within Solet TX or QGC, More info . [Mode Selection & Mavlink Buttons](configure-mavlinkbuttons.md)
{% endhint %}

## Sbus Outputs

The Herelink settings app allows you to program buttons A,B,C,D,Cam & HW Wheel to control  sbus outputs on the air unit. 

Herelink has dual sbus channels and buttons can be configured to channels 5 - 16 on bus 1 and 1-16 on bus 2. 

Each button can be programmed in 3 modes with long press and short press actions depending on mode.  

**Modes:**

* Toggle  = Output latchet between two pwm values with a short or long press option. 
* Momenty = Output changes to value when pressed and held, returns when released. 
* Multi = Send command for channel to go to set pwm value. Multi buttons can be stacked on both short and long press as well as multiple * buttons to allow channel output to range in values.  

To select the mode either press T for Toggle, M for Momantry, when none is selected the button is in Multi mode. 

## Profiles 

Herelink Sbus Buttons allows you to save multiple button profiles. This means you can set up Herelink to have multiple configurations for different applications.   

## Home Button 

The home button can only be configured with mavlink commands in Solex TX or QGC.  It is advised to set Homebutton Long Press to ‘RTL’ command as user safety backup. 


## Sbus Button Configuration

### Buttons Screen Overview

![](../.gitbook/assets/Buttons_screenoverview.jpg)


### To Configure 

From App Launcher slide down the notification drawer from the top and select Herelink Setting


Slide left for Buttons screen.

Here you will find the button configuration options for sbus. 


Click NEW and type name for your controles profile and press OK.

Select the first button you want to configure from the drop down menu then click ADD

Select Desired mode ie Toggle, Momenty or leave blank for Multi 

Note when setting up Multi mode buttons at least one must be selected as default, this sets the default output position on system boot. 



For Toggle & Momentary set default pwm and active pwm values. 


For Multi set desired pwm output on press 

Set sbus channel output and Bus output. 

Once configured you must click SAVE to store settings. 


Next contine to add more buttons via the above process. 

Multi buttons allows you to set Short and Long press as well as other buttons to set stages outputs on a sbus channel below is an example of two buttons changing a channel to 4 different pwm values.  


---
description: >-
  Overview of the ADS-B IN carrier board thats shipped with the Cube Orange
  Standard Kit
---

# ADS-B IN Carrier Board

The Cube Orange standard kit consists of the new Cube Orange as well as the new ADS-B equipt carrier board. 

![](../.gitbook/assets/700x467xorange-cube-standard-adsb-03.jpg.pagespeed.ic.b76kbv8lhc.jpg)

This is an updated version of the original carrier board, its overall footprint is identical to the previous versions, main changes compated to original carrier are as follows 

* Intergration of uAvonix ADS-B IN Receiver
* Built-In ADS-B Antenna 
* Revmoval of Intel Edison Bay and Debug USB Ports
* New Product Livery 
* Correct lableing Of CAN Ports 

All external connections and ports remmain identical to the orignal carrer apart from the following 

xxxxxxx



### uAvionix ADS-B Receiver   



The new carrier board has an intigrated 1090Mhz ADS-B IN receiver from uAvionix, this allows users to detect ADS-B OUT equip aircraft in the area and displays information sush as the Position, Altitude, Speed and ID of the detected aircraft on a connected ground station. This also allow sense and avoid features included in Ardupilot to be used if configured. 



This ADS-B receiver is conneted to the internal Serieal XXX Port,  this is compaible with Ardupilot, Mission Planner and QGC.This system will 

To enable ADSB in Ardupilot you need to be using Copter or Plane 4.0 onward for the Cube Orange and set the following paramiters 





 




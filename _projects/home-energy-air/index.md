---
layout: post
title: Home Energy Monitoring & Air Quality
description: I like to use open-source software and inexpensive electronics to measure and do things around the house, from making sure the air is clean and safe to understanding what is contributing to the electric bill.
card_image: /assets/energyrecoveryvfinishedbutnotinstalled.jpg
order: 8
skills:
  - ESPHome
  - AC Power Monitoring
  - Air Quality Sensing (PM2.5 / VOC / CO2)
  - Home Assistant Automation
  - Energy Cost Optimization
  - ERV & Ventilation Design
  - CAD Enclosure Design
---

## Description

I like to use open-source software and inexpensive electronics to measure and do things around the house, from making sure the air is clean and safe to understanding what is contributing to the electric bill.

## Energy Recovery Ventilator 

  During COVID Summer, I spent a lot of time in my room. The door closed, and the A/C was not turning on that often; I would often get bad headaches and brain fog that would go away if I went downstairs to the living room or kitchen. A few years later, CO2 tracking came across my radar. I bought an Aranet 4 Wireless E-Ink CO2 monitor and found out that my room regularly gets 'in the yellow' or 'in the red' on the CO2 scale. This seemed to explain at least part of why I would get those headaches. Opening a window and letting air in is rarely an option. I have bad allergies during spring, and the pollen here gets really bad then too. For the rest of the year, opening a window would mean either dealing with hot, humid conditions or uncomfortably cold temperatures at night. I found out about something called an Energy Recovery Ventilator and was interested.

{% include image-gallery.html images="/assets/onlineervgraphicIusedtobrainstormawaytomakemyown.jpg" height="350"%}
One of these works by exhausting indoor air and bringing in fresh air. They get physically close to each other in the middle portion called a heat exchanger, but they do not actually touch. I decided to experiment and make something like this.

{% include image-gallery.html images="/assets/energyrecoveryvmyolda1combowithacatonthefrontprintingthehugehousing.jpg" height="350" %}

I had just bought my 3D Printer and wanted to build my computer modeling skills. This project seemed to fit the bill. I had not yet learned SOLIDWORKS, so, armed with calipers and a vivid imagination, I made a design in Tinkercad. It had to be split in two because of size constraints on my Printer.

{% include image-gallery.html images="/assets/energyrecoveryvwideshotbutnotfullycompleteyetalmostthoughhasfanandpowersupplyandarduinoandhousingjustneededaparttoconnectittothewindow.jpg" height="350" %}



{% include image-gallery.html images="/assets/EnergyRecoveryVentInsidePhoto.jpg" height="350" %}

I used an old corrugated plastic sign and a rotary tool to make squares that I crisscrossed in the center of the design. The rotary tool didn't make very clean cuts, but that's acceptable for a demo. I used old server fans to pull/push air in the system. I used painter's tape to seal up holes because that is what I had on hand.

{% include image-gallery.html images="/assets/thermalcameraphotoofenergyrecoveryv.jpg" height="350" %}

This is a photo from a thermal camera of the system in use on a mild February day. I do not think the uninsulated PLA or the somewhat jagged, loose heat exchanger were very efficient, but it was a fun build. I used Home Assistant and a TP-Link Smart Plug to toggle the system on and off when the CO2 in the room got too high. Later on, I found out that the Honeywell thermostat had a circulate fan mode, so I swapped my automation to that instead of this build.


## Sensors

### Particle Sensor
{% include image-gallery.html images="/assets/particlesensorsolderedtoesp32butnohousing-ondesk.jpg" height="350" %}
I got this SPS30 Particle sensor from AliExpress. I was just a bit concerned about doing my long 3D prints indoors. It showed that my setup significantly increased the number of particles in the air. Once I got a large Costco Winix air purifier, it has kept the levels low. I also got a printer with an enclosure and rigged it to exhaust air outside, which also helped reduce airborne particles. The sensor is connected to my Home Assistant server but only to monitor the count, no automations.

{% include image-gallery.html images="/assets/CADsolidworksscreenshotofmyparticlesensorhousing.jpg" height="350" %}
{% include image-gallery.html images="/assets/particlesensorinabrightred3dprintedhousingImadeinsolidworkswithholesformassreductionandreducedwaste.jpg" height="350" %}
This is the housing I designed and printed for the sensor. I really did not want to use much material on this, as you can see.

### VOC Sensor
{% include image-gallery.html images="/assets/3dprintervocsensorandwindowexaust.jpg" height="350" %}
This is yet another sensor I bought from AliExpress, connected to an ESP32, and added to my Home Assistant server. Initially, this was just a data point, but once I got my Bambu P2S enclosed 3D Printer and wanted to print with engineering filaments like ASA and ABS, it became crucial. I needed to be certain that even though I was exhausting the air outside, I was not exposing my family and pets to chemical irritants. The Printer is far from anyone's bedroom and is on a different floor from the animals, but I wanted to be cautious. I set it up next to the active window exhaust and ran a long ABS print with a 10% exhaust duty cycle during printing, followed by a long 100% exhaust after the print was over. The VOC readings did not budge.

### Energy Sensors.
{% include image-gallery.html images="/assets/asinglepzemina3dprintedhousingImade.jpg" height="350" %}



{% include image-gallery.html images="/assets/closeupofrawpzemboard.jpg" height="350" %}



{% include image-gallery.html images="/assets/pzemfor3stagetanklesswaterheaterwith3dprintedhousingImadeinsolidworks.jpg" height="350" %}
Partly to become more informed about the energy in the house, and partly a problem in search of a solution, I ordered current/energy sensors on AliExpress called PZEM-004T. This was my first soldering project after I bought my own soldering iron and was taught by IEEE students. I printed two housings and connected two boards to an ESP32. We installed it in the electrical box to monitor the energy used by the two A/C units. Luckily, I got both orientations of the CT rings correct. I had the ones that did not open and close because I heard they have more accuracy, but if I got the orientation wrong, the reading would not be correct. In software, I multiplied V*I to get power and used an integral sensor to get energy. This proved to be quite a finicky way of doing it because it kept dropping Wi-Fi (it is basically in a Faraday cage). I learned that it actually tracks energy usage on the device itself and reports it, like an odometer. Later, I added 3 sets of these sensors to the 3-stage tankless water heater to track that too. Initially, this was to inform my family of what was and was not using that much energy in the house (A/C + Dryer + Hot Water trumped leaving the LED lights on by orders of magnitude). Later, this actually became a key data point in deciding to move us to a TOU (time-of-use) Energy plan. I could track what is using electricity, tune those things, and adjust our behavior to use it less during high-cost times of day and more during low-cost times. Our energy bill has dropped by $20-$120, depending on the month. 

---
layout: post
title: Home Energy Monitoring & Air Quality
description: I like to use open source software and inexpensive electronics to measure and do things around the house, from making sure the air is clean and safe to making sure we understand what is contributing to the electric bill.
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

<!-- DETAILS FROM ANTHONY:
- PZEM modules ("pzem 4 or whatever") on ESP32s measuring the A/C units + tankless water heater; discounted TP-Link smart plugs on 120V appliances → showed the family what's actually driving the electric bill → informed the decision to move to a time-of-use (TOU) plan
- Home Assistant automation exploiting TOU + house occupancy: saves $50–90/month on the Duke Energy bill (both summer and winter schedules) while keeping sleep/weekend comfort
- 3D-printed ERV (Feb): 2× harvested 80mm server fans; 3D-modeled two-channel system with crisscrossed corrugated-plastic squares at the core; pull-push configuration — HAS photos + thermal camera images, maybe Aranet 4 readings from that time
- Later REPLACED the ERV with an HA automation: toggles the Honeywell thermostat's circulate mode, but only at night + only if he's home + only if his room reads above 1000 on the Aranet (CO2)
- 3D printer: outdoor active exhaust for engineering plastics; VOC sensor → ESP32 → Home Assistant mounted near the printer, monitoring before/after the exhaust install
- $30 AliExpress particle sensor + ESP32 → Home Assistant particle sensor → validated the Costco Winix purifier ("turns out, it works extraordinarily")
- Circadian wake-up automation in HA: lots of morning light (some days are spent in his room a long time) -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- $50–90/month savings — how did you measure that? (Before/after bills? Normalized for weather?)
- How did you validate the PZEM readings were accurate?
- ERV: did the thermal images show actual heat recovery? What was the effectiveness, roughly?
- Why replace the ERV with the thermostat automation — what did the data say?
- The Winix validation: what did the particle numbers look like before/after? -->

<!-- MISSING / WOULD HELP:
- The thermal camera images + Aranet readings — these are GOLD for a portfolio, dig them up
- Before/after electricity bill numbers
- Photos: PZEM install, ERV build, printer exhaust, sensor placements -->

## Description

I like to use open source software and inexpensive electronics to measure and do things around the house, from making sure the air is clean and safe to making sure we understand what is contributing to the electric bill.

## Energy Recovery Ventilator 

  I during COVID Summer, I spent a lot of time in my room. The door closed and the A/C not turning on that often, I would often get bad headaches and brain fog that would go away if I went downstairs to the living room or kitchen. A few years later, CO2 tracking came across my radar. I bought an Aranet 4 Wireless E-Ink CO2 monitor and found out that my room regularly gets 'in the yellow' or 'in the red' on the CO2 scale. This seemed to at least partially explain why I would get those headaches. Opening a window and letting air in is almost never an option. I have bad allergies during Spring and the pollen here gets really bad then too. The rest of the year, opening a window would mean either dealing with hot and humid or uncomfortably cold temperatures at night. I found out about something called an Energy Recovery Ventilator and was interested.

{% include image-gallery.html images="/assets/onlineervgraphicIusedtobrainstormawaytomakemyown.jpg" height="350"%}
The way one of these works is that it exhausts indoor air out and brings in fresh air. They get physically close to each other in the middle portion called a heat exchanger, but they do not actually touch. I figured that I could experiment and make something like this.

{% include image-gallery.html images="/assets/energyrecoveryvmyolda1combowithacatonthefrontprintingthehugehousing.jpg" height="350" %}

I had just recently bought my 3D printer and I wanted to build my computer modeling skills. This project seemed to fit the bill. I had not learned SOLIDWORKS at this point, so armed with calipers and a good imagination, I made a design in TinkerCad. It had to be split in two because of size constraints on my printer.

{% include image-gallery.html images="/assets/energyrecoveryvwideshotbutnotfullycompleteyetalmostthoughhasfanandpowersupplyandarduinoandhousingjustneededaparttoconnectittothewindow.jpg" height="350" %}



{% include image-gallery.html images="/assets/EnergyRecoveryVentInsidePhoto.jpg" height="350" %}

I used an old corrugated plastic sign and a rotary tool to make squares that I crisscrossed in the center of the design. The rotary tool did not make very clean cuts, but I figured that was pretty okay for just a demo. I used old server fans to pull/push air in the system. I used painters tape to seal up holes because that is what I had on hand.

{% include image-gallery.html images="/assets/thermalcameraphotoofenergyrecoveryv.jpg" height="350" %}

This is a photo from a thermal camera of the system in use on a mild February day. I do not think the uninsulated PLA nor the somewhat jagged and loose heat exchanger were very efficient, but it was a fun build. I used Home Assistant and a TP-Link Smart Plug to toggle the system on and off when the CO2 in the room got too high. Later on, I found out that the honeywell thermostat had a circulate fan mode, so I swapped my automation to that instead of this build.


## Sensors

### Particle Sensor
{% include image-gallery.html images="/assets/particlesensorsolderedtoesp32butnohousing-ondesk.jpg" height="350" %}
I got this SPS30 Particle sensor from AliExpress. I was just a bit concerned by doing my long 3D prints indoors. It did show that my set up increased the particle count in the air quite a bit. Once I got a large Costco Winix air purifier, it has kept the levels low. I also got a printer with an enclosure and rigged it to exhaust air outside and that also contributed to a reduction of particles in the air. The sensor is connected to my Home Assistant server but only to monitor the count, no automations.

{% include image-gallery.html images="/assets/CADsolidworksscreenshotofmyparticlesensorhousing.jpg" height="350" %}
{% include image-gallery.html images="/assets/particlesensorinabrightred3dprintedhousingImadeinsolidworkswithholesformassreductionandreducedwaste.jpg" height="350" %}
This is the housing I designed and printed for the sensor. I really did not want to use much material on this as you can see.

### VOC Sensor
{% include image-gallery.html images="/assets/3dprintervocsensorandwindowexaust.jpg" height="350" %}
This is yet another sensor I bought from AliExpress, connected to an ESP32, and added to my Home Assistant server. Initially, this was just a datapoint, but once I got my Bambu P2S enclosed 3D printer and wanted to print with engineering filaments like ASA and ABS, this became crucial. I needed to be certain that even though I was exhausting the air outside that I was not exposing my family and pets to chemical irritants. The printer is far from anyone's bedroom and is on a different floor from the animals, but I wanted to be cautious. I set it up next to the active window exhaust and did a long ABS print with a 10% exhaust duty cycle while printing and a long 100% exhaust after the print was over. The VOC readings did not budge.

### Energy Sensors.
{% include image-gallery.html images="/assets/asinglepzemina3dprintedhousingImade.jpg" height="350" %}



{% include image-gallery.html images="/assets/closeupofrawpzemboard.jpg" height="350" %}



{% include image-gallery.html images="/assets/pzemfor3stagetanklesswaterheaterwith3dprintedhousingImadeinsolidworks.jpg" height="350" %}
To become more informed about the energy in the house, and somewhat a problem in search of a solution, I ordered current/energy sensors on AliExpress called PZEM-004T. This was my first soldering project after I bought my own soldering iron and was taught by IEEE students how to do it. I printed two housings and connected two boards to an ESP32. We installed it in the electrical box to monitor the energy used by the two A/C units. Luckily, I got both orientations of the CT rings correct. I had the ones that did not open and close because I heard they have more accuracy but if I got the orientation wrong, the reading would not be correct. In software, I multiplied V*I and used that as power and used an integral sensor to get energy. This proved to be quite a finicky way of doing it because it regularly dropped Wi-Fi (it is basically in a faraday cage). I learned that it actually has a way of tracking energy usage on the device itself and reporting it, like an odometer. Later, I added 3 sets of these sensors to the 3 stage tankless water heater to track that too. Initially, this was just to inform my family of what was and was not using that much energy in the house (A/C+Dryer+Hot Water trumped leaving the LED lights on by orders of magnitude. Later, this actually became a key point of data to decide to move us to a TOU (time of use) Energy plan. I could track what is using electricity and tune those things and change our behavior to use it less during high energy cost times of the day and use them more during low cost times. Our energy bill has dropped $20-120 depending on the month. 



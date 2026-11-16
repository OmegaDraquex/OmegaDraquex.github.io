---
layout: post
title: Autonomous Line-Tracking Robot Car
description: A log of my NCSU Embedded Systems Experience
card_image: /assets/306front.jpg
order: 2
skills:
  - MSP430 Bare-Metal C
  - Robotics
  - SMD Soldering & Rework
---

## Description

ECE 306 Embedded Systems is an infamous class at NCSU. Either you love it, hate it, or hate that you love it. It is time-consuming. it is so hands-on; sometimes it is terrible; most of the time it is a lot of fun!

## Photos

{% include image-gallery.html images="/assets/306carearlydaysdiagnosedbrokencapacitormicroscopepicture.jpg" height="350" %}

The semester had a rocky start. Because of alleged restrictions on when the department could order the parts, they were ordered very close to the start of the semester. It took way longer than normal for us to receive our parts. When we received them, we were told that fabrication mistakes were expected occasionally, and we were instructed to inspect our board for defects before plugging it in. I recently bought a cheap digital microscope, so I reviewed each SMT component. I found a capacitor that had been decapitated like 95% of the way through. I tried to desolder it for a bit, but it was really, really stuck on there. The TA I brought it to had just as much trouble as I did getting it off and tried many different strategies. What ended up working was drowning the component in an absurd amount flux and doing a long boil, sending the component to the surface.

{% include image-gallery.html images="/assets/306-18650-2sbatterypackold-originalconfig.jpg" height="350" %}
{% include image-gallery.html images="/assets/bottomof306car.jpg" height="350" %}
My instructor said that many people would have issues because they aren't monitoring their remaining battery life. The car's stock configuration uses a power supply consisting of four AA batteries in series. Instead of dealing with all the drawbacks of disposable batteries, I ordered four 18650 Lithium-Ion batteries, a DC-to-5V high-current converter board, a 2S Battery Management System (BMS), and a high-rated battery charger. My original design connected two lithium-ion batteries in series to the BMS, connected the output to a rocker switch, connected the rocker switch to the converter, and connected the converter to the car's battery input. I used the DC-to-5V board because I did not know how much voltage the car could handle. I knew that it could take at least 6.3V, but my batteries could bring it up to 7-8V. Recently, I simplified this power design a lot after learning it can handle up to about 15V. Now, it is just the batteries and the BMS. I also cut it down because keeping it at 5V limited how fast my motors could run.

{% include image-gallery.html images="/assets/306carcloseupbutwitha3dprintedsilvergrandmarquisshellorhaton.jpg" height="350" %}
This is a 3D printed cover I used to use with my robot car to protect it during transportation.

{% include image-gallery.html images="/assets/306ircustomshroud.png" height="350" %}
I 3D-printed a custom shroud for my IR Sensor Board setup on my car. We were given one, but I wanted to make some modifications to see if that would make it perform more consistently. I used digital calipers to recreate the original design in SOLIDWORKS. I made a few modifications, such as making it a bit taller and adding channels to isolate the IR Sensor Pairs from the emitters. I set it too low to the ground, which is fine in normal conditions, but we were warned that on demo day we would need to be able to drive up onto a platform, which my design cannot do. I later redesigned it to print it in ASA and include a thin slot for me to add aluminum foil within the walls. Then I covered that in electrical tape, all to block as much interference IR from coming in.
{% include image-gallery.html images="/assets/PXL_20261115_004548369.jpg" height="350" %}
Once time permitted, I became interested in adding more sensors to my car to upgrade its capabilities. I identified some unused pins, set them up for I2C, and ordered some sensors. The first extra sensor I implemented was a BNO055 9DOF Inertia sensor. With it, the car can detect what angle the car is facing and the angular velocity. The first feature I got out of it was being able to autonomously calibrate what the lowest voltage the motors can take before they actually move by recording the exact DAC value that the car is at when the sensor detects a change in angular velocity. I also use it to calibrate the PWM values required to make each of the motors run at the same rate so the car can drive straight. The second sensor I implemented was a VL53L0X Time-of-Flight (ToF) Laser Distance Sensor. I had a few left over from a previous project. It detects how far away objects are from the car. I use it to slow the car down when it gets too close to the wall or other objects. The third optional sensor I implemented was the PMW3901 (bridged by a Seeed Studio XIAO SAMD21) Optical Flow Odometry Sensor. It is similar to the sensor you would find in a computer mouse. This one I can use to tell the car to move a very specific distance or flag when the car is being told to move but the sensor does not detect displacement. I also use it to very roughly map out the path the car takes. I had to do so much troubleshooting to get all of these to work. They all share an SDA SCL pair. Some of the issues include powering the XIAO from the 3.3V rail instead of 5V, a swapped SDA SCL on one component, not driving a pin to ground that was supposed to be, not restricting the I2C probing behind a start up delay and voltage range, not having a way for the sensors to recover if they temporarily dropped out and more. I used Antigravity GUI to run a troubleshoot, plan, code, flash, test, loop when a lot of the bugs were piling up and I was not sure what was going wrong firmware-wise.  

{% include image-gallery.html images="/assets/app.png" height="350" %}
This is the Android App that I had Antigravity make. It provides several convenient functions. The first is that the robot car is programmed to publish its IP address, subnet mask, and port number to a ntfy topic, the app pulls the latest ntfy message and autofills the car's IP address, so I do not have to be near the car to read and manually input it. I can also read the voltage of the car batteries from the app. I can read the values of the three sensors on the car and have a fun little map to see roughly what path the car took. It can send commands to control the car with a joystick or with more precise angle and distance commands. It also lets me trigger the autocalibration mode.
## Demo video

{% include youtube-video.html id="UGPsE9ZyQIk" autoplay="false" %}

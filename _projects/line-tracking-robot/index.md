---
layout: post
title: Autonomous Line-Tracking Robot Car
description: A short log of my NCSU Embedded Systems Experience (The Robot Car Class)
card_image: /assets/306carextremetopview.jpg
order: 4
skills:
  - MSP430 Bare-Metal C
  - Robotics
  - SMD Soldering & Rework
---

## Description

ECE 306 Embedded Systems is an infamous class at NCSU. Either you love it, hate it, or love-and-hate it. It is time-consuming; it is so hands-on; sometimes it is oh so terrible; most of the time it is a lot of fun.

## Photos

{% include image-gallery.html images="/assets/306carearlydaysdiagnosedbrokencapacitormicroscopepicture.jpg" height="350" %}

The semester had a rocky start. Because of alleged restrictions on when the department could order the parts, they were ordered very close to the start of the semester. It took way longer than normal for us to receive our parts. I am glad that some of the parts students had to source themselves in the past are now available for purchase through the NCSU IEEE Student Organization. I would gladly trade a bit more money for the convenience of having all the parts I need, hassle-free. When we got our first board, we were told it was built by student volunteers on campus using a pick-and-place and reflow oven, overseen by the professor. Mistakes were expected occasionally, and we were instructed to inspect our board for defects before plugging it in. I just bought a cheap digital microscope, so I reviewed each SMT component. I had a capacitor that had been decapitated like 95% of the way through. I tried to desolder it for a bit, but it was really, really stuck on there. I brought it to the professor during office hours, and he told me the component capacitance value and said to bring it to a TA during my lab time. The TA had just as much trouble as I did getting it off and tried many different strategies. What ended up working was drowning the component in flux and doing a long boil; it floated to the surface.

{% include image-gallery.html images="/assets/306-18650-2sbatterypackold-originalconfig.jpg" height="350" %}
My instructor told us that we had to optimize our power management by turning things off when they are not in use. He said that many people would have issues because they aren't monitoring their remaining battery life. The car's stock configuration uses a power supply consisting of four AA batteries in series. The professor did say we could talk to him to get our car set up with a lithium-ion battery if we were interested. I am the kind of person who will go the extra mile to do something cool and avoid a tedious, stressful situation. I ordered four 18650s from the 18650 battery website, a DC-to-5V high-current converter board, a 2S Battery Management System (BMS), and a high-rated battery charger. My original design connected two lithium-ion batteries in series to the BMS, connected the output to a rocker switch, connected the rocker switch to the converter, and connected the converter to the car's battery input. I used the DC-to-5V board because I did not know how much voltage the car could handle. I knew that it could take at least 6.3V, but my batteries could bring it up to 7-8V. Recently, I trimmed this down a lot after learning it can handle up to about 15V. Now, it is just the batteries and the BMS. I also cut it down because keeping it at 5V limited how fast my motors could run.

{% include image-gallery.html images="/assets/306carcloseupbutwitha3dprintedsilvergrandmarquisshellorhaton.jpg" height="350" %}
This is a top-down photo of my car, taken for an assignment the professor will use to prevent people from cheating and using someone else's car on the final demo day.

{% include image-gallery.html images="/assets/306ircustomshroud.png" height="350" %}
I 3D-printed a custom shroud for my IR Sensor Board setup on my car. We were given one, but I wanted to make some modifications to see if that would make it perform more consistently. I used calipers to recreate the original design in SOLIDWORKS. I made a few modifications, such as making it a bit taller and adding channels to isolate the IR Sensor Pairs from the emitters. I set it too low to the ground, which is fine in normal conditions, but we were warned that on demo day we would need to be able to drive up onto a platform, which my design cannot do. I plan to redesign it to print in PETG or ASA and include a thin slot for me to add aluminum foil within the walls.


## Demo video

{% include youtube-video.html id="UGPsE9ZyQIk" autoplay="false" %}

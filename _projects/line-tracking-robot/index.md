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

<!-- DETAILS FROM ANTHONY (ECE 306, in progress):
- Bare-metal C firmware on TI MSP430: timer interrupts (switch debounce), motor drive, ADC
- Power: 18650 2S Li-ion pack — REMOVED the 5V regulator ("had that previously because I knew it could take it but I didn't know its upper limits")
- Soldered tiny optional PFETs that let firmware measure battery voltage → disables high-draw subsystems (DAC output stage, screen) to keep the MSP debug/programming interface from browning out
- Completed line-tracking + switch handling; integrating 12-bit DAC motor-drive stage
- Braking saga: Carlson warned plugging (reversing H-bridge while spinning) spikes ~7A through 2-3A SOT-23 FETs → brake mode = both low-side FETs on (shorted motor terminals), with all-off sequencing to avoid shoot-through -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- Why 2S Li-ion over the stock pack? What changed electrically (voltage, current, runtime)?
- How does the PFET battery sensing work, and at what threshold do you shed load?
- What happens during motor stall — how do you avoid brownout resets?
- Course project: what was YOUR contribution vs. the team? -->

<!-- MISSING / WOULD HELP:
- Photos: the car, the PFET mod close-up, the battery pack
- Video of it tracking a line
- Clarify team vs. individual contributions -->

## Description

ECE 306 Embedded Systems is an infamous class at NCSU. Either you love it, hate it, or love and hate it. It is time consuming, it is so hands on, sometimes it is oh so terrible, most of the time it is a lot of fun.

## Photos

{% include image-gallery.html images="/assets/306carearlydaysdiagnosedbrokencapacitormicroscopepicture.jpg" height="350" %}

The semester had a rocky start. Because of alleged restrictions on when the department could order the parts, they were ordered very close to the start of the semester. It took way longer than normal for us to receive our parts. I am glad that some of the parts that students had to source themselves in the past were available to purchase through the NCSU IEEE Student Organization. I gladly would trade a bit more money for the convenience of having all the parts I need hassle-free. When we got our first board, we were told that it was built with the pick-and-place and reflow oven by student volunteers on campus overseen by the professor. Mistakes were expected occasionally and we were instructed to inspect our board for defects before plugging it in. I just bought a cheap digital microscope, so I reviewed each of the SMT components. I had a capacitor that had been decapitated like 9%% of the way through. I tried to desolder it for a bit, but it was really really stuck on there. I brought it to the professor during office hours, and he told me the component capacitance value and said to bring it to a TA during my lab time. The TA had just as much trouble as I did getting it off and tried many different strategies. What ended up working was drowning the component in flux, doing a long boil, and it floated to the surface.

{% include image-gallery.html images="/assets/306-18650-2sbatterypackold-originalconfig.jpg" height="350" %}
My instructor told us that we had to optimize our power management by turning things off when they are not in use. He said that many people would have issues because they aren't monitoring the battery life they have left. The stock configuration of the car uses a power supply comprised of four AA batteries in series. The professor did say we could talk to him to get our car set up with a Lithium Ion battery if we were interested. I am the kind of person who will be a bit extra in order to do something cool and avoid a tedious and stressful situation. I ordered four 18650s from the 18650 battery website, a DC to 5V high current converter board, a 2S Battery Management Board (BMS), and a high rated battery charger. My original design connected two lithium ion batteries in series to the BMS, connected the output to a rocker switch, connected that to the converter, and connected that to the battery input of the car. I used the DC to 5V board because I did not know how much voltage the car could take. I knew that it could take at least 6.3V, but my batteries could bring it up to 7-8V. Recently, I trimmed this down a lot after learning it can take up to something like 15V. Now, it is just the batteries and the BMS. I also cut it down because keeping it at 5V was restricting how fast my motors could be run.

{% include image-gallery.html images="/assets/306carcloseupbutwitha3dprintedsilvergrandmarquisshellorhaton.jpg" height="350" %}
This is a top down photo of my car, taken for an assignment the professor will use to prevent people from cheating and using someone else's car on the final demo day.

{% include image-gallery.html images="/assets/306ircustomshroud.png" height="350" %}
I 3D printed a custom shroud for my IR Sensor Board set up on my car. We were given one, but I wanted to make some modifications to see if that would make it perform more consistently. I took calipers and recreated the original design in SOLIDWORKS. I made a few modifications like making it a bit taller and adding channels for the IR Sensor Pairs to be isolated from the emitters. Long story short, I made it too low to the ground, which normally would be fine, but we were warned that on demo day we will need to be able to drive up onto a platform, which my design will absolutely not be able to do. I plan on redesigning it to print it in PETG or ASA and have a thin slot for me to add aluminum foil within the walls.
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->


## Demo video

<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

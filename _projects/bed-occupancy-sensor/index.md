---
layout: post
title: Bed-Occupancy Sensor & Wake Accountability
description: Eager to try out new software and use it to make a fun little project, I built a system that uses Mark Zuckerberg's latest push in the AI race to give me a push out of bed.
card_image: /assets/bedsensormain.jpg
order: 2
skills:
  - ESP32
  - Analog Sensor
  - SolidWorks CAD
  - Muse Gadgets SDK
---

<!-- DETAILS FROM ANTHONY (Oct 2026, working):
- FSR pressure sensor under the mattress (slat → FSR → 3D-printed puck → mattress) into ESP32 ADC
- Voltage divider resistor ended at 460Ω — iterated DOWN from 10k → 1k → 460 because the divider was "bottoming out too quickly" (saturating); show the divider math
- 3D-printed PLA puck (30mm × 7mm, chamfered) focuses force into the sensor center
- KiCad single-sided PCB (milled on Bantam), 0805 resistor via NeoDen pick-and-place
- Firmware: threshold + 60s below-threshold dwell before "out of bed" (roll-over immunity)
- Built partly to test the Muse Code agent + Muse Gadgets feature (ESP32 pairs as a Muse gadget exposing a bed.occupancy command)
- "For fun, to have a little guy challenge the reason for why I'm in bed" — scheduled 11PM bedtime / 7:15AM wake / 7:30AM escalation checks; Muse only nags when the sensor says you're off-plan
- LIVE and in daily use -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- Why did 10kΩ bottom out, and how did you land on 460Ω? (Walk through the divider math.)
- How do you reject false triggers — rolling over, sitting on the bed, luggage on the bed?
- Why the 60-second dwell? What breaks without it?
- How does the Muse Gadgets integration work at a high level? -->

<!-- MISSING / WOULD HELP:
- Photos: the sensor stack, the puck, the PCB, ESP32 wiring
- The divider schematic (even a hand sketch)
- A screenshot of a morning accountability nudge -->

## Description

Curious to see how the new open-source Muse Gadget SDK and Muse Code functioned, I came up with a fun little project. One where Muse gets to challenge and log the actual time I stay in bed.

## Photos



{% include image-gallery.html images="/assets/bedsensorpuck.png" height="350" %}
This is a little puck that I threw together in a few minutes in SOLIDWORKS to sit on top of a force sensor, creating better contact between the mattress and the bed without making me the proverbial Princess and the Pea.


{% include image-gallery.html images="/assets/MUSECodeTerminalScreenshot.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->
This is what the Muse Code interface looks like.


{% include image-gallery.html images="/assets/bedsensordiagram.png" height="350" %}
A diagram of how it is wired up.


{% include image-gallery.html images="/assets/musemessage.png" height="350" %}
## Write-up

The other day, the (privacy nightmare) Muse LLM Tool released by Meta informed me that the company had yet another gift for the open-source community: an open-source SDK that lets developers connect whatever they want to a Raspberry Pi or ESP32 and have Muse interact with it. I'm predisposed to explore new, flashy hardware or software if I can make a project out of it. The LLM guided me through installing Muse Code on my system. It was as simple as two commands (and entering in the credit card . . . I'll try anything once), and I was off to the races.

I drafted up my vision for a device that detects whether you are physically in bed. It uses a 40 x 40mm force sensor connected to a miniature ESP32 and connects to Muse. Pretty simple, but it works quite well as a test. The agent asked me a few clarifying questions and then went to work. It wasn't fast, but it made something functional.

The first output was an Arduino Sketch, primarily because it would let me test it in real time. It was decided that we would do an iterative process with the voltage divider resistor. I soldered the force sensor to 3.3 and pin 4 of the ESP32 and pin 4 to a 10K ohm resistor connected to ground. My first test was a good data point, but it was not a success. A light touch from my fingertips would fully saturate the sensor. I desoldered the resistor from the pin and the wire and soldered a 1k ohm resistor. It was more promising. I used various household objects to test it: A US Quarter, an AA Alkaline Battery, and my phone. My 250g phone was very close to saturating it. The rule of three held in this situation, and a 450-ohm resistor I luckily owned did the trick. The objects had discernible outputs, and it had good contrast when under the mattress with me in bed vs not.

I did note, however, that the output value climbed at a diminishing rate. Something like 1600 with just the mattress, climbing to around 2000 before stopping. When I was on the mattress, it would be around 3500, climbing to 3900. The max was like 4500, so this was perfect. I informed Muse Code of this, and it accounted for the climb by having a 60-second debounce period and setting up a dynamic threshold. The debounce also prevents the device from thinking I am jumping up and down on the bed when I am just rolling over.

It wrote the firmware and flashed it itself. I had to fish the device from under the mattress to confirm the adoption into Muse by pressing a button. Presumably, it works. Muse Gadgets do not seem to push much info to the user as Home Assistant does. I will perform more testing to determine if it is functional. So far, I have just set up static, scheduled routines for Muse to poll the sensor and determine whether I am in bed. In the future, I want it to log my sleep so I can see how my time in bed compares to the sleep my smartwatch believes I am getting. This project cost 31 cents in compute.

{% include image-gallery.html images="/assets/MuseAPICost.png" height="300" %}


<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

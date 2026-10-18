---
layout: post
title: Bed-Occupancy Sensor & Wake Accountability
description:
skills:
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

<!-- TODO: 2-3 sentences in your words. -->

## Photos

<!-- TODO: drop photo files into _projects/bed-occupancy-sensor/, then embed:
{% include image-gallery.html images="photo1.jpg, photo2.jpg" height="400" %} -->

## Write-up

<!-- TODO: problem → approach → what you debugged → where it stands -->

## Demo video

<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

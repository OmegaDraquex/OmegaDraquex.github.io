---
layout: post
title: Autonomous Line-Tracking Robot Car
description:
skills:
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

<!-- TODO: 2-3 sentences in your words. -->

## Photos

<!-- TODO: drop photo files into _projects/line-tracking-robot/, then embed:
{% include image-gallery.html images="photo1.jpg, photo2.jpg" height="400" %} -->

## Write-up

<!-- TODO: problem → approach → what you debugged → where it stands -->

## Demo video

<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

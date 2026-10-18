---
layout: post
title: HP Prime G2 FPGA Video Interface
description:
skills:
---

<!-- DETAILS FROM ANTHONY (Oct 2026, in progress):
- HP Prime G2 calculator → tap the LCD bus → decode in FPGA → HDMI out → Python capture on PC
- 13.3 MHz serial-RGB LCD bus; 320x240 RGB565 frames
- Tang Nano 9K (Gowin GW1NR-9); PSRAM framebuffer (on-chip BSRAM too small for a 150KB frame); TMDS encoder → 640x480@60 HDMI (pixel-doubled)
- prime_pixel.v decoder written from scratch from the protocol spec — passed full sim: 76,800 pixels, 0 value/coordinate errors at real Prime timing
- Open-source Gowin EDA toolchain (yosys + nextpnr-gowin)
- Status: decoder done in sim; frame buffer + HDMI output path in progress; board bring-up next -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- Why tap the LCD bus instead of using the calculator's USB or a camera pointed at the screen?
- How did you reverse-engineer the LCD protocol? (logic analyzer? docs?)
- What was the hardest RTL bug, and how did you find it?
- Why PSRAM instead of on-chip BRAM?
- How do you verify the HDMI output is pixel-correct? -->

<!-- MISSING / WOULD HELP:
- Photos: tap wiring on the calculator flex, Tang Nano 9K setup, HDMI output on a monitor
- Sim waveform screenshots
- Is the repo public? Link it.
- 60-90s demo video: calculator screen appearing on the monitor via your pipeline -->

## Description

<!-- TODO: 2-3 sentences in your words. -->

## Photos

<!-- TODO: drop photo files into _projects/hp-prime-fpga-rig/, then embed:
{% include image-gallery.html images="photo1.jpg, photo2.jpg" height="400" %} -->

## Write-up

<!-- TODO: problem → approach → what you debugged → where it stands -->

## Demo video

<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

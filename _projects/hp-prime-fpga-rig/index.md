---
layout: post
title: HP Prime G2 FPGA Video Interface
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.
card_image: /assets/Tang9knocalculatorhdmidemo.jpg
order: 1
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

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat duis aute irure dolor in reprehenderit.

## Photos

<!-- No additional photos yet — the highlight image at the top of the page is the only one so far. To add more: copy a caption + image-gallery block from another project page and swap in your "/assets/filename". -->

## Write-up

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.

Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt, neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur adipisci velit.

At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.

## Demo video

<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

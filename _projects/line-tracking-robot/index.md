---
layout: post
title: Autonomous Line-Tracking Robot Car
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.
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

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat duis aute irure dolor in reprehenderit.

## Photos

{% include image-gallery.html images="/assets/306carextremetopview.jpg, /assets/306carcloseupbutwitha3dprintedsilvergrandmarquisshellorhaton.jpg, /assets/306-18650-2sbatterypackold-originalconfig.jpg, /assets/306carearlydaysdiagnosedbrokencapacitormicroscopepicture.jpg, /assets/306ircustomshroud.png" height="350" %}
<!-- To add more photos: append "/assets/filename" to the images list, separated by ", ". -->

## Write-up

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.

Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt, neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur adipisci velit.

At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.

## Demo video

<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

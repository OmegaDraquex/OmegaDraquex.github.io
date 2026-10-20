---
layout: post
title: Auto Shop Tech & Vehicle Work
description: Projects that I underwent at my family auto repair shop, mostly the ones that have nothing to do with cars.
card_image: /assets/mytransmissiononajackandmycarontheliftaboveit.jpg
order: 6
skills:
  - Automotive Diagnostics
  - Engine & Transmission Service
  - Electrical Troubleshooting
  - Small-Business Wi-Fi Deployment
  - Custom Dashboard Displays
  - 3D-Printed Tooling
  - Virtualization
---

<!-- DETAILS FROM ANTHONY (Hwy 42 Auto Service — family shop):
- Shop network: added a non-office AP (concrete building kills signal), guest network (no signal by the shop otherwise), QR code so customers can join easily
- Replaced the whiteboard calendar with a cheap 4K Walmart TV mounted vertically running the Tekmetric calendar + a vibe-coded CSS modification so each appointment displays in full instead of being concatenated
- Moved the main lot camera (always dropping signal) onto Ethernet
- 3D-printed office trinkets, tire tread depth tools, piston/valve mechanical demos

- Robinair A/C machine resurrection: dusty, disassembled, broken for ~5 years after sucking up stop-leak. On a visit (not working, just tinkering): opened it up, pulled every mechanical valve, tested each with a hose + compressed air + his new DC power supply — ALL worked, ruled out. Dad thought the vacuum pump was dead (it hadn't turned on years ago on a scrap car full of air) — Anthony reasoned the pump only engages in VACUUM mode and they'd been testing in RECOVER. Then: filter swap — put the new machine's old filter on the old machine and it worked. "It was as simple as that but it was really rewarding." Tested on personal/scrap cars, flawless. (Needs a tune-up, of course.)
- With his dad: replaced the torque converter on his Grand Marquis + alternator, tires, belt, radio; routed and installed a backup camera
- Does the service on the family's vehicles regularly — "it feels really good to be trusted to do that" -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- The Robinair: walk through the diagnostic logic — how did you isolate valves vs. pump vs. filter?
- The CSS mod: what exactly did you change, and why did the default view fail?
- The concrete-building AP: what did you learn about RF in that environment?
- (For systems-integration roles: this page screams customer empathy + resourcefulness. Lean into it.) -->

<!-- MISSING / WOULD HELP:
- Photos: the vertical TV calendar, the Robinair, the Grand Marquis work, printed tools
- The CSS snippet (small, fun detail) -->

## Description

Each summer, I worked at my parents' automotive repair shop. Most of my time was spent repairing vehicles, but every so often, I got to use my other skills to help out. 

## Photos


{% include image-gallery.html images="/assets/acmachine.jpg" height="350" %}
We had a Robinair A/C Refrigerant Machine that was broken for five years after sucking up stop-leak from someone's car. On a visit to the shop off the clock, I opened it up, pulled every solenoid valve, and tested each with a hose, compressed air, and my new DC power supply. All of them worked, so a stuck valve was ruled out. A theory thrown out previously was that the vacuum pump was dead. I figured that the vacuum pump might have been fine since it only engages in VACUUM mode and the machine could only try RECOVER while in this broken state. Then as a last ditch effort, I put the new machine's old filter on the old machine and it worked. I tested it on personal scrap cars, and it worked flawlessly

{% include image-gallery.html images="/assets/solenoid.jpg" height="350" %}
{% include image-gallery.html images="/assets/2acmachines.jpg" height="350" %}
Now we have a backup.

{% include image-gallery.html images="/assets/scope.jpg" height="350" %}
We were doing a diagnosis of the A/C system on a car during the summer. The technician could not find an A/C compressor relay. A search revealed that the car does not use a binary on/off system for controlling the compressor, instead, it essentially uses PWM. I remembered that the scantool we have has oscilloscope features that we never used. I learned how to use one in one of my classes last year, and I was excited to try it out. I connected it to the car, and kept getting this signal. This told us one crucial thing. The system the car uses upstream of the compressor very likely works. If it didn't work, it probably would not send this kind of heartbeat/test pulse. I unfortunately was not there when the car was actually repaired, but I am happy that I got to use my ECE skills out of the classroom.
{% include image-gallery.html images="/assets/calendar.jpg" height="350" %}
My parents moved to a new shop management platform and it included a calendar page to display the month's or week's appointments. They tasked me with replacing their whiteboard calendars with a digital one that used this. I measured the wall and calculated the largest TV that could me mounted in the calendar location on the wall. We bought a TV and I mounted it vertically. We used an old laptop that I disabled 'close lid to sleep' and enabled remote desktop and connected it to the TV. The calendar worked, but I did not like that the site truncated the events, cutting out a lot of useful details. There were no settings to stop this from happening. The details were there when I inspect element-ed the page, so I felt confident that I could put something together to make it display. I found a Chrome Extension that let you modify the style (CSS) of the pages you select. I used that and a few iterations of CSS style code generated by Gemini and it worked. 

{% include image-gallery.html images="/assets/bigvinylcutterplotter.jpg" height="350" %}
My dad and I got a very large vinyl cutter on a Facebook Marketplace run. There wasn't a simple open-source software for it that we could find, so we settled on one that worked with a one time fee (most were subscriptions). My dad preferred using his 10+ year old cutting/design program on his laptop, but that device was barely holding up and it does not run on Windows 11. I set up a Windows 7 VM in VirtualBox with quality-of-life file transfer features between the client machine and the host. The program runs well there and all of his asset files he has accumulated over the years were able to be imported.


{% include image-gallery.html images="/assets/outdoorphotoofmydadsvinylworkonacompanyswindowoldruralbuildingtreeinbackground.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->
A vinyl/sign side project that we put up for a local small business.

## Other

I set up static IPs for the office PCs and printer to stop intermittent issues with being able to print quotes for customers. 
I added a second wireless access point to make the signal within the shop and part of the lot better. I measured and terminated the CAT6 ethernet (patch cable) wire and helped plan out where the run would go from the office to the ceiling to another part of the shop. Because I added that infrastructure, I pretty easily wired up our main lot WIFI camera that often had lag spikes and drop outs, now it performs very smoothly. 
When I first bought my 3D printer, a lot of my first prints were little trinkets and display features for the shop, including figurines, piston/valve mechanical demos, and a tire depth tool.
I created a QR Code sign to allow customers to more easily connect to the network. The area has almost no cell service, especially within a concrete building.

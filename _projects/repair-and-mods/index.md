---
layout: post
title: Repair, Mods & Reverse Engineering
description: Some of the projects, big and small, that involve physical hardware. From repairing electrical appliances using a bit of robotics to helping out my relative and learning about RFID along the way.
card_image: /assets/photooflaptoptakenapartwithacableonthethunderboltchipconnectedtoausbtoflashitbecauseitdiedthinkpadt480s.jpg
order: 5
skills:
  - ESP32 Projects
  - Proxmark3 RFID Cloning
  - Console Hardware Modding
---

<!-- DETAILS FROM ANTHONY:
- Added USB-C to his new Nintendo 3DS XL while RETAINING the original charger (dual-power mod)
- Modded Switch, Wii U, Wii, 3DS: physical media → usable from storage; set up mods for his brother's games
- Relative's low-frequency RFID apartment key: she loses things, feared losing the key → Anthony used his Proxmark3 learning to clone her an emergency backup → saved her $230 vs. buying from the complex
- Dad's vinyl side-business: 65" Facebook Marketplace plotter; dad's old FlexiSign laptop dying → Anthony set up a Windows 7 VM with the old Flexi (shared clipboard, drag-between-desktops); dad designs in the VM, exports to a one-time-fee program that drives the plotter. Now cutting window signs for local businesses + dabbling in car tint
- Motorized trash can saga: stock = 6×AA, opens on motion, closes after 6s. Died one day → opened it → cheap internal connector to the main board had come undone → glued it. Tried adding adjustable open-time via capacitive touch through plastic — finicky, scrapped it ("called it a win that I fixed it"). Reassembling: DROPPED the board onto his power-supply lead (left on — "foolishly") → bright white flash + puff of smoke → board toast. Rebuilt with ESP32 → Home Assistant (easy code tweaks): 12V salvaged PSU → adjustable DC board → 9V to a motor driver; 12V → 5V buck → ESP32; 4 wires routed to the front of the housing. Two weeks of app-button open/close → added a TOF distance sensor (soldered in the kitchen onto the routed wires) → tuned. Now: no batteries, open as long as you want; mom's setting = 30s on sense, stays open while triggered
- Gym equipment mods: drilled the adjustable bench's steel to add a bolt → proper chest-supported row angle; converted a Gen-1 Bowflex (spaghetti strands) to Olympic free weights → lat pulldown machine; deadlift station from paint cans in a 2×2×2 ratchet-strapped config + pillow (noise) + coated aluminum rod wedged in the strap so plates can't roll off
- 3D-printed thick PLA pedals for the Peloton underside — "not that proud of this because I just found it on MakerWorld" (skip this one or keep as a footnote) -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- The 3DS USB-C mod: how did you keep both charging paths working without conflict?
- The RFID clone: what frequency/modulation was the key, and what did the Proxmark workflow look like?
- The trash can: what actually died when the board hit the live PSU lead? (Post-mortem.)
- The plotter VM: why Win7 + old Flexi instead of learning the new software? (Pragmatism story.) -->

<!-- MISSING / WOULD HELP:
- Photos: 3DS mod, trash can rebuild, plotter setup, gym mods
- The trash can saga deserves a video — it's your best "debugging under chaos" story
- Skip the Peloton pedals (your call — you said you're not proud of it) -->

## Motorized Trash Can Repair

My household has quite a lot of little gadgets here and there. One of which is a motorized trash can. Before this project I embarked on, we had it for about six months. It takes 6 AA batteries. It uses an infrared emitter and sensor to open it, and it has an open/close capacitive button to trigger longer-hold states. 

{% include image-gallery.html images="/assets/trashcanoriginalpcbdiagnosedfaultyconnector.jpg" height="350" %}
One day, the trash can stopped working. It acted as if it were dead, and new batteries did not bring it back to life. On a weekend I had more free time, I opened it up and found out that the long wire run had become disconnected from the flimsy connector. I glued it back in place, and for better or for worse, I decided to tackle a complaint my parents had about it. Both the infrared and the open button stayed open for a very short time, and I wanted to see if I could use a microcontroller to keep them open longer. I soldered an ESP32 to the 'Open' button part of the board. This did not work out well. It was bouncing and constantly triggering the open button, no matter what. I decided I was getting a bit too ambitious, so I desoldered it and started putting the trash can back together. I made quite a blunder when doing so and dropped the board on a lead of my power supply. I saw a bright white flash of light and a puff of smoke and knew the board was done for. Rather than fix it or order a replacement, I decided to remake the system and improve it. 

Using the various boards I had from previous AliExpress impulse-buys, I put together a system that could almost replace the old one. Starting from the wall, I used an old 12V power supply, connected to an LM2596 DC-DC converter tuned and hotglued to 9V to match the original voltage of the 6 AA array. I also connected a DC-DC converter to 5V to power an ESP32. The ESP32 and 9V were connected to a TB6612FNG Motor Driver board. I also connected four or five really long wires to the ESP32. I installed all of these components in an empty compartment next to where the batteries used to go. The ESP32 was flashed and connected to my ESPHome because I am most familiar with it, and I could easily modify and upload a new config over Wi-Fi. After a bit of tuning to the duration of the open and close states, I could manually trigger it to open and close from my server. I had to wait a little while for my VL53L0X Time-of-Flight sensor to arrive. Once it did, it was simple to integrate; I added and ran those long wires through the can. I had to modify the port where the old infrared sensor used to be, and I ended up drilling a hole through the plastic so the sensor has line of sight. One code modification later, and our trash can was working again, now wired and able to adjust the time it stays open. I didn't implement the buttons, and maybe, if the need arises, I will. It has worked flawlessly ever since.

Trash can repaired:
{% include youtube-video.html id="3jZYCb1aRBY" autoplay="false" %}

## RFID
My relative has a low-frequency RFID key for her apartment. She sometimes loses stuff and was worried about losing access to her apartment. I used my recent experiments with RFID technology and my Proxmark RFID tool to make her a backup for emergencies, so she didn't have to spend $230 to buy one from her complex. 


## Console Mods
### Software
On every console I have owned, I have done some software mod. My Switch, Wii U, Wii, 3DS, and more have custom firmware. It was mostly to back up physical media to the console's internal storage so I did not have to swap discs and cartridges. I also did it so my brother could play with mods.
### Hardware
I saw a video of someone adding USB-C to their Nintendo 3DS portable console. This was before I went to college for engineering, so I did not have much hardware experience. I used a rotary tool to cut out a pocket for a USB-C female board, giving it a place to sit in the console's housing. I struggled with soldering and got help from my dad when it wasn't working. At this point, I didn't know how to clean the soldering tip, use flux, tin the tip, or anything like that, so I was playing on hard mode. This experience was incredibly frustrating, but it gave me a lot of practice soldering through trial and error. Now, my system can charge off of either USB-C or the original proprietary charging port. 

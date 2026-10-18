---
layout: post
title: Repair, Mods & Reverse Engineering
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.
card_image: /assets/photooflaptoptakenapartwithacableonthethunderboltchipconnectedtoausbtoflashitbecauseitdiedthinkpadt480s.jpg
skills:
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

## Description

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat duis aute irure dolor in reprehenderit.

## Photos

{% include image-gallery.html images="/assets/photooflaptoptakenapartwithacableonthethunderboltchipconnectedtoausbtoflashitbecauseitdiedthinkpadt480s.jpg, /assets/robinairacmachinetorndownhighresphoto.jpg, /assets/trashcanoriginalpcbdiagnosedfaultyconnector.jpg, /assets/originalgarbagecanpcbundermicroscope.jpg, /assets/closeupoftrashcanesp32pictakentorecallwhichwiresgotowhichpinafterrouted.jpg, /assets/trashcanphotooftherawboardsiusedtoreplacetheoriginalone.jpg, /assets/trashcanlidnexttopowersupplytestingphoto.jpg" height="350" %}
<!-- To add more photos: append "/assets/filename" to the images list, separated by ", ". -->

## Write-up

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.

Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt, neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur adipisci velit.

At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.

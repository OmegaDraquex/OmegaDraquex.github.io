---
layout: post
title: Repair, Mods & Reverse Engineering
description:
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

<!-- TODO: 2-3 sentences in your words. -->

## Photos

<!-- TODO: drop photo files into _projects/repair-and-mods/, then embed:
{% include image-gallery.html images="photo1.jpg, photo2.jpg" height="400" %} -->

## Write-up

<!-- TODO: problem → approach → what you debugged → where it stands -->

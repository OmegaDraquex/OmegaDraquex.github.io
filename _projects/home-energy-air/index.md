---
layout: post
title: Home Energy Monitoring & Air Quality
description:
skills:
---

<!-- DETAILS FROM ANTHONY:
- PZEM modules ("pzem 4 or whatever") on ESP32s measuring the A/C units + tankless water heater; discounted TP-Link smart plugs on 120V appliances → showed the family what's actually driving the electric bill → informed the decision to move to a time-of-use (TOU) plan
- Home Assistant automation exploiting TOU + house occupancy: saves $50–90/month on the Duke Energy bill (both summer and winter schedules) while keeping sleep/weekend comfort
- 3D-printed ERV (Feb): 2× harvested 80mm server fans; 3D-modeled two-channel system with crisscrossed corrugated-plastic squares at the core; pull-push configuration — HAS photos + thermal camera images, maybe Aranet 4 readings from that time
- Later REPLACED the ERV with an HA automation: toggles the Honeywell thermostat's circulate mode, but only at night + only if he's home + only if his room reads above 1000 on the Aranet (CO2)
- 3D printer: outdoor active exhaust for engineering plastics; VOC sensor → ESP32 → Home Assistant mounted near the printer, monitoring before/after the exhaust install
- $30 AliExpress particle sensor + ESP32 → Home Assistant particle sensor → validated the Costco Winix purifier ("turns out, it works extraordinarily")
- Circadian wake-up automation in HA: lots of morning light (some days are spent in his room a long time) -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- $50–90/month savings — how did you measure that? (Before/after bills? Normalized for weather?)
- How did you validate the PZEM readings were accurate?
- ERV: did the thermal images show actual heat recovery? What was the effectiveness, roughly?
- Why replace the ERV with the thermostat automation — what did the data say?
- The Winix validation: what did the particle numbers look like before/after? -->

<!-- MISSING / WOULD HELP:
- The thermal camera images + Aranet readings — these are GOLD for a portfolio, dig them up
- Before/after electricity bill numbers
- Photos: PZEM install, ERV build, printer exhaust, sensor placements -->

## Description

<!-- TODO: 2-3 sentences in your words. -->

## Photos

<!-- TODO: drop photo files into _projects/home-energy-air/, then embed:
{% include image-gallery.html images="photo1.jpg, photo2.jpg" height="400" %} -->

## Write-up

<!-- TODO: problem → approach → what the data showed → where it stands -->

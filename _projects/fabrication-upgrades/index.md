---
layout: post
title: Printer & Fabrication Upgrades
description:
skills:
---

<!-- DETAILS FROM ANTHONY:
- 3D printer noise/vibration: gym foam tile + concrete slab underneath → less noise for others in the house + "dramatically" less shaking
- Built a TPU feed-assist module, direct-connected to his cheap Sunlu filament dryer (for printing flexibles reliably)
- MakerSpace: fixed the mylar roller on the NEWER pick-and-place (the roller sits on the motor shaft and pulls the mylar tape; it was slipping) — diagnosed drive-shaft slippage, CAD-modeled a replacement hub in SolidWorks, printed it in TPU
- Vibe-coded a Python GUI for the pick-and-place workflow: takes CSV export from the OLD Neoden → uses fiducial + SMD1 locations to correct all component placements (custom solution because the Neoden CSV has a weird format with varying column counts that broke existing tools); also converts KiCad placement exports into the machine's expected format
- The validation loop: KiCad export → his program → machine → locate actual fiducial/component-1 addresses → export back → his program → machine again — "testing that and having that work was awesome"
- Now extending it to the newer machine; his boss thinks it's cool and wants a demo + new documentation for the less-manual workflow -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- The slab: how much did vibration actually drop? (Measured, or just felt?)
- What exactly was weird about the Neoden CSV, and why did existing tools choke on it?
- How does the fiducial correction math work at a high level?
- Your boss wants docs — what does the new workflow look like end to end? -->

<!-- MISSING / WOULD HELP:
- Photos: printer on the slab, the TPU feed assist, the fixed roller
- Screenshots of the Python GUI
- Link to the code (if public) -->

## Description

<!-- TODO: 2-3 sentences in your words. -->

## Photos

<!-- TODO: drop photo files into _projects/fabrication-upgrades/, then embed:
{% include image-gallery.html images="photo1.jpg, photo2.jpg" height="400" %} -->

## Write-up

<!-- TODO: problem → approach → what you debugged → where it stands -->

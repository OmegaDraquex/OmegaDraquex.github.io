---
layout: post
title: Printer & Fabrication Upgrades
description: A collection of various projects that involve maker's equipment, like my 3D Printer and other equipment I have worked on.
card_image: /assets/digitalcalipersmeasuringneodengearrod.jpg
order: 3
skills:
  - Python GUI Development
  - Pick-and-Place Workflow Automation
  - SMT Assembly
  - SolidWorks CAD
  - FDM 3D Printing
  - TPU Flexible Printing
  - Mechanical Troubleshooting
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

A collection of various projects that involve maker's equipment, like my 3D Printer and other equipment I have worked on.

## Photos

This past summer, I ran into a few projects I could not do because I had a 3D printer without an enclosure. I ended up caving and bought a P2S. One of the things I immediately noticed was that on the old hollow wooden table I had, it would shake (vibrations) and sway like crazy. This would reverberate or resonate and would be noticeably noisy to my family. I came across a solution online from CNC Kitchen where he put his printer on a concrete slab from the hardware store and put the slab on top of a flexible material and put that on the desk. I tried it and it worked spectacularly. It eliminated the noise that would travel rooms and floors. It made the machine sound much quieter, and the print quality improved somewhat. Since then, I have added active exhaust to the outdoors and a VOC sensor, and particle sensor connected to HomeAssistant to be completely sure that I am not exposing my family to something irritating or dangerous. I also added the TPU Feed Module by Bambu Lab, but I have not had much opportunity to really see the difference between that and the standard way of using TPU.

{% include image-gallery.html images="/assets/P2SonConcreteandGymsquare.jpg" height="350" %}

While I was being trained on the Pick and Place Machine for my new ECE Makerspace job, a different student worker discussed an issue with one of the machines that he was having. The machine was failing to pull back the mylar peel sufficiently. My boss is a very busy man, and the next shift I had, I took a look at the machine. I ran the machine over and over again, trying to understand how it actually worked. I realized that the bottom gears were supposed to be way more snug on the motor shaft. I also realized that the gear has screws on it. I took a gear home to study it that night. I found out that it has a small flexible removable insert. I measured it with calipers and recreated it in SOLIDWORKS, except with a smaller diameter. I loaded (regrettably undried) TPU into my 3D Printer, set it to print a few dozen, and went to bed.

{% include image-gallery.html images="/assets/neodennewgearsolidworks.png" height="350" %}

This was what the gear looked like when taken apart:

{% include image-gallery.html images="/assets/neodenbrokengear.jpg" height="350" %}

This is what the gear looked like when I added my custom part:

{% include image-gallery.html images="/assets/insideneodenfixedgearafter.jpg" height="350" %}

This is the rail of gears. Quite surprisingly, this has worked and the machine now pulled the mylar with ease. Very rarely does a fix work the first time, so I will keep an eye on this.

{% include image-gallery.html images="/assets/neodensideofmachineallthegearsBrollshot.jpg" height="350" %}

Printer Picture:

{% include image-gallery.html images="/assets/justapicitookofthenewerneodenyy1.jpg" height="350" %}

This the program that the older pick and place machine uses. It is very basic, and by default you would have to enter each location value manually or go through a convoluted process to import it. I tested out the new Gemini 4 Argon Task mode to create a python program with a gui that could take a weirdly formatted csv export from the machine and adjust all of the component positions based on the location of the feducials. I iterated and made it able to convert a CSV export from KiCad to the CSV format the NeoDen expects.

{% include image-gallery.html images="/assets/olderneodenforpythonscriptprojectphotooflowrescomputermonitoroldoldmachinepicture.jpg" height="350" %}

My new phone has qi2 charging support. This is what some people call MagSafe: wireless inductive charging with a magnet to optimize charge rate and reduce waste heat production. I saw how expensive qi2 charging stands were on Amazon, so I bought good-enough anker standalones, got my calipers out, and got to work. I also wanted a bit of passive cooling, just because keeping your phone cool can potentially extend the length of your battery capacity/life.

{% include image-gallery.html images="/assets/personalprojectqi2standCADsolidworksscreenshot.png" height="350" %}

This is the final product. The qi2 charger pushes into the slot and has just enough friction to keep it in place but let it move slightly to come meet the phone a bit. Later on, I hotglued the fan to the stand because it is unshielded, would fall down and make a terrifying noise.

{% include image-gallery.html images="/assets/personalprojectqi2-3dprinted-abs-chargerstandwitha120mmnoctuafanmountedbehinditforcooling.jpg" height="350" %}

I wanted to test out the free-to-use tool Reality Capture from Epic Games. In the past, when I used 3D scanning on iPhone and Android, I was always met with restrictions and paywalls, so I decided to trade cost for convenience. We took a video of me standing still in the back deck and I imported the video to my computer. It took a lot of trial and error to get the output to be this good. A lot of processing in RealityScan and even more processing in blender. The file has a texture map, and I want to try out the full color resin printing at some point. I am happy with this little figurine though.

{% include image-gallery.html images="/assets/cutephotoofa3dprintedmulticolorfigurineofmenexttoandthesameheightasaAAbattery.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->


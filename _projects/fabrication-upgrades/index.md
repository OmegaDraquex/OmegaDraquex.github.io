---
layout: post
title: Printer & Fabrication Upgrades
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.
card_image: /assets/digitalcalipersmeasuringneodengearrod.jpg
order: 3
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

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat duis aute irure dolor in reprehenderit.

## Photos

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/P2SonConcreteandGymsquare.jpg" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/neodennewgearsolidworks.png" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/neodenbrokengear.jpg" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/insideneodenfixedgearafter.jpg" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/neodensideofmachineallthegearsBrollshot.jpg" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/justapicitookofthenewerneodenyy1.jpg" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/olderneodenforpythonscriptprojectphotooflowrescomputermonitoroldoldmachinepicture.jpg" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/personalprojectqi2standCADsolidworksscreenshot.png" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/personalprojectqi2-3dprinted-abs-chargerstandwitha120mmnoctuafanmountedbehinditforcooling.jpg" height="350" %}

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/cutephotoofa3dprintedmulticolorfigurineofmenexttoandthesameheightasaAAbattery.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->

## Write-up

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.

Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt, neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur adipisci velit.

At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.

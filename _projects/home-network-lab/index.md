---
layout: post
title: Home Network & Self-Hosted Lab
description: Using my education in Information Technology around the house and at work. 
card_image: /assets/u6proontheceiling.jpg
order: 9
skills:
  - MikroTik RouterOS Administration
  - UniFi AP Deployment
  - Cable Termination
  - WireGuard VPN
  - Cloudflare Tunnels
  - Virtualized Home Lab
  - Self-Hosted Services
---

<!-- DETAILS FROM ANTHONY:
- Was on Spectrum cable: modem/router prone to slowdowns, minute-long dropouts, bad radio, poor coverage
- Swapped to: Netgear modem + MikroTik router (programmed the firewall himself; optimized over time — fasttrack, cake for a while, then REMOVED cake when he realized it was causing issues; WireGuard VPN; ad lists) + UniFi U6 Pro + older routers as secondary wired APs + patch cables he measured and crimped himself
- T-Mobile fiber: he planned the modem placement (least disturbance, clean swap — NOT where the old modem was); did the whole cutover before most people woke up
- CGNAT on fiber broke his personal projects → bought his own domain + Cloudflare tunnels
- Headless VMs replacing Raspberry Pis ("the SD card killer"): one VM for Home Assistant, one Debian VM for servers + personal website
- Personal website hosts: Jellyfin for the family, a podcast feed URL for recorded content, Home Assistant, audiobooks, Calibre, "various other projects that I have not kept up with lol" -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- Why MikroTik over a consumer mesh system? What did the cake/fasttrack experiment teach you?
- How do Cloudflare tunnels solve CGNAT, and what are the tradeoffs vs. port forwarding?
- What was actually killing the Pi SD cards, and why are VMs better here?
- This is a lot of infrastructure for a house — what broke that started it all? (Story hook.) -->

<!-- MISSING / WOULD HELP:
- Network diagram (even a hand-sketched photo)
- Photos of the setup (modem/router/AP placement)
- Your domain name (optional — only if you want it public) -->

  I have always been a person who wanted to play with technology and see what it could do. I would watch a lot of nerdy computer videos on YouTube and find it all so fascinating. In middle school, I got a Raspberry Pi for my birthday and learned how to use Linux and the shell command line, years before my first Linux class. I would spin up servers like Pi-Hole DNS AD Block and make my family deal with the buggy repercussions. I learned that they highly value a fast, stable connection, so I made sure my future network projects aligned with that. I found that the original Spectrum Cable Modem Router caused a lot of slowdowns and intermittent disconnects. 

  For Christmas that year, I asked for a MikroTik Router. It was $60, way less than many high end consumer ones, and it required a lot more manual set up, which I liked. I set up the firewall list and the flow control. I set up a lot of optional features, like one that blocked ads on the network in a way that is way more capable than the raspberry pi. I used it to spin up web servers so that I could access stuff away from home, like Jellyfin to watch media, calibre to add books to my kindle, Home Assistant to monitor and control automations from my phone, and other projects that I have not kept up with. I moved my server system from my Raspberry Pi to two different VirtualBox VMs because the rapsberry pi wore out an expensive SD card and it would be terribly inconvenient to lose my systems again. Later, we got a Unifi U6 Pro Access point that I helped install and programmed. I enjoyed having non-consumer grade high end hardware for the network in the house. I also helped do wired runs through the crawlspaces so that each my dad any my workstations would have reliable and fast wired connections.

  I had to retire the MikroTik router sadly when we moved from Spectrum to T-Mobile Fiber. I enjoy the speeds, latency, and reliability of fiber, but it requires talking to a technician to allow you to use your own routing equipment, and I wouldn't want to put my family in the position where I use my own and it ends up having an issue with their systems that the stock configuration would not and not be able to easily switch back.

  Now I use Cloudflare for my DNS and Cloudflare tunnels to get past the ISP's CGNAT (double nat which makes setting up websites the normal way hard). Previously I used a free DuckDNS.
{% include image-gallery.html images="/assets/oldphotoofmewithwaytoolongofhaironareallytallplatforminstallinganAPattheautoshop.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->
This is when I put up a old router with custom firmware up at my family automotive shop to act as a second AP to boost signal and reduce repair video and schematic look up buffering and slowdowns. I needed a haircut desperately.



---
layout: post
title: Home Network & Self-Hosted Lab
description: Using my Information Technology education both at home and at work.
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

  I have always been a person who wanted to play with technology and see what it could do. I would watch a lot of nerdy computer videos on YouTube and find it all so fascinating. In middle school, I got a Raspberry Pi for my birthday and learned how to use Linux and the shell command line, years before my first Linux class. I would spin up servers like Pi-Hole DNS AD Block and make my family deal with the buggy repercussions. I learned that they highly value a fast, stable connection, so I made sure my future network projects aligned with that. I found that the original Spectrum Cable Modem Router caused frequent slowdowns and intermittent disconnects. 

  For Christmas that year, I asked for a MikroTik Router. It was $60, way less than many high-end consumer ones, and it required a lot more manual setup, which I liked. I set up the firewall list and the flow control. I set up a lot of optional features, like one that blocked ads on the network in a way that is way more capable than the Raspberry Pi. I used it to spin up web servers so I could access stuff from home, like Jellyfin to watch media, Calibre to add books to my Kindle, Home Assistant to monitor and control automations from my phone, and other projects I haven't kept up with. I moved my server system from my Raspberry Pi to two different VirtualBox VMs because the Raspberry Pi wore out an expensive SD card, and it would be terribly inconvenient to lose my systems again. Later, we got a UniFi U6 Pro Access point that I helped install and program. I enjoyed having non-consumer-grade, high-end network hardware in the house. I also helped run wires through the crawlspaces so that my dad and my workstations would have reliable, fast wired connections.

  I had to retire the MikroTik router sadly when we moved from Spectrum to T-Mobile Fiber. I enjoy the speeds, latency, and reliability of fiber. Still, it requires talking to a technician to use your own routing equipment. I want to avoid putting my family in a position where I use my own, which causes issues with their systems that the stock configuration wouldn't, and where I can't easily switch back.

  Now I use Cloudflare for my DNS and Cloudflare tunnels to get past my ISP's CGNAT (a double NAT, which makes setting up websites the normal way hard). Previously I used a free DuckDNS.
{% include image-gallery.html images="/assets/oldphotoofmewithwaytoolongofhaironareallytallplatforminstallinganAPattheautoshop.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->
This is when I put up an old router with custom firmware up at my family automotive shop to act as a second AP to boost signal and reduce repair video and schematic lookup buffering and slowdowns. I needed a haircut desperately.


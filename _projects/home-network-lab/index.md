---
layout: post
title: Home Network & Self-Hosted Lab
description:
skills:
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

## Description

<!-- TODO: 2-3 sentences in your words. -->

## Photos

{% include image-gallery.html images="/assets/u6proontheceiling.jpg, /assets/oldphotoofmewithwaytoolongofhaironareallytallplatforminstallinganAPattheautoshop.jpg" height="400" %}
<!-- To add more photos: append "/assets/filename" to the images list, separated by ", ". -->

## Write-up

<!-- TODO: problem → approach → what you debugged → where it stands -->

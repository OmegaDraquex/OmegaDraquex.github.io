---
layout: post
title: Home Network & Self-Hosted Lab
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.
card_image: /assets/u6proontheceiling.jpg
order: 9
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

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat duis aute irure dolor in reprehenderit.

## Photos

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua enim ad minim veniam quis nostrud.

{% include image-gallery.html images="/assets/oldphotoofmewithwaytoolongofhaironareallytallplatforminstallinganAPattheautoshop.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->

## Write-up

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.

Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt, neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur adipisci velit.

At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.

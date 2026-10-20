---
layout: post
title: Software Tinkering
description: An assortment of my various experiments using stuff on the computer.
card_image: /assets/hirescloseupofmmwavesensorconnectedtoverytinyesp32inmyhand.jpg
order: 10
skills:
  - LC-3 Assembly
  - C Programming
  - Local LLM/AI Deployment
---

<!-- DETAILS FROM ANTHONY:
- ECE 109: tic-tac-toe game written in LC-3 assembly — NO AI used, "I'm proud of that"
- ECE 209: deterministic pseudo-random card shuffler (+ other 209 projects) — NO AI used, "proud"
- Senior year of HS: helped set up a computer lab at his community college with peers — deployed the computers, recorded MAC addresses, connected everything, set up network boot (FOG) because professors wanted easier imaging
- Early adopter pattern: "when new tech comes out, I try it first hand to understand its utility, and later I rely on my artist/humanities friends and family to give me a more cultural understanding of it"
  - ChatGPT before it hit 1M users; Stable Diffusion on his PC before 1.5; early local LLMs (set one up remotely while on a family trip; ran one on his personal website with web-search tools)
- 24GHz mmWave presence sensor in his room → lights on/off without touching the switch
- Vibe-coded an app using FastWhisper (CLI) to transcribe videos to text ("less impressive now — a million people have done this")
- "Experimented with portable programs, and played Dolphin on my community college's kiosk — only including this because the image I have is quite funny and demonstrates that I am always experimenting as play (I was on good terms with the head of cyber security and the IT instructors)"
- Does ALL the tech stuff in the house + a lot of the building/moving stuff -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- The LC-3 tic-tac-toe: what was the hardest part of writing a game in assembly? (This is a GREAT interview story — keep it.)
- "No AI used and I'm proud" — say more. Why does that matter to you?
- The FOG imaging setup: how many machines, and what broke?
- The early-adopter pattern (tech first, cultural understanding via friends/family) is a genuinely interesting worldview — consider putting a version of it on your About section. -->

<!-- MISSING / WOULD HELP:
- The Dolphin-on-kiosk photo (you said it's funny — include it, it shows playfulness)
- Screenshots of the LC-3 game running
- Anything visual for the mmWave setup -->

## Description

Trying out videogame Mods and growing up with a tinkerer of a father made me very curious and interested in trying out new software throughout the years. From trying out Seth Bling's Mar/IO when I was 10 to watch my computer learn how to play Mario, to getting my degree in IT, to my current journey as a Computer Engineering student, I have always had an obsession with seeing what can be done with technology.

## Photos



{% include image-gallery.html images="/assets/kioskfunny.jpg" height="350" %}
Back when I was in my Early College high school, I was playing around with a tool that makes programs portable. I found out that the Dolphin Wii emulator worked with this, and I thought it would make my friends laugh to see Mario running on a printer kiosk in the lounge. It was a fun time. I got a bluetooth dongle and used a old usb hub to be able to connect all of my USB devices to it and play with actualy Wii Remotes. I do not recommend others do something like this, please respect institutional property and use it as directed. 



{% include image-gallery.html images="/assets/lc3.jpg" height="350" %}
My final project in my first ECE class. It was to write a tic tac toe game in LC3 (actual assembly). I found this so much fun to do and being in a programming flow state felt really good. Nowadays, programming is taught as a piece of a project that can be delegated to AI, but for this project I did not use it, and I am very proud of that. 



{% include image-gallery.html images="/assets/mmwavesensormountedonwallwithpainterstapeina3dprintedhousingthatlookslikeasecuritycamuglyandonlycouldbeinaroomthatnowomanwouldapproveof.jpg" height="350" %}
This eyesore was a result of an AliExpress impulse buy. I was recommended cheap mmWave presence detectors. I wired one up to an ESP32, flashed it to ESPHome and connected it to my HomeAssistant. I used it in an automation to turn my bedroom lights on and off depending on me being in there. With some tuning, it worked even if I did not move. I did have to keep the fans off, and it stopped working because the painter's tape gave way and I lost interest in keeping it up.
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->

## Others

In my C programming class, a project was a deterministic pseudo-random card shuffler. The professor provided the code that generates the randomness, we had to make the program draw a user-specified number of cards, swap out a user-specified number of cards, and shuffle them. I also took pride in this class that I did not use generative AI to write any of my code. 

In my Senior year of high school, my professor had split the class into a few different teams to help out the deployment of a new computer lab and better management capabilities of the labs. My team's task was to record the Mac Address of each computer and laptop. I used a USB Arduino Rubber Ducky to enter the commands into the command prompt for a few computers. In hindsight, I could have used it to open run and do more of the manual process.

I like to try out new software and technology products, especially if they are free. I tried out Project Stream by Google in 2018 before they released Stadia. I tried out Stable Diffusion before version 1.5 came out (generating ai images directly on my PC before the space got overwhelming and controversial), I tried out ChatGPT after hearing about it on a tech podcast, like the week it came out, and introduced it to my friends. I tried out Obsidian MD (very popular notes app) in 2020 shortly after it was accessible to the public. I tried early versions of the latest prealpha versions of Anki's spaced repetition algorithm. I tried out Google's Bard before it became Gemini. I tried out Bing Chat when it came out, before it became Copilot. I tried out local LLMs before it got easy to deploy them. I have changed my view on generative AI through many conversations with my artist/teacher friends and family members. I am not online or on social media much, so it took me longer to realize the negative implications that they entail.

---
layout: post
title: HP Prime G2 FPGA Video Interface
description: A solution in search for a problem. I bought a calculator, found a cool FPGA project online for it, wanted to try it and iterate on it.
card_image: /assets/Tang9knocalculatorhdmidemo.jpg
order: 1
skills:
  - Verilog HDL
  - Gowin Tang Nano 9K FPGA
---

<!-- DETAILS FROM ANTHONY (Oct 2026, in progress):
- HP Prime G2 calculator → tap the LCD bus → decode in FPGA → HDMI out → Python capture on PC
- 13.3 MHz serial-RGB LCD bus; 320x240 RGB565 frames
- Tang Nano 9K (Gowin GW1NR-9); PSRAM framebuffer (on-chip BSRAM too small for a 150KB frame); TMDS encoder → 640x480@60 HDMI (pixel-doubled)
- prime_pixel.v decoder written from scratch from the protocol spec — passed full sim: 76,800 pixels, 0 value/coordinate errors at real Prime timing
- Open-source Gowin EDA toolchain (yosys + nextpnr-gowin)
- Status: decoder done in sim; frame buffer + HDMI output path in progress; board bring-up next -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- Why tap the LCD bus instead of using the calculator's USB or a camera pointed at the screen?
- How did you reverse-engineer the LCD protocol? (logic analyzer? docs?)
- What was the hardest RTL bug, and how did you find it?
- Why PSRAM instead of on-chip BRAM?
- How do you verify the HDMI output is pixel-correct? -->

<!-- MISSING / WOULD HELP:
- Photos: tap wiring on the calculator flex, Tang Nano 9K setup, HDMI output on a monitor
- Sim waveform screenshots
- Is the repo public? Link it.
- 60-90s demo video: calculator screen appearing on the monitor via your pipeline -->

## Photos

<!-- No additional photos yet — the highlight image at the top of the page is the only one so far. To add more: copy a caption + image-gallery block from another project page and swap in your "/assets/filename". -->

## Write-up
{% include image-gallery.html images="/assets/hp1.jpg" height="350" %}
  I bought a HP Prime G2 calculator because I saw that it could do a particular kind of integration that none of my other calculators could do. I had fun playing with it and I wanted to learn more. While I was at the airport waiting to board a plane to visit my partner, I came across a [very cool write up](https://davidigreen.com/blog/reverse-engineering-the-hp-prime-lcd-and-replacing-it-with-an-ips-panel)
 by David, an engineer who reverse engineered the LCD on the screen. He made his project available on GitHub and his write up on his site is beautiful. I suggest you read it. I've always thought FPGAs were cool but I would not have classwork with one until next semester, so I kept this in the back of my mind.
{% include image-gallery.html images="/assets/hp2.jpg" height="350" %}
   I didn't think much of it until a few days later. My partner, an MIT Undergrad, whom I was visiting recieved an incredible summer internship offer in Cambridge. I am so proud of her. She is so incredible. She inspires me to work hard everyday. It was already my goal to get an internship this summer and this made me really invested in getting one in Massachusetts, so we could have a really awesome summer together. I decided that before I apply, I wanted to get one more targeted project under my belt. I decided to try to replicate and iterate on the calculator project I heard about prior.
{% include image-gallery.html images="/assets/hp3.jpg" height="350" %}
   I ordered a Tang Nano 9K. The author used a 20K and maybe I should have gone with that, but I figured that I could probably get past the restrictions that this device has. I started with running some demo HDMI code from online for the 9K to test if my board worked. The test pattern displayed on the screen once I ruled out a faulty HDMI cable. Next, I did an exercise where I tried to recreate one of the .v modules from scratch. I did this as a challenge to get more familiar with Verilog. This is really the only code I contributed. I had an llm tell me kinda how it worked if it was written in C, and told me the syntax of Verilog. Through a few iterations, I rewrote the module. It passed the python script that tested the module. I'll admit, most of the Verilog in this project has been a product of David's work and Gemini 4 Argon. I just wanted to get a taste of Verilog, knowing that I would be taking the Verilog class next semester and wanting to get the project done in a reasonable amount of time. 
{% include image-gallery.html images="/assets/hp4.jpg" height="350" %}
   Once it wrote something that might have worked on my 9K and passed the test cases, I got to soldering. I used 30AWG wire from the ECE Makerspace, and embarked on one of the most tedious and underprepared processes I have ever embarked on. I had 13 wires to solder on the very tiny connector pins on my calculator. I only had a slightly more narrow conical soldering iron tip head than what is stock, thick .8mm solder wire, and no experience with desoldering or wicking. It went about as well as you could expect.
{% include image-gallery.html images="/assets/hp5.jpg" height="350" %}
   I used my microscope to actually see where I was working. This was so challenging, My hands needed to be steady, the pins had to be very saturated with flux, the wires had to be tinned since my solder was too thick, but not too tinned because that would bridge pins. I soldered about 5 pins after a few hours of attempts and them falling off dozens of times. I decided (foolishly) to hot glue them in place so they would not be disturbed by me working on the other 8. This decision cost me so much time and effort. The hot glue created a residue everywhere. It made it impossible to keep working. Once I found this out, I carefuly removed the hot glue blob, which expectedly removed all the wires I soldered on. I cleaned the board with IPA and a soft bristled tooth brush. I noticed under the microscope that a few pins were bridged with solder. I tried for two hours to remove the solder with a wick and a lot of flux. I removed most of it, but most is infinitely insufficient. I developed a headache and went to bed.
{% include image-gallery.html images="/assets/hp6.jpg" height="350" %}
   The next day, during breakfast, I watched a few [videos](https://youtu.be/0qcBN-knx7s?si=CusQIApNLXYj4-N6) on YouTube about desoldering small SMD pins. I went back to the workbench and tried again. I switched to a larger iron tip because that was what others online were doing. It was a long process that took multiple runs, but the continuous progress I was making helped keep my spirits up. I also used a sewing needle to rip off a very very small solder wick fiber that was bridging two pins. It barely showed up on the screen. 
{% include image-gallery.html images="/assets/hp7.jpg" height="350" %}
   I was back to soldering pins on. My technique I ended up using is as follows: I used tweezers to hold the wire, about 5 mm away from the end. This made holding the wire steady easier and I burned my hands less. I tinned the tip of the wire with a minimal amount of solder. I cleaned the tip thoroughly, tinned it, and wiped it again in a brass sponge. For every pin I attempted, I put a blob of flux paste. This helped keep the wire from moving, like a temporary glue. I did have to redo wires that came undone a few times, but eventually, I successfully got a connection from the pins of the calculator to the FPGA.
{% include image-gallery.html images="/assets/hp8.jpg" height="350" %}
   The screen was blank. This is to be expected. I did a few troubleshooting steps to test if it was my solder job, but those came out clear. It was the Verilog that Argon made. I had it do a few rounds of troubleshooting and eventually, it had an output that displayed . . . something to the screen. It was a repeating pattern of small vertical bars on the left edge of the screen. What was promising is that if I navigated the calculator to a more colorful screen, these bars became more colorful. It was getting late, and I maxed out my Gemini Pro family plan 5 HR utilization, so I went to bed.
{% include image-gallery.html images="/assets/hp9.jpg" height="350" %}
   I had Gemini do more troubleshooting and for the most part it was nothing. It seemed like progress was going backwards. It was changing things to do with clocks and timing and memory and such. Things I don't really understand in Verilog just yet. 
{% include image-gallery.html images="/assets/hp10.jpg" height="350" %}
   I was working on this write up when I noticed that the wall opposite of me was glowing white. My monitor was outputting something. I was so shocked. This garbled, repeated mess of pixels was the second most exciting thing I have seen during this project, behind actually getting the soldering done. My break is coming to an end, so the second half of my project, connecting this video output to a display capture and being able to use an LLM to control the calculator for demo and tutorial purposes, will come later.
{% include image-gallery.html images="/assets/hp11.jpg" height="350" %}
{% include image-gallery.html images="/assets/hp12.jpg" height="350" %}

<!-- TODO: {% include youtube-video.html id="VIDEO_ID_HERE" autoplay="false" %} -->

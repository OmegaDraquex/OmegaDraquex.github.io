---
layout: post
title: Synchronous Digital State Machine Controller
description: My Intro to Logic Design Final Project. A Breadboard State Machine for a simple vending machine controller.
card_image: /assets/FSMbreadboardfinalprojectona3dprintedholderthatholdstheboardandtheanalogdiscovery.jpg
order: 7
skills:
  - Digital Logic Design
  - Karnaugh-Map Minimization
  - 74-Series TTL
  - Breadboard Prototyping
---

<!-- DETAILS FROM ANTHONY (ECE 212, done):
- 4-state synchronous Mealy state machine (vending-machine controller), designed in Logisim Evolution
- Used "a different tool" to significantly reduce gate count by relying on multiplexers instead of discrete gates
- Breadboarded with 74-series TTL + D flip-flops; K-map minimization for state-transition equations
- Resolved open-collector signal float with external pull-up resistor networks
- Verified with Analog Discovery 3 (logic analyzer): 1000 randomized-input simulated test, scored 1000/1000 -->

<!-- RECRUITER QUESTIONS TO PRE-ANSWER:
- Muxes vs. discrete gates: what was the gate count before and after?
- How did you generate the 1000 random vectors, and what would a failure have looked like?
- What did the open-collector float issue teach you about real hardware vs. simulation? -->

<!-- MISSING / WOULD HELP:
- Name "the different tool" used for gate reduction
- Before/after gate counts
- Photos: the breadboard, AD3 captures, K-maps/schematics -->

## Description

My Intro to Logic Design Final Project. A Breadboard State Machine for a simple vending machine controller.

## Photos



{% include image-gallery.html images="/assets/fsmphotoofthewaveformsdiligent1000randomizedinputtestscripttestpass1000outof1000.jpg" height="350" %}
<!-- To add more photos: copy a caption + image-gallery block above and swap in your "/assets/filename". -->
The benchmark that determines if the project has worked or not, running on Digilent WaveForms

## Write-up

This was the ultimate test of whether we could interpret operational requirements, convert them into states in a big spreadsheet, turn them into simplified boolean expressions, and then optimize them to run on as few TTL gates as possible. That constraint was imposed by a desire to do as little wiring as needed.

Turning the requirements into a spreadsheet was a pretty standard task. Once the states and inputs were identified and the impossible states were X (don't care), filling in the rest was trivial. I decided to use Logisim Evolution to find the minterms using their combinational analysis feature. Partially to reduce the chances of making a tedious mistake, but mostly because I like trying out new programs. Once the minterms were found for the next state and outputs, I had it build the circuits and connected them to the necessary memory elements (D flip-flops). The circuit seemed quite cumbersome, and I knew that I had MUXes that could be used to cut down on gate count. I used OpenAI's ChatGPT LLM to check for any low-hanging fruit ways to use the TTL gates I had in my kit to do this. It proposed a circuit scheme in tabular form. I manually built that scheme in Logisim to test it. It worked well in the simulation, so I built it on my breadboard. I ran into a lot of issues, however. The simple ones were wiring mistakes where I put some wire ends in the wrong slots. The more complex ones involved troubleshooting a faulty breadboard. The retaining metal on some rows was not making good contact with the wires I had. I ended up redoing the project on a new breadboard, scrapping a custom battery harness once I found out my Analog Discovery 3 could supply the necessary power for the circuit, and making/printing a project holder to protect my delicate project. On demo day, my project passed the 1000 randomized test cases, and I went home feeling triumphant.

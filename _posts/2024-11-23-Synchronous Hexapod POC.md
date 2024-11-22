---
title: "Hexapod POC"
description: Design, Implementation, and Testing
date: 2024-11-20
categories: [Projects, Robotics]
tags: [Hexapod, robotics]
author: "Bryan Vas"
image: assets/images/Hexapod_1.0/Hexapod_POC.jpeg # Feature image for the post
---

# Synchronized Hexapod: Proof of Concept

This project has been an immensely rewarding experience, teaching me essential skills like curve parametrization, 3D transformations, and inverse kinematics. 

An additional highlight was developing an NRF24-based transmitter and receiver, showcasing the versatility of wireless systems.

## Demonstration Video

Watch the Heexapod in action:

<div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden;">
  <iframe src="https://www.youtube.com/embed/nqDUA7U9GqU" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen 
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>


## Project Overview

This was a project testing the limits of a simple (single core) microcontroller. Some cool features implemented in this Hexaod are
- Roll, and pitch control of the hull.
- Default body height adjustment.
- Complete 2D walk velocity vector control.
- Ability to switch between different walking patterns(gaits).
- Maximum step size, and height control.
- Wirerless Communication with the operator

This project combines mechanical design, and software algorithms, to achieve full autonomy.

## Technical Details

### Hardware
- **Body and Legs:** Custom-3D printed from PLA.
- **Controller:** Arduino Nano.
- **Servos:** MG995 Servo (11 Kg-cm torque)(180deg max)

### Software
- **Programming Language:** Embedded C
- **Autonomy:** Wireless Teleoperation, Using Shock-Burst Protocol, and NRF24L01 RF Module.

## Gallery

<div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 20px; align-items: center; justify-items: center;">
  <div>
    <img src="assets/images/Hexapod_1.0/Hexapod_POC.jpeg" alt="Rover Prototype" style="width: 100%; max-width: 300px;">
    <p style="text-align: center; margin-top: 10px;">Figure 1: POC</p>
  </div>
  <div>
    <img src="assets/images/Hexapod_1.0/hexapod_transmitter.jpeg" alt="Remote Control" style="width: 100%; max-width: 300px;">
    <p style="text-align: center; margin-top: 10px;">Figure 2: Remote Control</p>
  </div>
  <div>
    <img src="assets/images/Hexapod_1.0/abd7d4ec-66d1-4993-861a-9b7464e9a3ce.jpeg" alt="Stored Data" style="width: 100%; max-width: 300px;">
    <p style="text-align: center; margin-top: 10px;">Figure 3: Insides</p>
  </div>
  <div>
    <iframe width="100%" height="auto" style="max-width: 300px; aspect-ratio: 4/3;" 
    src="https://www.youtube.com/embed/iwAWR1MDBaE?si=iPdtvmGcoOsi6Q_h" 
    frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen></iframe>
    <p style="text-align: center; margin-top: 10px;">Figure 4: Test Setup</p>
  </div>
</div>



## Source Code

The complete codebase and documentation are available on [GitHub](https://github.com/bryanvas-cpu/Hexapod_POC).

## Acknowledgments

MySelf, Hardware Provided by IIT Dhanbad.

## What’s Next?

I am currently working on a better hexapod. Since the arduino in to slow to handle the computational load, I will be using a raspberry-pi in the newer model. You can see the newer one in this post: [Hexapod](https://bryanvas-cpu.github.io/posts/Hexapod/).
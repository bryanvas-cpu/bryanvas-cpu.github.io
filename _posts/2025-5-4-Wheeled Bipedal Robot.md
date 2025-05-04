---
title: "Wheeled Bipedal Robot"
description: Design, Implementation, Simulation, Testing
date: 2025-5-4
categories: [Simulation, Robotics, Control]
tags: [robotics, simulation, dynamic, hardware]
author: "Bryan Vas"
image: assets/images/Wheeled_Biped/SIM.png # Feature image for the post
---

# LQR based Wheeled Bipedal Robot: Design, Implementation in Simulation

This project implements a Linear Quadratic Regulator (LQR) for a wheeled bipedal robot in simulation. As an optimal state-feedback controller, LQR utilizes a system model and offers improved performance over traditional PID controllers, ensuring better stability and control efficiency.

**Current Progress:**

- Simulation environment established in pybullet. 
- Hardware has been acquired.
- Assembly and transfering simulation to real world is in progress.

## esp32 Based Controller

esp32 developmnet module has beeen used here, for all communication, and computational needs.

### Simulation in PyBullet Simulator:
<!-- Full-width video -->
<!-- Full-width video with label -->
<div style="margin-bottom: 24px;">
  <div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe src="https://youtube.com/embed/cU9GdywgIZA"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
      style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
    </iframe>
  </div>
  <div style="text-align: center; margin-top: 8px; font-weight: bold;">Basic Implementation (without white noise)</div>
</div>

<!-- Two half-width videos side by side with labels -->
<div style="display: flex; gap: 16px;">
  <div style="flex: 1;">
    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
      <iframe src="https://youtube.com/embed/abBMGKY4s2A"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
      </iframe>
    </div>
    <div style="text-align: center; margin-top: 8px; font-weight: bold;">(with Filtered Gaussian Noise std:0.2)</div>
  </div>
  <div style="flex: 1;">
    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
      <iframe src="https://youtube.com/embed/0Fu-uNR4_DY"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
      </iframe>
    </div>
    <div style="text-align: center; margin-top: 8px; font-weight: bold;">Plots, of various filters implemented</div>
  </div>
</div>



### Overview

- The 3 videos shown above display the implementations of LQR, in both perfect world, and real world scenarios.
- Real world scenario is achieved by adding gaussian noise to all sensor readings.
- 3 filters have been implemented, namely: low pass(exponential average) filter, moving average filter, and median filter. here: LPF + MA filter has been found to give best results.

## Technical Details

### Hardware
- **In development**
<!-- BEGIN responsive image grid -->
<div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
  <div style="flex: 1 1 22%; min-width: 150px;">
    <img src="assets/images/Wheeled_Biped/rando_biped_image.jpeg" alt="Image 1" style="width: 100%; height: auto;">
  </div>
  <div style="flex: 1 1 22%; min-width: 150px;">
    <img src="assets/images/Wheeled_Biped/biped_test_setup.jpeg" alt="Image 2" style="width: 100%; height: auto;">
  </div>
  <div style="flex: 1 1 22%; min-width: 150px;">
    <img src="assets/images/Wheeled_Biped/biped_test_setup_2.jpeg" alt="Image 3" style="width: 100%; height: auto;">
  </div>
  <div style="flex: 1 1 22%; min-width: 150px;">
    <img src="assets/images/Wheeled_Biped/biped_PCB.jpeg" alt="Image 4" style="width: 100%; height: auto;">
  </div>
</div>
<!-- END responsive image grid -->


### Software
- **Programming Language:** Python, embedded C.

#### Source Code

The complete codebase and documentation are available on [GitHub](https://github.com/bryanvas-cpu/Ashsish_Biped)

## Acknowledgments

- Design, Software, Hardware, Electronics: me
- Funding: IIT Dhanbad

## What’s Next?

A lot of cool stuff.
- Completion of hardware
- Tuning and Testing
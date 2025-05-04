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


## Technical Details

### Hardware
- **Currently non existent (In development)**

### Software
- **Programming Language:** Python, C++.
- **Autonomy:** Fully autonomous drive to Target site (static environment).

#### Source Code

The codebase for the project will not be made public due to institute regulations, however, the software stack used is listed below.

- ROS2:(python) Slam-toolbox, Nav2.
- Non-linear Model Predictive control(NMPC): casadi, numpy.
- Path planning: (python) basic A* implementation.

## Acknowledgments

- CAD model: <a href="https://www.linkedin.com/in/shobit-verma15/" target="_blank">Shobit Verma</a> 
- Software: me
- Funding: IIT Dhanbad.

## What’s Next?

A lot of cool stuff.
- Improving the code structure
- Implementing CNN based ore detection
- Automatic mining of detected coal
- Adding behaviour tree, for full functionality
- and more

---
title: "LDH/UUV"
description: Implementation, Simulation
date: 2025-5-4
categories: [Simulation, Robotics, Autonomous]
tags: [robotics, simulation, uuv]
author: "Bryan Vas"
image: assets/images/UUV/URDF_view.png # Feature image for the post
---

# Autonomous Load Haul Dumper: Design, Basic Implementation, in Simulation

A foundational framework, currently under development, for deployment on underground vehicles.

**Current Progress:**

Initial simulation environment established, featuring a functional client interface with verified autonomous traversal to target destinations.

## ROS2 Based Controller

ROS2 based controller is implemented here for controlling the **Wheel Velocities**, and **Pivot Joint** of the LHD.


### Simulation in Gazebo Simulator:
<div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden;">
  <iframe src="https://youtube.com/embed/Xlj6dwbFPWI" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen 
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

### Overview

This video shows the following:

- **LEFT**: physics simulation
- **RIGHT**: visualization of position, and predicted trajectory using NMPC (green).
- A brief view of the client interface is shown at the begining where the target location is selected.

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

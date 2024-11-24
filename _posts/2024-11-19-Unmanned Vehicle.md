---
title: "Unmanned Land Rover POC"
description: Design, Implementation, and Testing
date: 2024-11-20
categories: [Projects, Robotics]
tags: [land rover, robotics, unmanned vehicles]
author: "Bryan Vas"
image: assets/images/UMV/UMV_POC.jpeg # Feature image for the post
---

# Unmanned Land Rover: Design, Implementation, and Testing

Creating an unmanned land rover has been an exciting and educational journey. This project, a collaboration with [Prof. Shikha Singh](https://iitism.irins.org/profile/215120), demonstrates how innovation and teamwork can solve real-world challenges in robotics.

## Demonstration Video

Watch the rover in action:

<iframe width="560" height="315" src="https://www.youtube.com/embed/6zfTf6diOmM" 
frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>

## Project Overview

The unmanned land rover was designed to:
- Navigate rough terrain.
- Use advanced sensor systems for monitoring its status, and environment.
- Demonstrate modular hardware and scalable software.

This project combines mechanical design, software algorithms, and sensor integration to achieve full autonomy.

## Technical Details

### Hardware
- **Base Platform:** Custom-built chassis - nothing special here
- **Sensors:** Inclination, ambient_temp, speed, weight, battery_level, battery temperature, time, battery_rating, charging_cycle, acceleration, battery_current, battery_voltage, humidity.
- **Controller:** Esp32 WROOM - Dual Antenna, + Arduino Nano.

### Software
- **Programming Language:** Embedded C
- **Autonomy:** Wireless Teleoperation, Using Shock-Burst Protocol, and NRF24L01 RF Module.
- **Website and database:** PHP, MySQL, Hostgator(hosting service + database)
- **Website for viewing Live Data(removed support by now):** http://ioioioio.in/ind.php

## Gallery

<div style="display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px;">
  <div>
    <img src="assets/images/UMV/UMV_internal.jpeg" alt="Rover Prototype" style="width: 100%;">
    <p style="text-align: center;">Figure 1: Rover prototype.</p>
  </div>
  <div>
    <img src="assets/images/UMV/umv_transmitter.jpeg" alt="Remote Control" style="width: 100%;">
    <p style="text-align: center;">Figure 2: Remote Control.</p>
  </div>
  <div>
    <img src="assets/images/UMV/Hostgator_data_example.png" alt="Stored Data" style="width: 100%;">
    <p style="text-align: center;">Figure 3: Stored Data.</p>
  </div>
  <div>
    <img src="assets/images/UMV/umv_live_page.jpeg" alt="Live Data" style="width: 100%;">
    <p style="text-align: center;">Figure 4: Live Data.</p>
  </div>
</div>


## Source Code

The complete codebase and documentation are available on [GitHub](https://github.com/bryanvas-cpu/UMV).

## Acknowledgments

This project was made possible through the guidance and support of [Prof. Shikha Singh](https://www.linkedin.com/in/professor-profile/). I am deeply grateful for her expertise and mentorship throughout the project.

## What’s Next?

WUnfortunately, I will not be trying to update this Project, as my interests have shifted to legged robots as of now. However, it was still a great learning experience, and well worth the time and effort!
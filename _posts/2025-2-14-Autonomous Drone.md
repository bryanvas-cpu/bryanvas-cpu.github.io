---
title: "Autonomous Drone"
description: Setup, Simulation, Implementation
date: 2025-2-14
categories: [Simulation, Robotics, Drone]
tags: [robotics, simulation, drone]
author: "Bryan Vas"
image: assets/images/Swift_pico/drone_assembly.jpeg # Feature image for the post
---

# Warehouse Drone: Implementation: Simulator + Hardware

## Overview

An autonomous quadcopter designed for warehouse logistics, equipped with a self-navigation system for obstacle avoidance in dynamic environments. It features package identification and seamless integration with central warehouse management systems (CWMS). The quadcopter optimizes inventory tracking and retrieval, enhancing supply chain efficiency in high-demand logistics operations.

## Control

CWMS: Broadcasts Package IDs. 
Drone Software: The drone system Identifies, Locates, and Traverses a dynamically computed Path to the target package.

### Simulation in Gazebo Simulator (Classical Control):

<div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden;">
  <iframe src="https://www.youtube.com/embed/VvDUvXERRvY"
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen 
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
</div>

This shows the Simulation of the Process:
- CWMS Sends Package IDs
- A Drone Client Node Receives These, computes the Paths to traverse, and sends waypoints to a Drone Server Node
- The Server is responsible for controlling the Drone, based of Client Requests, and Overhead Camera.

## Detailed Process:

### Arena/Warehouse Setup:

<div style="display: flex; justify-content: space-between; gap: 0.75vw; flex-wrap: wrap;">

  <!-- Simulated Setup -->
  <div style="flex: 1; min-width: 45%; max-width: 50%;">
    <h4>Simulated:</h4>
    <div style="width: 100%; display: flex; justify-content: center; align-items: center;">
      <img src="assets/images/Swift_pico/Setup_Simulation.png" alt="Simulated Setup" style="width: 100%; height: auto; display: block;">
    </div>
    <ul style="font-size: 14px;">
      <li>Overhead Camera for detecting Drone locations and identifying obstacles.</li>
      <li>4 Aruco markers at the corners of the Warehouse, used for image processing.</li>
      <li>Racks for storage of packages.</li>
      <li>Simulated drone, using force at each propeller based on throttle commands.</li>
    </ul>
  </div>

  <!-- Physical Setup -->
  <div style="flex: 1; min-width: 45%; max-width: 50%;">
    <h4>Physical:</h4>
    <div style="width: 100%; display: flex; justify-content: center; align-items: center;">
      <img src="assets/images/Swift_pico/arena_labelled.png" alt="Physical Setup" style="width: 100%; height: auto; display: block;">
    </div>
    <ul style="font-size: 14px;">
      <li>Overhead Camera: 1080P 2.1 Megapixel Digital CMOS Camera.</li>
      <li>4 Aruco markers at the corners of the Warehouse, used for image processing.</li>
      <li>To simulate storage racks, cardboard boxes have been used.</li>
      <li>Actual drone, with "Whycon Sticker" for identifying position.</li>
    </ul>
  </div>

</div>

### Path Creation:

- Image From Camera  === >  (1) Image Processing  === >  (2) Bitmap-Creation  === >  (3) Path Finding using A*  === >  (4) conversion to Trajectory with 3D Coordinates (waypoins)

<div style="width: 100%; max-width: 800px; margin: auto; display: flex; justify-content: center; align-items: center;">
  <img src="assets/images/Swift_pico/Image_processing+path.jpeg" alt="Image description" style="width: 100%; height: auto; display: block;">
</div>



### Drone Control

The Drone Server uses a PID controller to regulate roll, pitch, and throttle, ensuring stable hover at the client-specified target point.

<div style="width: 100%; max-width: 800px; margin: auto; display: flex; justify-content: center; align-items: center;">
  <img src="assets/images/Swift_pico/PID_block_diagram.jpeg" alt="Image description" style="width: 100%; height: auto; display: block;">
</div>

<!-- <div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden;">
  <iframe src="https://www.youtube.com/embed/7HyKRMM0qj4"
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen 
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    <p> Hover at target </p>
</div> -->

<div style="display: flex; justify-content: space-between; gap: 10px; flex-wrap: wrap;">
  <!-- First YouTube Short Video + Text -->
  <div style="flex: 1; max-width: 23.8%; text-align: center;">
    <div style="position: relative; padding-bottom: 177.78%; height: 0; overflow: hidden;">
      <iframe src="https://www.youtube.com/embed/7HyKRMM0qj4"
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen 
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>
    <p style="font-size: 16px; margin-top: 10px;">Hover at Target</p>
  </div>

  <!-- Regular Video + Text -->
  <div style="flex: 1; max-width: 75%; text-align: center;">
    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
      <iframe src="https://www.youtube.com/embed/TSCfxzi9k3s"
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen 
        style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>
    <p style="font-size: 16px; margin-top: 10px;">Traverse A square shape</p>
  </div>
</div>

## Upcomming : Traversing Path by avoiding Obstacles

## Technical Details

### Hardware
- **Kit:** E-yantra Drone Kit.

- **Flight Controller:** CrazyF405HD ELRS 1-2S AIO Flight controller. It is a flight controller with a built-in Serial ELRS receiver and 4-IN-1 Blheli_S 12A ESC
- **Transmitter:** Frsky’s Vantac ExpressLRS Lite TX Module
- **Overhead Camera:** Lenovo 4XC1B34802 FHD Webcam

#### Images
<div style="display: flex; justify-content: space-between; gap: 10px; flex-wrap: wrap;">
  <div style="flex: 1; max-width: 42%;">
    <img src="assets/images/Swift_pico/drone_assembly_e-yantra.jpeg" alt="Hexapod Internal View" style="width: 100%;">
  </div>
  <div style="flex: 1; max-width: 56%;">
    <img src="assets/images/Swift_pico/kit.jpeg" alt="Hexapod Complete Build" style="width: 100%;">
  </div>
</div>

### Software
- **Programming Language:** ROS2, Gazebo, Python,C++, OpenCV, Rviz2
- **Concepts:** Control Systems, Quadcopter Dynamics, Quadcopter Assembly, Computer Vision, Path Planning.

#### Source Code

- Due to Restrictions from E-yantra, I am not allowed to share the source code.

## Acknowledgments

Software: Package: E-yantra, Controller: me
Hardware: Drone-kit: E-yantra, Setup: me

## What’s Next?

Implememting Path Traversal + obstacle avoidance in Hardware.

Advanced Controllers for the drone.
- PID
- LQR
- Reinforcent Learning based Models

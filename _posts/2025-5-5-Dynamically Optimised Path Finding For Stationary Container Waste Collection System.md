---
title: "Dynamic Waste Collection Path Optimizer"
description: Simulation
date: 2025-5-5
categories: [Simulation, Environmental Engineering, Software]
tags: [simulation, dynamic, software]
author: "Bryan Vas"
image: assets/images/SWM/Waste-Routing-Software-Paving-the-Way-for-Smart-Waste-Management-scaled.jpeg # Feature image for the post
---

https://youtube.com/embed/AkaV2teI_iM

# Dynamically Optimised Path Finding For Stationary Container Waste Collection System

This project implements a **Brute Force** approach to determine the **optimal path**, that a waste collection vehicle should take for a stationary container system. 
It uses a **Physics based Model** that accounts for:
- 3D distance along route
- frictional (road + braking), and gravity based energy losses
- dynamic weight changes, while driving due to:
  1. Continuous fuel consumption
  2. Weight change due to pickup of waste

**Current Progress:**

- Client interface for user to select target collection sites, and valid routes created.
- Simulation environment created. 
- Testing of algorithm yielded satisfactory results.

## Basic Overview of the work:

This project can be explained in 3 parts.
1. metadata
2. client interface
3. path finding algorithm

### Metadata

Inorder to use the client interface, we must provide
1. the satellite raster elevation map of the land area under consideration. (necessary for correct physics calculations)
2. the road map of the same area. (note: this is just an overlay, inorder to be able to easily identify the necessary locations)
<div class="row">
  <div class="col-md-6 mb-3">
    <div class="border p-2 text-center">
      <img src="assets/images/SWM/Road_Map_Dhanbad.png" class="img-fluid" alt="Image 1">
      <p class="mt-2 small">Fig. 1 Road Map of area</p>
    </div>
  </div>
  <div class="col-md-6 mb-3">
    <div class="border p-2 text-center">
      <img src="assets/images/SWM/Elevation_Dhanbad.png" class="img-fluid" alt="Image 2">
      <p class="mt-2 small">Fig. 2 Elevation Map of same area</p>
    </div>
  </div>
</div>

### Client Interface

The client interface shows the road map of the area.
for usage of the interface, the user needs to:
1. select Starting location, Target sites, and Disposal/MRF/Transfer station.
2. select neighbors for each node.
3. select various intermediate points between each node, and its neighbours.

**Advantages of this setup:** it allows us flexibility in choosing the routes, such as metalled roads. Also, for example, if a road between two nodes A, and B is 2-way-road, each of the two nodes (A,B) can be each others neighbours, but if it is a one way road, then only A will be a neighbour of B, or vice-versa.

### Path Finding Algorithm (Technical Details)

The Path finding algorithm follows the structure of a branching tree, where each simluation step moves the disposal velicle to the next location.

- At the begining(start), the first step will be an intermediate node, from one of the neighbouring paths.
- If the vehicle reaches an intermediate node, the energy used in this step is calculated based of frictional loss, and gravity/braking. Then the fuel mass reduction is calculated based on energy spent an taking the step, calorific value of the fuel, and fuel effeciency of the truck.
- If the vehicle reaches a target Waste Collection site, then along with the above, the mass of the vehicle is also updated, and carried on throught the simulation.
- After any of these, the process carries on until any of the termination steps are reached. (branches that reach disposal/ are more ineffecient than previously conputed path/ exceed the fuel capacity).

### Images and Video Demonstration

<div style="margin-bottom: 24px;">
  <div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden;">
    <iframe src="https://youtube.com/embed/AkaV2teI_iM"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
      style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
    </iframe>
  </div>
  <div style="text-align: center; margin-top: 8px; font-weight: bold;"></div>
</div>

Steps: 
  1. Set Collection sites, neighbors for each, and intermediate points. (you can see the feedback in bottom left of video).
  2. Set the required Target sites, along with associated waste quantity at those location.
  3. Run the simulation.(it will output the paths that take minimum, as well as maximum energy).

<div class="row">
  <div class="col-md-6 mb-3">
    <div class="border p-2 text-center">
      <img src="assets/images/SWM/client.png" class="img-fluid" alt="Image 1">
      <p class="mt-2 small">Fig. 3 Set Collection Sites, their neighbors, and intermediate path</p>
    </div>
  </div>
  <div class="col-md-6 mb-3">
    <div class="border p-2 text-center">
      <img src="assets/images/SWM/succesful_run.png" class="img-fluid" alt="Image 2">
      <p class="mt-2 small">Fig. 4 Choose Targets Sites, and run simulator</p>
    </div>
  </div>
</div>


### Source Code

The complete codebase and documentation are available on [GitHub](https://github.com/bryanvas-cpu/SWM)

## Acknowledgments

- me

## What’s Next?

nothing for now
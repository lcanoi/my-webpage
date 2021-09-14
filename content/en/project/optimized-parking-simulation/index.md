---
title: MySpot - Optimized Parking Simulation
subtitle: ""
date: 2021-09-01T03:57:45.024Z
summary: Simulation of multiagents with an intelligent system to improve the waiting time of cars when looking for a parking space in a plaza. Made in Unity
draft: false
featured: false
tags:
  - C#
  - Unity
  - Programming
external_link: ""
# https://github.com/lcanoi/OptimizedParkingSimulation
image:
  filename: featured.png
  focal_point: Smart
  preview_only: false
---

## Overview
MySpot is the result of the solution created for a Modeling of multiagent systems with computer graphics project. This brings a simulation of multiagents in which an intelligent system helps to improve the waiting time when looking for a parking space in a plaza.

## Example of the simulation:
[![Simulation Example](https://img.youtube.com/vi/YWoAGjl28zU/0.jpg)](https://www.youtube.com/watch?v=YWoAGjl28zU)

## Find the project on Github
[**MySpot**](https://github.com/lcanoi/OptimizedParkingSimulation)


## Tools
For the creation of this project, the tools that were mainly used were:
+ NetLogo: for initial simulation and algorithm testing (multi-agent area).
+ Unity: for the development of the final project (multi-agent and graphics area).

## Further improvment
+ Improving the intelligence of the sensor system in the parking lot:
  + Not only assigning cars parking spots near the shop they want to go to but consider also the time each one will approximately take on the store. It might be better to park further away cars that stay for a long time while prioritizing the closer spots for cars that leave quickly.
  + Should also consider to save enough disabled parking spots near each shop.
+ Add cars to the circulation which are not going to any shop, just passing through the street.
+ Fixing bugs that can happen when running a simulation with a fast car spawn rate and high concentration of cars.

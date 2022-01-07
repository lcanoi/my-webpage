---
title: Unity Internship at Gamejam
subtitle: ""
date: 2021-09-02T03:57:45.024Z
summary: Worked with Gamejam to develop an idea/brief into a game prototype working with a larger team and learning from their work process.
featured: false
tags:
  - C#
  - Unity
  - Programming
  - UI/UX
external_link: ""
# 
image:
  filename: featured.png
  focal_point: Smart
  preview_only: false
---

## Overview
While working at Gamejam I managed to learn a lot about working in a large team for a software project as well as learning numerous skills for C# developing in Unity.
My work there can be described in the following points:


### UI/UX
I was added to a Figma project with all of the screen layouts for an existing game project and was asked to implement the UI/UX layouts from Figma into Unity.
I created the following 3 screens accesible from the starting screen from the game, with working buttons, select options, scroll, small animations...

image:
  filename: img1.png
  focal_point: Smart
  preview_only: false

image:
  filename: img2.png
  focal_point: Smart
  preview_only: false

image:
  filename: img3.png
  focal_point: Smart
  preview_only: false

Developed an idea/brief into a game prototype, creating the following:
- Player mechanics
- Enemies AI
- Obstacles and interactions with them
- Editor Tool for Level Building
Worked with a large team providing ideas for others and implementing received feedback into my own projects.

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

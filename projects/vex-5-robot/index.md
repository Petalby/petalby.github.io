---
layout: page
title: VEX V5 Robot Programming Project
permalink: /projects/vex-5-robot/
---

<p class="project-summary">A Python robotics project exploring motion control, trajectory tracking, kinematic model validation, and sensor-based feedback.</p>

<div class="tag-row"><span>Python</span><span>VEX V5</span><span>Robot kinematics</span><span>Trajectory tracking</span><span>Sensor feedback</span></div>

## Overview

As part of a robotics lab course, I worked on a comprehensive VEX V5 robot programming project using Python. The goal was to explore motion control, trajectory tracking, and sensor-based feedback in autonomous robots.

This project was completed by Alberta Petiafo, Priscilla Yeboaa, and Hillary Kiduhu Ndeda.

<div class="project-media two-column-media">
    <img src="{{ '/assets/vexrobot.jpeg' | relative_url }}" alt="VEX 5 mobile robot used in the project">
</div>

## What I Did

### 1. Motion Control and Kinematics

I programmed basic robot actions including forward driving, turns, and spins. I combined these actions to trace a triangle, learning how encoder ticks and wheel synchronization affect path accuracy. I addressed real-world issues such as slippage and drift through unit calibration and speed tuning.

### 2. Validating Robot Models

I verified forward-kinematic equations by comparing theoretical and experimental velocities. I simulated and executed an S-shaped trajectory using numerical integration in Python, achieving high tracking accuracy with a fine-tuned timestep of 0.01 seconds.

### 3. Sensor Integration and Smart Control

I mounted an ultrasonic sensor to detect obstacles in real time and implemented a feedback loop that paused the robot when an obstacle was nearby and resumed motion once the path was clear. I also used proportional control to follow waypoints smoothly and minimize deviation.

## Key Takeaways

1. Developed proficiency in differential-drive robot control using Python and VEX V5.
2. Gained hands-on experience with real-time sensor integration.
3. Deepened my understanding of how kinematic theory relates to physical robot behaviour.
4. Developed skills in simulation, control tuning, and problem-solving in dynamic environments.

## Demonstrations

<div class="link-list">
  <a href="https://youtu.be/Qjbvib-Wt3s">Moving in an arbitrary zigzag path →</a>
  <a href="https://youtu.be/l_IQPxSFarE">Moving in an enclosed trajectory →</a>
  <a href="https://youtu.be/jlOTTmG8V8g">Using a distance sensor on an S trajectory →</a>
  <a href="https://youtu.be/K29BbcEq1vo">Following an S trajectory while updating orientation →</a>
</div>

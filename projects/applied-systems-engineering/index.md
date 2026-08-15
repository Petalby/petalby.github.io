---
layout: page
title: The Transporter
permalink: /projects/applied-systems-engineering/
---

<p class="project-summary">An autonomous mobile robot designed to follow a course, identify and transport colour-coded packages, cross a step, and balance a ping-pong ball.</p>

<div class="tag-row"><span>C++</span><span>STM32</span><span>Mbed OS</span><span>Systems engineering</span><span>Line following</span><span>Sensor fusion</span><span>Autonomous robotics</span></div>

## Project overview

The Transporter was developed for the MECH 617 Applied Systems Engineering course. The project brought several mechanical, electrical, sensing, and embedded-software subsystems together in one autonomous robot.

The team consisted of Alberta Petiafo, Priscilla Yeboaa Asiedu, Samuel Kojo Akwensivie, Godlove Bissaga, and Douglas Kumi Koomson.

<figure class="featured-project-image">
  <img src="{{ '/assets/applied-systems-robot.jpeg' | relative_url }}" alt="The Transporter autonomous mobile robot with its electronics and package-handling mechanism visible">
  <figcaption>The assembled Transporter robot.</figcaption>
</figure>

## Mission

The robot was designed to operate autonomously and complete a clockwise course in the shortest possible time. Its mission was to:

1. Start at the depot and follow a 20 mm black line.
2. Identify package locations using red, blue, green, and yellow markers.
3. Pick up each package and deliver it to the matching destination.
4. Cross a step without turning around.
5. Balance a ping-pong ball throughout the run.

## Engineering challenges

### Mobility and step crossing

The chassis and wheel system had to fit within an initial envelope of 200 × 200 × 200 mm and climb a step. The robot used DC motors with encoders and was powered by the supplied 12 V NiMH battery pack.

### Line following and colour detection

An infrared line sensor enabled the robot to follow the course. A colour sensor distinguished the four package markers so the robot could associate packages with their correct destinations. The team developed the `LineFollower.cpp` implementation used by the system.

### Package transport

The mechanical pickup system collected the colour-coded packages, retained them while following the course, and positioned them for delivery at the corresponding coloured locations.

### Ball balancing

A two-degree-of-freedom gimbal used two servos and IMU feedback to balance a ping-pong ball while the robot moved. Accelerometer and gyroscope measurements were combined using a team-developed one-dimensional Mahony filter to estimate roll and pitch.

## Embedded implementation

The system used an STM32F446RE Nucleo board and PES expansion board. 

## Outcome and lessons

The final lightweight prototype demonstrated colour sensing, package transport, line following, step crossing, and ball balancing as an integrated system. The project reinforced the importance of teamwork and systems thinking: changing one mechanical, electronic, or software component affected the performance of the complete robot.

<a class="button button-primary" href="{{ '/assets/the-transporter-portfolio.pdf' | relative_url }}">View The Transporter portfolio</a>

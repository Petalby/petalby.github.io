---
layout: page
title: Ball Balancing Robot
permalink: /projects/ball-balancing-robot/
---

<p class="project-summary">A team robotics project demonstrating feedback control by balancing a ball with a PID controller.</p>

<div class="tag-row"><span>Robotics</span><span>PID control</span><span>Feedback systems</span></div>

## Project overview

This project was completed by Acha Simonel Fon, Alberta Petiafo, Andrew Omolo, Ayobami Olumide Adigun, and Jamiu Olamide Afolayan.

<figure class="featured-project-image">
  <img src="{{ '/assets/ball-balancing-robot.png' | relative_url }}" alt="Ball-balancing robot shown with the ball in two positions on its platform">
  <figcaption>The ball-balancing robot platform.</figcaption>
</figure>

## Closed-loop control architecture

The desired X and Y ball positions are compared with the measured positions from a 60 Hz camera. A PID controller generates the control action, inverse kinematics converts it into the required plate orientation, and the servos actuate the plate. The measured ball position is then returned through the feedback loop.

<figure class="control-diagram">
  <img src="{{ '/assets/ball-balancing-closed-loop.png' | relative_url }}" alt="Closed-loop response diagram showing PID control, inverse kinematics, servos, ball dynamics, and camera feedback">
  <figcaption>Closed-loop control architecture for the ball-balancing system.</figcaption>
</figure>

## Reference

The [Multi-Scale Robotics Lab at ETH Zürich](https://msrl.ethz.ch/) is referenced for its work in robotics and intelligent systems. This acknowledgment is provided as a technical reference and does not imply an institutional affiliation.

<a class="button button-primary" href="https://youtu.be/WWQu4sDhVPg">Watch the PID controller demonstration</a>

---
layout: page
title: Ball Balancing Robot
permalink: /projects/ball-balancing-robot/
---

<p class="project-summary">A real-time ball-balancing system using visual tracking, inverse kinematics, and PID feedback control.</p>

<div class="tag-row"><span>C</span><span>ESP32</span><span>Pixy2</span><span>PID control</span><span>Inverse kinematics</span><span>Camera calibration</span></div>

## Project overview

This project focuses on building a real-time ball-balancing system controlled through a PID feedback loop. The system uses three KST DS725MG RC servos connected to a tilting plate through mechanical linkages. A Pixy2 camera tracks the ball’s position for closed-loop control, while a Feather HUZZAH ESP32 microcontroller runs the control system.

The plate is supported by three servo-actuated legs, forming a 3-RRS parallel mechanism. Controlling the plate’s pitch and roll makes it possible to regulate the position and motion of the ball.

This team project was completed by Acha Simonel Fon, Alberta Petiafo, Andrew Omolo, Ayobami Olumide Adigun, and Jamiu Olamide Afolayan.

<figure class="featured-project-image">
  <img src="{{ '/assets/ball-balancing-robot.png' | relative_url }}" alt="Ball-balancing robot shown with the ball in two positions on its platform">
  <figcaption>The ball-balancing robot platform.</figcaption>
</figure>

## Experiments

We conducted three experiments to evaluate the system’s performance:

1. **Centering:** Bringing the ball to rest at the centre of the plate.
2. **Step response:** Studying the ball’s dynamics as it moved from the centre to an outer radius 80 cm away under underdamped, critically damped, and overdamped conditions.
3. **Circular trajectory:** Guiding the ball along a circular reference path.

### Experiment videos

<div class="link-list">
  <a href="https://youtu.be/AtePK2dwZHQ">Watch the centering response →</a>
  <a href="https://youtube.com/shorts/TwZUbm-KzVU">Watch the step response →</a>
</div>

## Camera calibration and signal filtering

Camera calibration was performed to reduce image distortion and accurately map the ball’s position from camera coordinates to real-world coordinates. This mapping is essential for precise closed-loop control.

To reduce noise in the feedback signal:

- Position measurements are filtered using a moving-average filter with a buffer size of 10.
- Velocity estimates are smoothed using a shorter moving-average filter with a buffer size of 5.

## PID implementation

The PID controller was implemented in C using a discretized form of the continuous control law. At each timestep:

- The proportional term responds to the current position error.
- The integral term accumulates error over time using the Forward Euler method.
- The derivative term uses filtered velocity differences and the Backward Euler method.

## My contributions

My primary contributions were the Pixy2 camera calibration and the derivation of the inverse-kinematics model for the 3-RRS parallel mechanism.

For camera calibration, I corrected lens distortion and applied extrinsic camera transformations to convert the ball’s image-frame coordinates into real-world coordinates. For inverse kinematics, I derived the mathematical relationships required to calculate the servo angles corresponding to desired plate pitch and roll orientations. The inverse-kinematics model was validated by commanding specific plate tilts and comparing the resulting orientation with smartphone IMU measurements.

## Closed-loop control architecture

The desired X and Y ball positions are compared with the measured positions from a 60 Hz camera. A PID controller generates the control action, inverse kinematics converts it into the required plate orientation, and the servos actuate the plate. The measured ball position is then returned through the feedback loop.

<figure class="control-diagram">
  <img src="{{ '/assets/ball-balancing-closed-loop.png' | relative_url }}" alt="Closed-loop response diagram showing PID control, inverse kinematics, servos, ball dynamics, and camera feedback">
  <figcaption>Closed-loop control architecture for the ball-balancing system.</figcaption>
</figure>

## Academic collaboration

This coursework was taught by [Multi-Scale Robotics Lab](https://msrl.ethz.ch/) as part of the Ashesi-ETHZ collaboration. The lab introduced the feedback-control platform and guided the work on inverse kinematics, camera calibration, and model validation.

<a class="button button-primary" href="https://youtu.be/WWQu4sDhVPg">Watch the PID controller demonstration</a>

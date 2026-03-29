# Arduino-Based Inverted Pendulum Stabilization using PD Control

This project focuses on stabilizing an inverted pendulum — a classic problem in control systems — using an Arduino-based setup. Since the pendulum is naturally unstable, the goal is to keep it balanced upright using continuous real-time feedback.

## Overview
In this project, I built a wheeled cart system with a vertical pendulum and implemented a control strategy to keep it balanced. The angle of the pendulum is measured using a quadrature encoder, and based on this, corrective action is taken to maintain stability.

The entire system runs in real time, where sensing, computation, and actuation happen continuously.


## Key Features
- Real-time stabilization of the inverted pendulum  
- Implementation of a PD controller  
- Angle measurement using a quadrature encoder  
- PWM-based motor control using L298N driver  
- Safety mechanism for large tilt angles  
- Simulation using state-space modeling and pole placement  


## Control Strategy
The system is controlled using a PD controller:

u(t) = - (Kp * θ + Kd * dθ/dt)

Here, the proportional term helps correct the angle error, while the derivative term reduces oscillations and improves stability. A low-pass filter is used with the derivative term to reduce noise effects.


## Implementation Details
- The control loop runs at approximately 200 Hz using `micros()`  
- Encoder signals are processed using interrupts  
- Angle and angular velocity are computed in real time  
- Motors are controlled using bidirectional PWM signals  
- The system is structured into sensing, control, and actuation blocks  

## Outcome
After tuning the controller, the system is able to balance the pendulum near the upright position. The response is quick, and oscillations are reduced to a reasonable level.

During implementation, challenges like sensor noise, tuning of controller gains, and mechanical imperfections were encountered and handled.


## Applications
- Self-balancing robots  
- Robotics and automation  
- Aerospace stabilization systems  
- Control systems education  


## Conclusion
This project helped in understanding how control theory works in practice. It shows how a relatively simple controller like PD can stabilize an unstable system when implemented properly in real time.


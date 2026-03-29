Arduino-Based Inverted Pendulum Stabilization using PD Control

This project focuses on building and controlling an inverted pendulum on a wheeled cart, a well-known problem in control engineering used to study system stability. The goal is to keep the pendulum balanced upright, even though it is naturally unstable, by using real-time feedback control.
The hardware setup uses an Arduino-based mobile platform, where the angle of the pendulum is measured using a quadrature encoder. A Proportional–Derivative (PD) controller processes this information and continuously adjusts the motor input to keep the system balanced. The controller works by correcting the tilt and reducing oscillations to maintain stability.
Alongside the hardware implementation, a state-space model of the system is developed and analyzed using pole placement techniques. This helps in understanding the system behavior theoretically and provides a comparison between classical control (PD) and modern control methods.

Key Features
•Real-time stabilization of the inverted pendulum using embedded control
•PD controller with derivative filtering to reduce noise effects
•Accurate angle measurement using a quadrature encoder with interrupts
•Motor control using PWM signals through an L298N driver
•Built-in safety mechanism to stop the system if the pendulum tilts too far
•State-space modeling and pole placement-based control in simulation

Control Strategy
The hardware system is controlled using a PD controller, given by:
u(t) = − (Kp·θ + Kd·θ̇)

Here, the proportional term corrects the angle error, while the derivative term helps reduce oscillations and improves stability. A low-pass filter is applied to the derivative term to make the system less sensitive to noise.
In simulation, state feedback control using pole placement is used. By placing the system poles at desired locations, the system’s stability and response can be shaped more precisely.


Implementation Details
•Control loop runs at approximately 200 Hz using micros()
•Encoder signals are processed using hardware interrupts
•Angle and angular velocity are computed in real time
•Motors are driven using bidirectional PWM signals
•System design separates sensing, control, and actuation for clarity

Outcome
The system is able to balance the pendulum around the upright position with reasonable stability after proper tuning. The response is quick, and oscillations are minimized. During development, practical challenges such as sensor noise, controller tuning, and mechanical imperfections were encountered and addressed.

Applications

The concepts used in this project are relevant to:

•Self-balancing robots and vehicles
•Aerospace and rocket stabilization systems
•Robotics and automation
•Teaching and research in control systems


Conclusion
This project brings together theory and practice by implementing control concepts on a real system. It demonstrates how a simple PD controller can effectively stabilize an unstable system, while also highlighting the usefulness of state-space methods for deeper analysis and design.

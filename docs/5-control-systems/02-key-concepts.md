
# Chapter 5: Key Concepts

This chapter introduces the engineering discipline that makes robots function reliably in the real world.

- **Control System:** A system that manages, commands, directs, or regulates the behavior of other devices or systems to achieve a desired result. In robotics, it's what translates a goal into action.

- **Setpoint (SP):** The desired state or target value for the system. For a robot joint, the setpoint is the desired angle. For a cruise control system, it's the desired speed.

- **Process Variable (PV):** The actual, measured state of the system. This measurement is provided by a sensor. For the robot joint, the PV is the *actual* angle measured by the joint's encoder.

- **Error:** The difference between the Setpoint (SP) and the Process Variable (PV). `Error = SP - PV`. The goal of a control system is to make this error zero.

- **Feedback:** The process of using the Process Variable (the sensor measurement) to calculate the error and adjust the system's output. Feedback is the core idea of closed-loop control.

- **Open-Loop Control:** A control system that does *not* use feedback. It sends a command and just assumes it will work, without checking the result. It's like throwing a ball with your eyes closed.

- **Closed-Loop Control:** A control system that *does* use feedback. It constantly measures the result, compares it to the goal, and makes corrections. It's like steering a car—you are always watching the road and making small adjustments.

- **PID Controller:** The most common type of closed-loop feedback controller. It calculates an output command based on three terms:
    - **Proportional (P):** The reaction is *proportional* to the current error. A big error gets a big correction.
    - **Integral (I):** The reaction is based on the *sum of past errors*. This helps eliminate small, steady-state errors over time.
    - **Derivative (D):** The reaction is based on the *rate of change* of the error. This helps to predict future errors and dampen oscillations, preventing the system from overshooting its goal.

- **Hierarchical Control:** A control strategy where a complex task is broken down into a pyramid of simpler sub-tasks.
    - **High-Level Control (AI):** Decides the overall goal (e.g., "pick up the blue cup").
    - **Mid-Level Control:** Plans the motions required (e.g., calculates the trajectory for the arm).
    - **Low-Level Control (PID):** Manages the individual motors to follow that trajectory precisely.

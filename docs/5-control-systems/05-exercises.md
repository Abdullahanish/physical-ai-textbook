
# Chapter 5: Exercises

Let's apply your new knowledge of control systems.

### Exercise 1: Open-Loop or Closed-Loop?

For each system below, determine if it is an example of **Open-Loop** or **Closed-Loop** control.

1.  **A simple kitchen toaster:** You put bread in, push the lever, and a timer runs. The toaster doesn't check how brown the toast is; it just stops when the time is up.
    -   (Open-Loop / Closed-Loop)

2.  **The thermostat in your house:** You set a desired temperature. A thermometer constantly measures the actual temperature and turns the furnace on or off to maintain that setting.
    -   (Open-Loop / Closed-Loop)

3.  **A remote-controlled car:** You press the "forward" button on the remote, which sends a signal to the car's wheels to spin. You, the driver, watch the car and decide when to stop or turn.
    -   (Open-Loop / Closed-Loop)  *(Hint: Where is the feedback sensor and controller in this system?)*

4.  **An automatic watering system for a garden:** It is programmed to turn on the sprinklers every day at 6 AM for 15 minutes, regardless of whether it has been raining or not.
    -   (Open-Loop / Closed-Loop)

### Exercise 2: The PID Controller

You are tuning a PID controller for the cruise control in your car. Describe what would probably happen in the following scenarios.

1.  **Your P (Proportional) value is set too high, and you don't use I or D.**
    -   *Behavior:* ________________________________________________________________

2.  **You have a well-tuned P and D, but your I (Integral) value is set to zero.** You are driving up a long, gentle hill.
    -   *Behavior:* ________________________________________________________________

3.  **You have a well-tuned P and I, but your D (Derivative) value is set to zero.**
    -   *Behavior:* ________________________________________________________________

### Exercise 3: Design a Control System

You are tasked with building a control system for a simple robot. The robot's goal is to keep a ping-pong ball balanced on a flat plate that it can tilt left and right.

1.  **What is the overall goal of the system?**
2.  **Setpoint (SP):** What is the desired state?
3.  **Process Variable (PV):** What sensor would you use to measure the current state?
4.  **Actuator:** What actuator would you use to take action?
5.  **Describe the feedback loop in one sentence.**

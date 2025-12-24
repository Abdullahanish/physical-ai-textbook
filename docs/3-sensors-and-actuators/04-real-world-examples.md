
# Chapter 3: Real-World Examples

Let's look at how sensors and actuators work together in some familiar robots.

### 1. A Self-Driving Car (e.g., Waymo)

This is a fantastic example of complex sensor fusion and actuation.

- **The Goal:** Drive safely from point A to point B.
- **Sensors in Action:**
    - **LiDAR:** The spinning sensor on the roof creates a continuous 360-degree, 3D map of the world around the car, detecting the precise location of other vehicles, pedestrians, and the road itself.
    - **Cameras:** Multiple cameras around the car are used to read traffic lights, identify road signs (like a stop sign or speed limit), and see lane markings.
    - **Radar:** Often mounted on the front and back of the car, radar is good at detecting the speed of other objects, even in bad weather like rain or fog where LiDAR and cameras might struggle.
    - **IMU:** Measures the car's motion to help the AI understand if it's accelerating, braking, or turning smoothly.
    - **GPS:** Provides the car's overall location on a map.
- **Sensor Fusion:** The car's AI controller takes the data from *all* these sensors and fuses it into a single, unified understanding of the world. This is what allows it to make safe driving decisions.
- **Actuators in Action:** The AI's decisions are turned into physical actions by electronically controlling the car's standard actuators:
    - The **steering rack** (to turn the wheels).
    - The **throttle** (to accelerate).
    - The **brakes** (to slow down).

### 2. A Robotic Vacuum Cleaner (e.g., Roomba)

A much simpler, but still effective, use of the Sense-Act loop.

- **The Goal:** Clean the floor without falling down the stairs or getting stuck.
- **Sensors in Action:**
    - **Infrared (IR) Sensors:** These are exteroceptive sensors on the bumper. When the Roomba is about to hit a wall, the IR beam is reflected back, telling the controller to stop and turn.
    - **Cliff Sensors:** These are IR sensors on the bottom of the robot, pointing downwards. If the signal suddenly takes a long time to come back (or doesn't come back at all), the controller knows it has reached a "cliff" like a staircase and backs away.
    - **Wheel Encoders:** These are proprioceptive sensors that track how much the wheels have spun. This allows the robot to estimate how far it has traveled.
- **Actuators in Action:**
    - **DC Motors:** Two DC motors drive the left and right wheels independently. To turn, the controller simply spins one wheel faster than the other.
    - **DC Motors (for Cleaning):** Other small DC motors are used to spin the cleaning brushes and create vacuum suction.

### 3. A Humanoid Robot Hand

- **The Goal:** Pick up a variety of objects, from a strong tool to a delicate strawberry.
- **Sensors in Action:**
    - **Joint Angle Encoders:** Proprioceptive sensors in each finger joint tell the controller the exact position of the fingers.
    - **Force-Torque Sensors:** Located in the fingertips, these exteroceptive sensors give the hand a sense of "touch." They measure how much force is being applied, so the AI knows whether it has a firm grip or if it's about to crush the object.
- **Actuators in Action:**
    - **Servo Motors:** Each joint in the finger is controlled by a small servo motor, allowing the controller to command a precise curl for each finger. By coordinating the servos, the hand can form different grips (a pinch grip, a power grip, etc.).


# Chapter 2: Real-World Examples

The basic principles of robotics are at play in thousands of different machines around us. Here are a few examples that show these concepts in action.

### 1. Industrial Robotic Arm (e.g., KUKA or FANUC arms)

- **What they are:** These are the most common type of robot, found in factories all over the world, especially in car manufacturing. They are typically bolted to the floor.
- **Components in Action:**
    - **Frame:** A series of heavy, connected metal links.
    - **Actuators:** Powerful electric motors located at each joint.
    - **Controller:** A large computer cabinet that sits next to the robot, running the pre-programmed movements.
    - **End-Effector:** This is interchangeable. It might be a gripper to lift a car door, a welding torch to join parts, or a paint sprayer.
    - **Degrees of Freedom (DoF):** Most industrial arms have 6 DoF, which is enough to position the end-effector in any orientation (x, y, z, roll, pitch, yaw) within its workspace.
- **Kinematics:** These robots rely heavily on solving inverse kinematics problems with extreme precision. The controller calculates the exact joint angles needed to move the welding torch along a perfect seam on a car chassis.

### 2. The "Spot" Robot from Boston Dynamics

- **What it is:** A four-legged "robot dog" designed for inspection and data collection in places where it's difficult or dangerous for humans to go.
- **Locomotion in Action:** This is a prime example of **legged locomotion**. Spot can walk, run, climb stairs, and even get back up if it falls over. This makes it far more versatile than a wheeled robot for exploring a construction site or a disaster area.
- **Components in Action:**
    - **Frame:** A lightweight but strong chassis designed to house the batteries and controller while keeping the robot's center of gravity low for stability.
    - **Sensors:** It's covered in cameras and sensors that give it a 360-degree view of its environment, which is crucial for avoiding obstacles and navigating rough terrain.
    - **Controller:** A very powerful onboard computer runs the complex algorithms for balance and walking.
    - **Actuators:** 12 motors (3 in each leg) provide the high number of Degrees of Freedom needed for such agile movement.

### 3. A Common Consumer Drone (e.g., DJI Mavic)

- **What it is:** A small, four-propeller aerial robot used for photography, videography, and recreation.
- **Locomotion in Action:** This is **aerial locomotion**. The controller precisely adjusts the speed of the four propellers (actuators) to make the drone hover, fly forward, or turn. For example, to fly forward, the rear propellers spin faster than the front ones, tilting the drone and creating forward thrust.
- **Components in Action:**
    - **Frame:** An extremely lightweight frame, often made of plastic or carbon fiber, to maximize flight time.
    - **Power Source:** A high-density lithium-polymer (LiPo) battery, which is a major limiting factor for how long it can fly.
    - **Controller:** An onboard flight controller uses data from an gyroscope and accelerometer to keep the drone stable in the air. The AI for obstacle avoidance also runs on this controller.
    - **Sensors:** GPS for location, cameras for navigation, and often infrared sensors to avoid crashing into things.


# Chapter 2: Key Concepts

This chapter introduces the fundamental building blocks of any robot. Understanding these concepts is essential for figuring out how robots work.

- **Robot:** A machine capable of carrying out a complex series of actions automatically, especially one programmable by a computer. A true robot can **sense** its environment, **process** that information, and **act** upon its environment.

- **Frame / Chassis:** The physical structure or skeleton of the robot that holds all the other components together. It determines the robot's shape and durability.

- **Controller:** The "brain" of the robot's body. It's a computer that takes information from the sensors and sends commands to the actuators. In Physical AI, the AI software runs on the controller.

- **Power Source:** What provides energy to the robot. This could be a battery for a mobile robot or a connection to a wall outlet for a stationary one.

- **Degrees of Freedom (DoF):** The number of basic ways a robot or a robot joint can move. A simple joint that just bends like your elbow has one Degree of Freedom. A robot's total DoF describes its overall agility.

- **Locomotion:** The study of how robots move. This includes different methods like:
    - **Wheeled Locomotion:** Using wheels to roll across a surface (fast and efficient on flat ground).
    - **Legged Locomotion:** Using legs to walk or run (better for uneven terrain).
    - **Aerial Locomotion:** Using propellers or wings to fly (drones).

- **End-Effector:** The tool or "hand" at the end of a robotic arm. It's the part that directly interacts with objects. Examples include grippers, drills, or welding torches.

- **Kinematics:** The study of motion without considering the forces that cause it. In robotics, it's about figuring out the position of the robot's end-effector based on the angles of all its joints.
    - **Forward Kinematics:** If you know the angles of all the joints, where is the hand?
    - **Inverse Kinematics:** If you want the hand to be at a specific spot, what do the angles of the joints need to be? (This is much harder!)

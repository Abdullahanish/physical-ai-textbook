
# Chapter 3: Key Concepts

This chapter is about the hardware that connects the robot's brain to the physical world. Here are the essential concepts.

- **Sensor:** A device that detects and responds to some type of input from the physical environment. Sensors are the "input" devices for a robot, converting physical properties like light, sound, and pressure into electrical signals the controller can read.

- **Actuator:** A device that converts energy (usually electrical) into physical motion. Actuators are the "output" devices for a robot—its muscles. They are what make the robot move.

- **Proprioceptive Sensors:** These are "internal" sensors that tell the robot about its own state. For example, a sensor that measures the angle of a robot's elbow joint is proprioceptive. It's like your own sense of where your limbs are without having to look at them.

- **Exteroceptive Sensors:** These are "external" sensors that tell the robot about the world around it. Cameras, microphones, and touch sensors are all exteroceptive.

- **Camera:** A sensor that captures light to create an image. It's the robot's sense of sight.

- **LiDAR (Light Detection and Ranging):** A sensor that measures distances by shooting out a laser beam and timing how long it takes for the light to bounce back. It's often used to create 3D maps of the environment.

- **IMU (Inertial Measurement Unit):** A sensor that combines accelerometers (to measure acceleration) and gyroscopes (to measure rotation). An IMU is crucial for a robot to understand its own motion and orientation, helping with balance and navigation.

- **Force-Torque Sensor:** A sensor that measures forces and twisting motions (torques). These are often placed in a robot's wrist or joints to give it a sense of "touch" and to control how hard it pushes on something.

- **Electric Motors:** The most common type of actuator in robotics.
    - **DC Motor:** A simple motor that spins when you apply power. Good for driving wheels.
    - **Servo Motor:** A motor that can be commanded to move to a specific angle and hold it. Perfect for joints in a robotic arm.
    - **Stepper Motor:** A motor that moves in precise, discrete steps. Excellent for applications requiring very accurate positioning, like 3D printers.

- **Sensor Fusion:** The process of combining data from many different sensors to get a more accurate and reliable understanding of the environment than any single sensor could provide on its own.

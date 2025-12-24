
# Chapter 3: Exercises

Let's put your knowledge of sensors and actuators to the test.

### Exercise 1: Classify the Sensor

For each sensor listed below, decide if it is **Proprioceptive** (sensing the robot's own state) or **Exteroceptive** (sensing the outside world).

1.  **A camera on a drone:** (Proprioceptive / Exteroceptive)
2.  **A joint encoder that measures the angle of a robot's knee:** (Proprioceptive / Exteroceptive)
3.  **A microphone listening for voice commands:** (Proprioceptive / Exteroceptive)
4.  **An IMU that tells a walking robot it's starting to tip over:** (Proprioceptive / Exteroceptive)
5.  **A force sensor in a robot's fingertip:** (Proprioceptive / Exteroceptive)

### Exercise 2: Choose the Right Actuator

You are building a robot and need to choose the best actuator for the job. For each application, which would you choose: a **DC Motor**, a **Servo Motor**, or a **Stepper Motor**?

1.  **The joint of a robotic arm that needs to hold a specific, steady angle.**
    -   **Actuator Choice:** _________________________
    -   **Why?** _________________________________________________

2.  **The wheels of a small, fast-moving robot designed for a robot racing competition.**
    -   **Actuator Choice:** _________________________
    -   **Why?** _________________________________________________

3.  **The print head of a 3D printer that must be positioned with extreme precision.**
    -   **Actuator Choice:** _________________________
    -   **Why?** _________________________________________________

### Exercise 3: Design the "Sense-Act" Loop

Imagine you are designing a simple robot whose only job is to follow a black line on a white floor.

1.  **Sense:** What kind of sensor would you use to detect the black line? (Hint: Think about how the colors black and white interact with light).
2.  **Process:** What is the simple rule the controller would follow? (e.g., "If the sensor on the left sees white and the sensor on the right sees black, then...")
3.  **Act:** What actuators would the robot need to move, and how would the controller use them to stay on the line?

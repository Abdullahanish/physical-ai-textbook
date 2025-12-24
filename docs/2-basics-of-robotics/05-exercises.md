
# Chapter 2: Exercises

Time to apply what you've learned about the basics of robotics!

### Exercise 1: Count the Degrees of Freedom (DoF)

Look at the simple robotic arm below. Each arrow indicates a joint that can rotate in one direction. How many Degrees of Freedom does this robot have?

```mermaid
graph LR
    A[Base] -- 1. Rotate --> B(Link 1);
    B -- 2. Bend --> C(Link 2);
    C -- 3. Bend --> D(Link 3);
    D -- 4. Rotate Wrist --> E[Gripper];
```

-   **This robot has ______ Degrees of Freedom.**

### Exercise 2: Choose the Right Locomotion

You are designing a robot for each of the tasks below. Which type of locomotion (Wheeled, Legged, or Aerial) would be the best choice for each, and why?

1.  **A robot to deliver food and drinks to tables in a restaurant.**
    -   **Locomotion Type:** _________________________
    -   **Why?** _________________________________________________

2.  **A robot to search for lost hikers in a dense, mountainous forest.**
    -   **Locomotion Type:** _________________________
    -   **Why?** _________________________________________________

3.  **A robot to inspect the top of a very tall wind turbine for damage.**
    -   **Locomotion Type:** _________________________
    -   **Why?** _________________________________________________

### Exercise 3: Inverse Kinematics in Real Life

You perform inverse kinematics all the time without even thinking about it!

1.  **The Task:** Reach out and pick up a bottle of water from your desk.
2.  **Your Goal:** Your brain knows the final position where your hand needs to be.
3.  **The Problem:** Your brain has to solve the inverse kinematics problem. It needs to calculate the correct angles for your shoulder, elbow, and wrist joints to move your hand to the bottle.

**Question:** Describe another simple, everyday task you do that requires your brain to solve an inverse kinematics problem.
________________________________________________________________
________________________________________________________________

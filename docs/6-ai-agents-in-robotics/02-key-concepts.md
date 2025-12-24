
# Chapter 6: Key Concepts

This chapter covers the different software structures and learning methods that allow a robot to behave intelligently.

- **AI Agent:** An entity that perceives its environment through sensors and acts upon that environment through actuators to achieve a goal. A Physical AI is an agent with a body. The core of an agent is the function that maps perceptions to actions.

- **Perception-Action Loop:** The fundamental cycle of an agent: it perceives the world, thinks about what to do, and then takes an action, which in turn changes the world and its next perception.

- **State:** A complete description of the system at a particular point in time.
    - **World State:** The true state of the world (e.g., the exact position of all objects, people, and the robot). The robot almost never knows the full world state.
    - **Agent's State (or Belief State):** The robot's internal representation of the world, based on its sensor readings. This is an *estimation* of the world state.

- **State Estimation:** The process of using sensor data (which is always noisy and incomplete) to create the best possible guess of the current state of the world and the robot.

- **Simple Reflex Agent:** The most basic type of agent architecture. It maps sensor inputs directly to actions without considering past history. It follows simple "if-then" rules (e.g., "if bumper is pressed, then reverse and turn").

- **Model-Based Agent:** A more advanced agent that maintains an internal "model" of how the world works. It uses this model to predict how its actions will affect the world, allowing it to plan ahead.

- **Learning Agent:** An agent that can improve its performance over time through experience. Instead of having its decision-making logic programmed by a human, it learns from data.

- **Machine Learning (ML):** A subfield of AI that gives computers the ability to learn without being explicitly programmed.

- **Reinforcement Learning (RL):** A type of machine learning where an agent learns to behave in an environment by performing actions and seeing the results. It is the primary way modern robots learn complex behaviors.
    - **Agent:** The learner or decision-maker (the robot's brain).
    - **Environment:** The world the agent operates in.
    - **Action:** A possible move the agent can make.
    - **State:** The agent's current situation, as perceived from the environment.
    - **Reward:** A feedback signal from the environment. The agent's goal is to maximize the total reward it receives over time.

-   **Policy (π):** The "brain" of the RL agent. It is the strategy or function that the agent uses to choose an action given a particular state. The goal of reinforcement learning is to find the optimal policy—the one that maximizes the cumulative reward.

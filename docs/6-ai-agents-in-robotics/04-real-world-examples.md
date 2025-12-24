
# Chapter 6: Real-World Examples

The concepts of AI agents and learning are what give modern robots their "smarts." Let's see how they are applied in practice.

### 1. AlphaGo: A Purely Digital Learning Agent

- **What it is:** AlphaGo is the famous AI agent from DeepMind that learned to play the board game Go at a world-champion level. While not a *physical* AI, it is one of the clearest and most successful examples of a learning agent.
- **Agent Concepts in Action:**
    - **Agent:** The AlphaGo software.
    - **Environment:** The rules of the Go board.
    - **State:** The position of all the black and white stones on the board.
    - **Actions:** Placing a stone on any valid empty spot.
    - **Reward:** `+1` for winning the game, `-1` for losing the game.
    - **Learning:** AlphaGo was trained using a combination of supervised learning (by studying millions of human games) and reinforcement learning (by playing millions of games against itself).
    - **The Policy:** The result of this training was a highly advanced policy network that could look at any board state and determine the move most likely to lead to a win. This is a perfect example of a learned, rather than programmed, intelligence.

### 2. Autonomous Drones for Racing

- **What they are:** Researchers are training AI agents to fly quadcopter drones through complex race courses at incredible speeds, often faster than human pilots.
- **Agent Concepts in Action:**
    - **Agent:** The AI flight controller software on the drone.
    - **Environment:** A simulation of the drone and the race course. Training is done in simulation because crashing is "free."
    - **State:** The drone's position, velocity, and the data from its onboard camera.
    - **Actions:** The desired thrust for each of the four motors.
    - **Reward:** A large positive reward for finishing the course, with smaller positive rewards for passing through gates and negative rewards for hitting a wall or the ground.
    - **From Sim to Real:** After training for thousands of hours in simulation, the learned policy is transferred to a real drone. The agent has learned such a deep understanding of flight dynamics that it can apply its "knowledge" to the real world, controlling the drone with superhuman reflexes.

### 3. A Robotic Arm Learning to Grasp Objects

- **What it is:** Google and other research labs have set up large experiments where dozens of robotic arms work 24/7 to learn how to pick up a wide variety of objects.
- **Agent Concepts in Action:**
    - **Agent:** The AI software controlling the arm.
    - **Environment:** A bin filled with random objects (toys, tools, fruit, etc.).
    - **State:** The image from a camera looking down at the bin.
    - **Actions:** The position, orientation, and grip width for the robotic hand to attempt a grasp.
    - **Reward:** `+1` if the grasp is successful (detected by sensors in the gripper), `0` if it fails.
    - **Learning:** This is a massive reinforcement learning problem. Each arm attempts a grasp, records the image (state), the action it took, and the result (reward). All this data is fed into a single, shared neural network. Over millions of attempts, the network learns a policy that can look at an image of a bin of objects and determine the best way to pick one up. This is a move away from programmed grasping and towards a learned, general-purpose skill.

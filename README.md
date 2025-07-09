# Project Documentation: Reinforcement Learning Project (main.ipynb)

##  Overview
This project utilizes **Reinforcement Learning (RL)** to solve a problem using the **Deep Deterministic Policy Gradient (DDPG)** algorithm. It involves training an RL agent within the `Pendulum-v1` environment from the **OpenAI Gym** library.

---

##  Libraries & Installation

The project uses the following Python libraries:
- **gym** (v0.26.2): RL environment framework.
- **pygame**: For rendering (indirect dependency via gym).
- **torch**: Deep learning library for building neural networks.
- **numpy**: Numerical computing.

To install dependencies, the following commands are executed:
```bash
pip install gym==0.26.2 pygame torch numpy==1.23.5
```

---

##  Code Structure & Explanation

### 1. Importing Dependencies
Essential libraries are imported to handle the environment, neural networks, and mathematical operations.

### 2. Actor & Critic Networks
Two neural networks are defined:
- **Actor Network**: Maps states to actions.
- **Critic Network**: Estimates the value of state-action pairs.

Both use fully connected layers with ReLU activations.

### 3. Replay Buffer
A replay buffer is implemented to store past experiences `(state, action, reward, next_state, done)` for stable training.

### 4. OU Noise
Ornstein-Uhlenbeck noise is used for action exploration in continuous action spaces.

### 5. DDPG Agent
The agent class implements the DDPG algorithm, including:
- Action selection (with noise).
- Experience storage.
- Learning (Actor & Critic updates).
- Soft target updates.

### 6. Training Loop
The agent interacts with the environment for multiple episodes, learning from its experiences to minimize the environment’s penalty.

---

##  Key Functions & Methods

- **select_action()**: Selects an action with added exploration noise.
- **store()**: Saves experience into the buffer.
- **learn()**: Updates Actor and Critic networks using sampled experiences.
- **update_target()**: Soft updates target networks.

---

##  Environment: Pendulum-v1
This environment simulates a pendulum, where the agent tries to keep the pendulum upright while minimizing energy usage.

**Observation Space**: 3-dimensional (cos(theta), sin(theta), theta_dot)  
**Action Space**: Continuous force applied.

---

##  How to Run

1. Install dependencies (as shown above).
2. Run the notebook cells sequentially.
3. The agent will start training and display periodic logs.

---

##  Notes & Tips

- Ensure that the correct Python version and dependencies are used (some libraries have compatibility issues).
- Training might take several minutes depending on hardware.
- Modify hyperparameters like learning rates, buffer size, or noise for better performance.

---

## Strawberry Smart Farm Control using Reinforcement Learning

This project uses **Reinforcement Learning (RL)** to control temperature, humidity, and light in a strawberry smart farm.  
The agent learns how to manage the environment across different growth stages of strawberries to ensure optimal growth.

---

### Installation

pip install gymnasium
pip install numpy
pip install pandas
pip install matplotlib
pip install stable-baselines3

---
### Python Version
Python 3.11 (Google Colab)

___
### Algorithms Used
- PPO (Proximal Policy Optimization)
Stable, fast, and widely used for continuous control.

- SAC (Soft Actor-Critic)
Explores more, slower convergence, better long-term potential.

- DQN (Deep Q-Network)
Not suitable for continuous control → Discretized with custom wrapper.
Performance was unstable and low.

___

### Project Logic
1. Custom Environment

- StrawberryEnv simulates strawberry plant growth.

- Observations: temperature, humidity, light, stage, and time.

- Actions: adjust 3 values (scaled).

2. Reward Function

- +5: within optimal range

- +2: near-optimal

- -0.2: far from range

- Reward clipping is applied.

3. Training

- Trained using PPO, SAC, and DQN (with DiscreteActionWrapper)

- Each for 500,000 time steps.

4. Evaluation

Rewards plotted for comparison.

- PPO: fast and stable

- SAC: slower but better performance

- DQN: not effective


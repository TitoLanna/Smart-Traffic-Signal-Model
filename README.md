
---

# Q-Learning Traffic Light Control Simulation

This repository contains a Python implementation of a Q-learning algorithm for optimizing traffic light control at an intersection. The goal is to learn the optimal action to take at each state (traffic light phase) to maximize the total reward over time. Additionally, it includes a simple custom environment using OpenAI Gym for visualizing traffic flow using animated graphics.

## Overview

The Q-learning algorithm uses a **Q-table** to store the expected reward for each state-action pair. It updates the Q-table after each action based on the observed reward and the expected reward for the next state-action pair. This approach helps in determining the optimal policy for controlling traffic lights in a simulated environment.

### Key Components:

1. **Q-Learning Algorithm**:
    - A Q-table with 6 rows (corresponding to 6 traffic light states/phases) and 3 columns (corresponding to 3 actions: do nothing, switch to the next phase, switch to the previous phase).
    - The algorithm randomly selects a starting state and takes actions based on an epsilon-greedy policy.
    - After each action, the Q-table is updated using the Q-learning update rule:

      \[
      Q(s, a) = Q(s, a) + \alpha \times (r + \gamma \times \max(Q(s', a')) - Q(s, a))
      \]

      Where:
      - \( Q(s, a) \): Expected reward for taking action \( a \) in state \( s \)
      - \( \alpha \): Learning rate
      - \( r \): Observed reward for taking action \( a \) in state \( s \)
      - \( \gamma \): Discount factor
      - \( \max(Q(s', a')) \): Expected reward for the best action \( a' \) in the next state \( s' \)

2. **Traffic Light Control Environment**:
    - A custom OpenAI Gym environment (`TrafficLightEnv`) is created to simulate traffic lights and vehicle positions at an intersection.
    - It includes an animation of traffic light transitions using `matplotlib` to visualize the traffic flow and light changes.

## Installation

To run this project locally, follow the steps below:

1. **Clone the repository**:

    ```bash
    git clone https://github.com/yourusername/q-learning-traffic-light-control.git
    cd q-learning-traffic-light-control
    ```

2. **Install the required dependencies**:

    ```bash
    pip install numpy matplotlib gym
    ```

## Usage

### 1. Run Q-learning Simulation

You can run the Q-learning simulation to learn the optimal policy for traffic light control:

```bash
python q_learning_simulation.py
```

This will display the updated Q-table every 1000 iterations and a final heatmap visualization of the Q-table.

### 2. Run Traffic Light Environment Animation

You can run the custom environment with animated traffic light control using the following command:

```bash
python traffic_light_environment.py
```

This will display an animated plot showing the movement of cars and the changing traffic lights at the intersection.

## Project Structure

- `q_learning_simulation.py`: Contains the Q-learning algorithm for optimizing traffic light control.
- `traffic_light_environment.py`: Contains the custom environment using OpenAI Gym and animation code.
- `README.md`: Project overview and instructions.

## Q-Table Heatmap

The code generates a heatmap of the Q-table to visualize the expected reward for each state-action pair. The heatmap shows the expected reward for each combination of state and action as a colored square. The row labels represent the traffic light phases (states) and the column labels represent the possible actions:

- **States**: `State 0, State 1, State 2, State 3, State 4, State 5`
- **Actions**: `Do Nothing, Switch to Next Phase, Switch to Previous Phase`

## Animation Preview

The animation shows traffic light switching between different phases and the movement of cars based on the traffic light state. The goal is to optimize traffic flow and reduce waiting times at the intersection.

## Contributing

Feel free to contribute to this project by submitting issues or pull requests. Contributions are always welcome!

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgments

- [OpenAI Gym](https://github.com/openai/gym)
- [NumPy](https://numpy.org/)
- [Matplotlib](https://matplotlib.org/)

---


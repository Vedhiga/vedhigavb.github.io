# AI-Based Intelligent Power and Propulsion Management for Satellites Using Reinforcement Learning

> **Project Status:** Conceptual Proof-of-Concept

⚠️ **Disclaimer:** This project presents a conceptual simulation framework exploring the application of Reinforcement Learning (RL) for intelligent satellite power and propulsion management. The current implementation uses a simplified satellite environment and is intended for educational and exploratory research purposes.

---

# Overview

Modern satellites operate under strict power constraints. Energy generated through solar panels and stored in onboard batteries must be carefully allocated among critical subsystems such as communication, computation, payload operations, and propulsion.

This project investigates whether a Reinforcement Learning (Q-Learning) agent can autonomously learn operational policies that balance:

* Power efficiency
* Orbital stability
* Battery safety

The objective is to demonstrate the feasibility of AI-assisted decision-making for future autonomous spacecraft operations.

---

# Problem Statement

Orbit maintenance requires periodic propulsion maneuvers, which consume valuable onboard energy.

Inefficient power allocation can lead to:

* Reduced satellite lifetime
* Increased orbital drift
* Battery depletion risks
* Degraded mission performance

Traditional spacecraft controllers often rely on predefined rules. This project explores an adaptive learning-based approach capable of improving decisions through experience.

---

# Concept Model

The satellite is represented using a simplified operational environment.

### State Variables

The RL agent observes:

* Battery Level
* Orbit Error
* Power Consumption

### Available Actions

The agent selects one of the following actions:

* Idle
* Minor Thrust
* Full Thrust
* Charge Mode

Through repeated interaction with the environment, the agent learns policies that maximize long-term operational efficiency.

---

# System Architecture

**Figure 1. RL-Based Satellite Power and Propulsion Management Architecture**


<img width="1646" height="956" alt="Final architecture" src="https://github.com/user-attachments/assets/eae69116-a4f8-4798-9a6a-99606b81901e" />


---

# Optimization Equation

The decision-making process is modeled as a multi-objective optimization problem.

[
f = \alpha(PowerUsage) + \beta(OrbitError) + \gamma(BatteryRisk)
]

Where:

* **PowerUsage** = Energy consumed by satellite operations
* **OrbitError** = Deviation from desired orbital position
* **BatteryRisk** = Penalty associated with unsafe battery levels

The Reinforcement Learning reward function is defined as:

[
Reward = -f
]

This encourages the agent to:

* Minimize energy consumption
* Maintain orbital accuracy
* Protect battery health

---

# Reinforcement Learning Framework

The project uses **Tabular Q-Learning**.

The agent updates its knowledge using:

[
Q(s,a)=Q(s,a)+\alpha[r+\gamma\max Q(s',a')-Q(s,a)]
]

Where:

* (Q(s,a)) = Current estimate of action quality
* (r) = Immediate reward
* (\gamma) = Discount factor
* (\alpha) = Learning rate
* (s') = Next state

Over multiple training episodes, the Q-table converges toward improved decision-making policies.

---

# Results

## Performance Metrics

## Performance Metrics

| Metric | Value | Interpretation |
|---------|---------|---------|
| Reward Improvement | +249.8% | Significant learning improvement during training |
| Average Battery Level | 77.4% | Well above the 15% safety threshold |
| Average Orbit Error | 0.57 km | Meets the target of less than 1 km |
| Battery Safety Violations | 0 | No unsafe battery events occurred |
| Final Epsilon | 0.05 | Agent relies primarily on learned policy |


---

## Q-Table Visualization

**Figure 2. Q-Table Heatmap – Learned State-Action Values**


<img width="1983" height="793" alt="Final Q values" src="https://github.com/user-attachments/assets/c5d86584-ec31-46db-b26a-220887ebde76" />


---

## Simulation Statistics

```json
{
  "episodes": 600,
  "avg_reward_first50": -17.7536,
  "avg_reward_last50": 26.6024,
  "improvement_pct": 249.84,
  "best_reward": 35.5208,
  "final_epsilon": 0.05,
  "avg_battery_last_ep": 77.44,
  "avg_orbit_last_ep": 0.57,
  "battery_violations": 0
}
```

---

# Repository Structure

```text
satellite-power-propulsion-rl/
│
├── Report.pdf
├── README.md
├── source_code.py
├── simulation_stats.json
├── images/
│   ├── architecture.png
│   └── qtable_heatmap.png
├── requirements.txt
└── LICENSE
```

---

# Future Work

Potential extensions include:

* Realistic orbital mechanics simulations
* Solar charging and eclipse modeling
* Fuel consumption and delta-v analysis
* Deep Reinforcement Learning (DQN/PPO)
* Multi-satellite coordination
* Integration with spacecraft telemetry data

---

# Author

**Vedhiga V B**
B.E. Artificial Intelligence and Data Science
Avinashilingam University, Coimbatore

---


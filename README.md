# SmartLoopRL

# The Big Picture

<p align="center">
  <img src="https://github.com/Ngali-coder/Ngali-coder/blob/main/banner.png" alt="Ngali Abiru Banner" width="100%">
</p>

### Personalized Walking Route Recommendation using Proximal Policy Optimization (PPO) and OpenStreetMap

SmartLoopRL is an end-to-end Reinforcement Learning system that generates personalized walking-loop recommendations using real-world geospatial data from OpenStreetMap. The project formulates route recommendation as a Markov Decision Process (MDP) and trains a Proximal Policy Optimization (PPO) agent to recommend walking routes that closely match a user's desired walking duration while simultaneously maximizing scenic quality and route diversity.

# Project Overview

Traditional route recommendation systems rely on shortest-path algorithms or static heuristics, often ignoring user preferences and the sequential decision-making nature of route selection.

SmartLoopRL addresses this challenge by modeling personalized route recommendation as a Reinforcement Learning problem. Instead of selecting routes based solely on distance, the PPO agent continuously learns an optimal policy that balances multiple objectives:

- Walking duration accuracy
- Scenic attractiveness
- Route diversity
- User satisfaction

The project demonstrates how modern Reinforcement Learning can be integrated with Geographic Information Systems (GIS) to solve real-world recommendation problems.

# Problem Statement

Given a user's desired walking duration, automatically recommend the most suitable walking loop by learning an optimal navigation policy that minimizes duration error while maximizing route quality.

Unlike traditional optimization approaches, SmartLoopRL continuously improves its recommendations through interaction with a custom environment.

# Key Features

- Personalized walking-loop recommendation
- Custom Reinforcement Learning environment using Gymnasium
- PPO agent implementation with Stable-Baselines3
- OpenStreetMap road network integration
- Candidate route generation
- Multi-objective reward optimization
- Feature engineering for route quality assessment
- Interactive route visualization using Folium
- PPO learning curve analysis
- Performance evaluation and policy optimization

# System Workflow

```
User Desired Duration
          │
          ▼
OpenStreetMap Road Network
          │
          ▼
Candidate Loop Generation
          │
          ▼
Feature Engineering
(Duration • Scenic Score • Diversity)
          │
          ▼
Custom Gymnasium Environment
          │
          ▼
PPO Agent Training
          │
          ▼
Policy Optimization
          │
          ▼
Recommended Walking Route
```

---

# Reinforcement Learning Formulation

## State Space

Each environment state represents a candidate walking route described by engineered features including:

- Duration error
- Scenic score
- Route diversity
- Proposal count
- Additional normalized route characteristics

## Action Space

The PPO agent selects between available candidate routes by deciding whether to:

- Accept a route
- Reject a route and evaluate another candidate

## Reward Function

The reward function combines multiple objectives:

- Minimize walking duration error
- Maximize scenic quality
- Encourage route diversity
- Penalize poor route selections

This multi-objective reward design enables the PPO agent to learn realistic route recommendation behavior.

## Episode Termination

An episode terminates when:

- An acceptable walking loop is selected
- Maximum proposal attempts are reached
- Environment truncation conditions occur

---

# Technology Stack

**Programming**

- Python

**Reinforcement Learning**

- Stable-Baselines3
- PPO (Proximal Policy Optimization)
- Gymnasium

**Machine Learning**

- PyTorch

**Geospatial Analysis**

- OpenStreetMap
- OSMnx
- NetworkX

**Visualization**

- Folium
- Matplotlib

**Data Processing**

- NumPy
- Pandas

# Project Structure

```
SmartLoopRL/

├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── notebooks/
├── src/
├── images/
├── results/
├── docs/
└── demo/
```

---

# Installation

Clone the repository

```bash
git clone https://github.com/Ngali-coder/SmartLoopRL.git

cd SmartLoopR
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# Usage

Run the notebook inside the `notebooks` directory to:

- Generate candidate walking loops
- Train the PPO agent
- Evaluate learned policies
- Visualize accepted routes
- Analyze learning curves

---

# Results

The trained PPO agent successfully learns high-quality walking-loop recommendation policies by balancing:

- Walking duration accuracy
- Scenic route preference
- Route diversity

The optimization process demonstrates steady policy improvement throughout training, with reward convergence indicating successful learning.

The repository includes:

- PPO learning curves
- Reward progression
- Evaluation metrics
- Accepted vs rejected route visualizations
- Interactive walking maps

# Visualizations

The project provides several visual analyses including:

- Walking route maps
- Candidate route comparison
- PPO learning curves
- Mean episode reward progression
- Best reward evolution
- Policy evaluation metrics

---

# Limitations

Current limitations include:

- Single-user preference modeling
- Static road network assumption
- Limited environmental context (weather, traffic, safety)
- Single-agent recommendation framework

---

# Future Improvements

Potential future work includes:

- Multi-user personalization
- Real-time GPS integration
- Multi-objective reinforcement learning
- Human preference learning
- Context-aware recommendations
- Deep graph neural networks for route representation
- Deployment as a FastAPI service
- Mobile application integration

# License

This project is released under the MIT License.

# Author

**Ngali Abiru**

AI Engineer | Machine Learning Engineer | Data Engineer

Master of Artificial Intelligence in Digital Health  
Vrije Universiteit Brussel

⭐ If you found this project interesting, consider starring the repository.

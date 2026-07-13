# Results and Findings

## Overview

The SmartLoopRL framework successfully demonstrated that reinforcement learning can be applied to personalized walking-route recommendation using real-world road network data from OpenStreetMap.

A custom Gymnasium environment was developed in which a PPO agent learned to recommend walking loops that closely matched a user's preferred walking duration while simultaneously maximizing scenic quality and route diversity.

Unlike traditional shortest-path algorithms, the agent continuously improved its recommendation policy through interaction with the environment.

# Environment Construction

The walking environment was successfully generated from OpenStreetMap using OSMnx.

The resulting navigation graph contained:

| Property | Value |
|----------|------:|
| Graph Type | MultiDiGraph |
| Road Network Nodes | **989** |
| Road Network Edges | **2604** |
| Navigation Source | OpenStreetMap |

Candidate walking loops were generated using shortest-path searches through randomly sampled intermediate waypoints, producing diverse route alternatives for reinforcement learning. :contentReference[oaicite:1]{index=1}

# PPO Training Performance

The PPO agent demonstrated steady policy improvement throughout training.

Initially, the agent explored candidate walking loops almost randomly. As training progressed, the learned policy increasingly selected routes that better satisfied the optimization objectives.

The training reward exhibited:

- Rapid improvement during early learning
- Progressive stabilization as the policy matured
- Convergence toward a consistent recommendation strategy
- Stable learning despite stochastic candidate generation

The mean episode reward converged around **1.5–1.6**, indicating that the learned policy consistently identified high-quality walking loops. :contentReference[oaicite:2]{index=2}

# Policy Optimization

Analysis of the cumulative best reward showed continuous improvement throughout training.

Rather than plateauing immediately, the PPO agent continued discovering better recommendation strategies over successive episodes before converging toward an optimal policy.

This behaviour indicates that:

- Exploration remained effective during training.
- The reward function successfully guided policy improvement.
- PPO maintained stable optimization without catastrophic policy collapse. :contentReference[oaicite:3]{index=3}

# Recommendation Behaviour

The trained agent learned to balance multiple competing objectives simultaneously.

Instead of optimizing only walking distance, the final recommendation policy considered:

- Walking duration accuracy
- Scenic route quality
- Route diversity
- Recommendation efficiency

The learned policy progressively rejected low-quality candidate loops while accepting routes that better satisfied the multi-objective reward function.

Final route visualizations showed that, after several evaluation episodes, the agent consistently selected a compact, high-quality walking loop while rejecting less suitable alternatives. :contentReference[oaicite:4]{index=4}

# Key Findings

The experiments demonstrated several important observations.

| Finding | Observation |
|---------|-------------|
| Stable Learning | PPO successfully converged without unstable reward oscillations. |
| Effective Exploration | Random waypoint sampling enabled the agent to explore diverse candidate routes. |
| Reward Engineering | The multi-objective reward function successfully balanced duration accuracy, scenic quality, and diversity. |
| Policy Improvement | Mean episode rewards increased steadily before stabilizing. |
| Route Quality | Final recommendations closely matched the desired walking duration while preserving scenic value. |
| General Framework | The environment can easily be extended with additional user preferences and contextual information. |


# Project Deliverables

The project successfully produced:

- A complete custom Gymnasium reinforcement learning environment
- PPO-based route recommendation agent
- OpenStreetMap road-network integration
- Automatic candidate loop generation
- Reward-engineering framework
- Interactive Folium route visualization
- PPO training statistics
- Episode reward analysis
- Policy evaluation workflow


# Visual Results

The project generates several visual outputs that illustrate both the environment and the learning process.

These include:

- OpenStreetMap road-network visualization
- Generated walking-loop candidates
- PPO learning curve
- Mean episode reward progression
- Best reward discovered during training
- Accepted versus rejected walking loops
- Final recommended walking route

<p align="center">
  <img src="https://github.com/Ngali-coder/SmartLoopR/blob/main/results/ppo%20learning%20curve.png" alt="Ngali Abiru Banner" width="100%">
</p>

- you can find the rest of these figures in the pdf version of the notebook uploaded

These figures provide clear evidence that the reinforcement learning agent progressively improves its route recommendation strategy throughout training.

# Final Conclusion

The SmartLoopRL project demonstrates that reinforcement learning can be successfully applied to personalized route recommendation using real-world geographic data.

By combining OpenStreetMap, graph-based route generation, custom reward engineering, and PPO, the system learns an adaptive recommendation policy capable of balancing multiple user preferences rather than optimizing a single objective.

The project establishes a strong foundation for future intelligent navigation systems capable of incorporating additional contextual information such as weather, terrain difficulty, pedestrian traffic, safety, accessibility, and real-time user feedback.

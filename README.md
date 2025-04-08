# SeqPolicy: Sequential Control Policy for Multiple Peg-in-Hole Assembly

![Framework Overview](./images/framework_diagram.png) <!-- You can replace this with your own diagram -->

## Overview

**SeqPolicy** is a modular reinforcement learning framework designed for high-precision, multi-hole **peg-in-hole assembly tasks**. The system integrates a sequential control strategy and contrastive self-supervised learning (CSSL) to improve performance and generalization in robotic assembly operations.

This project was developed to address the challenges in real-world industrial automation where multiple-hole insertions are needed in a fixed order, such as wire harness assembly.

## Key Features

- 🧠 **Reinforcement Learning (RL)-based sequential controller**: Trains separate control policies for each insertion stage.
- 🔀 **Stage-wise policy execution**: Implements multiple sub-policies sequentially for multi-step assembly.
- 🧲 **Contrastive Self-Supervised Learning (CSSL)**: Improves data efficiency and task generalization using visual representation learning.
- 🎯 **High-precision performance**: Achieves ≤0.5mm tolerance in physical experiments.
- 🛠 **Sim-to-Real Transfer**: Demonstrates robustness in both Isaac Sim and real-world settings.

## Architecture

The SeqPolicy framework consists of:
1. **Pretraining** of visual encoders using contrastive learning on unlabeled image pairs.
2. **Stage-specific RL policy training** using PPO for each hole insertion step.
3. **Sequential policy execution** on robot agents in both simulation and real environments.

## Directory Structure


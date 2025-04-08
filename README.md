# SeqPolicy: Sequential Control Policy for Multiple Peg-in-Hole Assembly

https://github.com/user-attachments/assets/089565aa-9086-446f-9a78-f2206c164b93

[align_insert.webm](https://github.com/user-attachments/assets/f93f0088-5ba8-422f-a071-dc2b1a6f1c36)

## Abstract
Robotic assembly is widely utilized in large-scale manufacturing due to its high production efficiency, and the peg-in-hole assembly is a typical operation. While single peg-in-hole tasks have achieved great performance through reinforcement learning (RL) methods, multiple peg-in-hole assembly remains challenging due to complex geometry and physical constraints. To address this, we introduce a control policy workflow for multiple peg-in-hole assembly, dividing the task into three primitive sub-tasks: picking, alignment, and insertion to modularize the long-term task and improve sample efficiency. Sequential control policy (SeqPolicy), containing three control policies, is used to implement all the sub-tasks step-by-step. This approach introduces human knowledge to manage intermediate states, such as lifting height and aligning direction, thereby enabling flexible deployment across various scenarios. SeqPolicy demonstrated higher training efficiency with faster convergence and a higher success rate compared to the single control policy. Its adaptability is confirmed through generalization experiments involving objects with varying geometries. Recognizing the importance of object pose for control policies, a low-cost and adaptable method using visual representation containing objects’ pose information from RGB images is proposed to estimate objects’ pose in robot base frame directly in working scenarios. The representation is extracted by a Siamese-CNN network trained with self-supervised contrastive learning. Utilizing it, the alignment sub-task is successfully executed. These experiments validate the solution’s reusability and adaptability in multiple peg-in-hole scenarios.

## Pipeline

![pipeline](https://github.com/user-attachments/assets/df53e719-d8f2-4f4d-bc34-9c3156f9db44)


**SeqPolicy** is a modular reinforcement learning framework designed for high-precision, multi-hole **peg-in-hole assembly tasks**. The system integrates a sequential control strategy and contrastive self-supervised learning (CSSL) to improve performance and generalization in robotic assembly operations.

This project was developed to address the challenges in real-world industrial automation where multiple-hole insertions are needed in a fixed order, such as wire harness assembly.

## Policy Learning
The policy learning is efficient with quick and reproducable convergence.

![policy_learning](https://github.com/user-attachments/assets/879ef321-a9a4-4303-8509-22558f61101e)

## Architecture

The SeqPolicy framework consists of:
1. **Pretraining** of visual encoders using contrastive learning on unlabeled image pairs.
2. **Stage-specific RL policy training** using PPO for each hole insertion step.
3. **Sequential policy execution** on robot agents in both simulation and real environments.

## BibTeX

<pre> 
@article{Liu2024, 
author = {Xinyu Liu and Chao Zeng and Chenguang Yang and Jianwei Zhang},
title = {Reinforcement Learning-Based Sequential Control Policy for Multiple Peg-in-Hole Assembly},
year = {2024},
journal = {CAAI Artificial Intelligence Research},
volume = {3},
pages = {9150043},
keywords = {deep reinforcement learning, multiple peg-in-hole assembly, self-supervised contrastive learning},
url = {https://www.sciopen.com/article/10.26599/AIR.2024.9150043},
doi = {10.26599/AIR.2024.9150043},
}
</pre>





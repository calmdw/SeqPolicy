# SeqPolicy: Reinforcement Learning-Based Sequential Control Policy for Multiple Peg-in-Hole Assembly

<div style="display: flex; justify-content: center; gap: 20px;">
  <video width="45%" controls>
    <source src="https://github.com/user-attachments/assets/d982fea1-155d-4a06-9eeb-02cdd2131ed4" type="video/webm">
    Your browser does not support the video tag.
  </video>
  <video width="45%" controls>
    <source src="https://github.com/user-attachments/assets/f93f0088-5ba8-422f-a071-dc2b1a6f1c36" type="video/webm">
    Your browser does not support the video tag.
  </video>
</div>

<div style="display: flex; gap: 20px; justify-content: center; flex-wrap: wrap;">
  <img src="https://github.com/calmdw/SeqPolicy/blob/main/Pick.gif" width="45%">
  <img src="https://your-repo.github.io/assets/align_insert.gif" width="45%">
</div>


---

## Abstract
Robotic assembly is widely utilized in large-scale manufacturing due to its high production efficiency, and the peg-in-hole assembly is a typical operation. While single peg-in-hole tasks have achieved great performance through reinforcement learning (RL) methods, multiple peg-in-hole assembly remains challenging due to complex geometry and physical constraints. To address this, we introduce a control policy workflow for multiple peg-in-hole assembly, dividing the task into three primitive sub-tasks: picking, alignment, and insertion to **modularize** the long-term task and improve sample efficiency. Sequential control policy (SeqPolicy), containing three control policies, is used to implement all the sub-tasks step-by-step. This approach introduces human knowledge to **manage intermediate states**, such as lifting height and aligning direction, thereby enabling **flexible deployment across various scenarios**. SeqPolicy demonstrated higher training efficiency with **faster convergence and a higher success rate** compared to the single control policy. Its adaptability is confirmed through generalization experiments involving objects with **varying geometrie**s. Recognizing the importance of object pose for control policies, a low-cost and adaptable method using visual representation containing objects’ pose information from RGB images is proposed to estimate objects’ pose in robot base frame directly in working scenarios. The representation is extracted by a Siamese-CNN network trained with self-supervised contrastive learning. Utilizing it, the alignment sub-task is successfully executed. These experiments validate the solution’s **reusability** and **adaptability** in multiple peg-in-hole scenarios.


## 🧩 Modular Policy Pipeline

<p align="center">
  <img src="https://github.com/user-attachments/assets/df53e719-d8f2-4f4d-bc34-9c3156f9db44" width="80%" alt="Pipeline">
</p>

---

## ⚙️ Simulation Environment Variables

| Variable               | Range             |
|------------------------|------------------|
| Grasp state            | Uncertain         |
| Object position offset | ±0.18 m           |
| Object rotation offset | ±0.22 rad         |
| Gravity variation      | ±0.02 m/s²        |
| Object mass            | 0.2 – 0.3 kg      |
| Joint stiffness        | ±0.1              |
| Joint damping          | ±0.1              |

---

## 📈 Policy Training Performance

<p align="center">
  <img src="https://github.com/user-attachments/assets/879ef321-a9a4-4303-8509-22558f61101e" width="80%" alt="Policy Learning Curve">
</p>

---

## 🔬 Ablation Study: Impact of Observations

| Observations Used                                           | Success Rate |
|-------------------------------------------------------------|--------------|
| Peg pose, EEF pose, hole pose, hand force                   | 0.912        |
| Peg pose, hole position                                     | 0.898        |
| Joint angle, hole position, hand force                      | 0.882        |
| EEF pose, hole position                                     | 0.497        |
| Joint angle, hole position                                  | 0.514        |
| Joint angle, hand force                                     | 0.012        |

---

## 🧪 Generalization to Unseen Geometries

<p align="center">
  <img src="https://github.com/user-attachments/assets/d128fd65-153d-4593-ac69-0566b851627b" width="80%" alt="Generalization Test">
</p>

| Geometry   | Success Rate |
|------------|--------------|
| Square     | 0.868        |
| Triangle   | 0.787        |
| Ellipse    | 0.901        |

---

## 📚 Citation

```bibtex
@article{Liu2024, 
  author  = {Xinyu Liu and Chao Zeng and Chenguang Yang and Jianwei Zhang},






# SeqPolicy: Reinforcement Learning-Based Sequential Control Policy for Multiple Peg-in-Hole Assembly

[Pick.webm](https://github.com/user-attachments/assets/d982fea1-155d-4a06-9eeb-02cdd2131ed4)

[align_insert.webm](https://github.com/user-attachments/assets/f93f0088-5ba8-422f-a071-dc2b1a6f1c36)



## Pipeline

![pipeline](https://github.com/user-attachments/assets/df53e719-d8f2-4f4d-bc34-9c3156f9db44)

## Training Configuration
\begin{tabhere}
\centering
\caption{\centering Simulation Environment Variables}
\setlength{\tabcolsep}{6.6mm}%{6.6mm}{% Change this value to adjust the width of the table.
\begin{tabular}{cc}
    \toprule% Tables with three horizontal lines are recommended.
    Variables & Range \\ %& Direction\\
    \midrule
    grasp state    & uncertain \\   %  & along peg's side\\
    object initial position  & $\pm{0.18 m}$ \\
    object initial rotation  & $\pm{0.22 radian}$\\
    gravitational acceleration   & $\pm{0.02 m/s^2} $\\
    mass   &    $0.2-0.3$\\
joint stiffness  & $\pm{0.1}$  \\
    joint damping  & $\pm{0.1}$  \\
    \bottomrule
\end{tabular}
\label{tab: Simulation Environment Variables}%
\end{tabhere}%

## Policy Learning
The policy learning is efficient with quick and reproducable convergence.

![policy_learning](https://github.com/user-attachments/assets/879ef321-a9a4-4303-8509-22558f61101e)

## Ablation experiment on different observations
\begin{tabhere}
    \centering
    \caption{\centering Ablation Experiment Result}
    \setlength{\tabcolsep}{3.3mm}%{6.6mm}{% Change this value to adjust the width of the table.
    \begin{tabular}{cc}
        \toprule% Tables with three horizontal lines are recommended.
        Observation & Sucess Rate \\ %& Direction\\
        \midrule
        peg pose, eef pose, hole pose, hand force & 0.912 \\
        peg pose, hole position & 0.898 \\
        joint angle, hole position, hand force & 0.882 \\
        eef pose, hole position & 0.497 \\
        joint angle, hole position & 0.514 \\
        joint angle, hand force & 0.012 \\
        \bottomrule
    \end{tabular}%
    \label{tab: ablation experiment}%
    \end{tabhere}

## Gernalization test on unseen geometry
![generalization_test](https://github.com/user-attachments/assets/d128fd65-153d-4593-ac69-0566b851627b)

\begin{tabhere}
        \centering
        \caption{\centering Success Rate of Generalization Test}
        \setlength{\tabcolsep}{6.6mm}%{6.6mm}{% Change this value to adjust the width of the table.
        \begin{tabular}{cc}
            \toprule% Tables with three horizontal lines are recommended.
            Geometry & Success Rate \\ %& Direction\\
            \midrule
            Square    & 0.868\\   %  & along peg's side\\
            Triangle  & 0.787\\
            ellipse   & 0.901\\
            \bottomrule
        \end{tabular}%

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





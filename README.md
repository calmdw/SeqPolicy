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
  <img src="https://github.com/calmdw/SeqPolicy/blob/main/align_insert.gif" width="45%">
</div>

---

## Abstract
Robotic assembly is widely utilized in large-scale manufacturing due to its high production efficiency, and the peg-in-hole assembly is a typical operation. While single peg-in-hole tasks have achieved great performance through reinforcement learning (RL) methods, multiple peg-in-hole assembly remains challenging due to complex geometry and physical constraints. To address this, we introduce a control policy workflow for multiple peg-in-hole assembly, dividing the task into three primitive sub-tasks: picking, alignment, and insertion to **modularize** the long-term task and improve sample efficiency. Sequential control policy (SeqPolicy), containing three control policies, is used to implement all the sub-tasks step-by-step. This approach introduces human knowledge to **manage intermediate states**, such as lifting height and aligning direction, thereby enabling **flexible deployment across various scenarios**. SeqPolicy demonstrated higher training efficiency with **faster convergence and a higher success rate** compared to the single control policy. Its adaptability is confirmed through generalization experiments involving objects with **varying geometrie**s. Recognizing the importance of object pose for control policies, a low-cost and adaptable method using visual representation containing objects’ pose information from RGB images is proposed to estimate objects’ pose in robot base frame directly in working scenarios. The representation is extracted by a Siamese-CNN network trained with self-supervised contrastive learning. Utilizing it, the alignment sub-task is successfully executed. These experiments validate the solution’s **reusability** and **adaptability** in multiple peg-in-hole scenarios.


## Overview Pipeline

![overview](https://github.com/user-attachments/assets/9a4e68b3-88c2-4ddb-8546-a1759d26e27a)

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

<div style="display: flex; gap: 24px; align-items: flex-start; flex-wrap: wrap;">

  <!-- Generalization image -->
  <img src="https://github.com/user-attachments/assets/d128fd65-153d-4593-ac69-0566b851627b" alt="Generalization Test" width="50%" style="border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">

  <!-- Success Rate Table -->
  <div style="flex: 1; min-width: 260px;">
    
  <h4>📊 Success Rate of Generalization Test</h4>
  
  <table>
    <thead>
      <tr>
        <th>Geometry</th>
        <th>Success Rate</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Square</td>
        <td>0.868</td>
      </tr>
      <tr>
        <td>Triangle</td>
        <td>0.787</td>
      </tr>
      <tr>
        <td>Ellipse</td>
        <td>0.901</td>
      </tr>
    </tbody>
  </table>

  </div>
</div>

<p align="center">
  <img src="https://github.com/user-attachments/assets/d128fd65-153d-4593-ac69-0566b851627b" width="80%" alt="Generalization Test">
</p>

| Geometry   | Success Rate |
|------------|--------------|
| Square     | 0.868        |
| Triangle   | 0.787        |
| Ellipse    | 0.901        |

---

## 📚 BibTeX
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



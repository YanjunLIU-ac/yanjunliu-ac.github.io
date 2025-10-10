---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
redirect_from:
  - /project
---

{% include base_path %}

## Optimal Control of RCM-constrained Redundant Manipulator in RA-MIS
* 08/2022 - 09/2023

Robot-Assisted Minimally Invasive Surgery (RA-MIS) uses long and slender surgical tools (e.g., endoscope) rigidly mounted on the robot's end-effector, which are controlled by the surgeon via a hands-on or tele-operation setup. During a RA-MIS, the surgical tool performs tasks inside the patient’s body. Simultaneously, the tool movements are constrained by the trocar where the position deviation must be minimized, in order to avoid any injury to the patient. The kinematic constraint discussed above is commonly known as the Remote Center of Motion (RCM) constraint. The detailed illustration of RA-MIS components is shown in Figure 1.

<p align="center">
  <img width="35%" src="../assets/rcm.png">
</p>
<center>Figure 1. Representation of a typical RA-MIS system [1].</center>

In this project, the primary research topics include a variety of relevant control and planning tasks:
+ admittance control
+ hybrid force-impedance control
+ reactive manipulability-maximizing motion control
+ motion control of rigid-flexible integrated and soft instruments

The kinematically redundant Emika Frank Panda manipulator is used to study. Our work targets the following two applications:

(a) QP-based admittance control in hands-on RA-MIS

By decomposing the cartesian space into a free motion space and a constraint space under RCM-constraint, we formulated hands-on admittance control as a Quadratic Programming (QP) Problem. The redundant manipulator’s nullspace enables the optimization of multiple tasks simultaneously. We also proposed to model trocar position along the tool axis as a virtual prismatic joint to restrict the instrument’s radial motion. A running demo is shown in Figure 2.

<p align="center">
  <img width="70%" src="../assets/qp_demo.gif">
</p>

<center>Figure 2. Demo of admittance control in hands-on RA-MIS. </center>

(b) Prototype of compliant robot-assisted laparoscope-holder system

The proposed laparoscope-holder system aims to keep the instrument’s tip (represented as the green ball in Figure 3) within the camera horizon. By exploiting the nullspace of redundant manipulators, it features compliant tasks such as reducing the interaction forces at the trocar position, avoiding sudden gestures and restricting elbow motion. To be specific, our system consists of the task-space compliance control (RCM constraint), the nullspace compliance control (elbow motion) and MoCap system with instrument locating algorithm (not shown here). A running demo is shown in Figure 3. 

<p align="center">
  <img width="60%" src="../assets/laparoscope_demo.gif">
</p>
<center>Figure 3. Demo of robot-assisted laparoscope-holding system. </center>

References:

[1] Sandoval, J., Pierre Vieyres, and Gérard Poisson. "Generalized framework for control of redundant manipulators in robot-assisted minimally invasive surgery." IRBM 39.3 (2018): 160-166.

## Teaching-by-Demonstration Scheme for Robotic Compliant Skills
* 03/2022 - 06/2022
* Faculty of Robot Science and Engineering, Northeastern University
* Advisor: Prof. Lijin Fang

This project aims to investigate the method for demonstrating and teaching robotic compliant skills. Its primary contents include dynamic parameter identification, compliant dragging, and trajectory tracking. Our experiment platform is based on the Rokae xMate3Pro manipulator.

<p align="center">
<iframe width="336" height="189" src="https://www.youtube.com/embed/0tn974odp6Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</p>

For the identification portion, we modeled the robot's dynamics using 13 parameters per joint, including Coulomb friction. A Fourier-series based excitation trajectory and Least Squares Method were used for parameter identification. The experimental results indicated that the root Mean Square Error between the calculated and actual torque of each joint was within 0.5Nm.

<p align="center">
  <img width="60%" src="../assets/flowchart.png">
</p>
<center>Figure 1. Dynamic parameter identification flowchart. </center>

For the compliant dragging portion, we devised a variable admittance scheme based on the operator's direct and indirect intentions. The scheme can adjust the virtual damping to modulate the dragging speed based on the operator's intent, while predicting the operator's desired force direction by calculating the path's curvature to guide the operator. The experiments show that the variable damping method can improve dragging precision and reduce dragging time. Variable admittance scheme is capable of making the manipulator respond rapidly to the operator's intent and correcting dragging errors and jitter compared to constant damping scheme. Some of the system details are shown below.

<p align="center">
  <img width="80%" src="../assets/vadmit_pic1.png">
</p>
<center>Figure 2. Variable admittance control strategy. </center>

<p align="center">
  <img width="80%" src="../assets/vadmit_pic2.png">
</p>
<center>Figure 3. Variable admittance control experiments & results. </center>

For the trajectory tracking portion, we used the Time Delay Estimation (TDE) method in combination with Sliding Mode Controller (SMC) to improve the tracking accuracy. Experiments were conducted to track the target dragging trajectory using the proposed controller, and the tracking error of each joint was reduced to within 1e-3 radians.

[[Project Thesis (Complete)](https://www.jianguoyun.com/p/DQAfQGgQkOm1CRjAi_cEIAA)]
[[Thesis on Dynamic Identification](https://www.jianguoyun.com/p/DUbc1G0QkOm1CRjKi_cEIAA)]
[[Code](https://github.com/YanjunLIU-ac/Dynamic_Parameter_Identification_for_Rokae_xMate)]


## Indoor 3D Scene Understanding and Modelling
* 08/2020 - 08/2021
* Publication: **Y. Liu**, and W. Yang*, "Explicit3D: Graph Network with Spatial Inference for Single Image 3D Object Detection," Signal Processing: Image Communication, vol. 124, pp. 117120, 2024. [[URL](https://www.sciencedirect.com/science/article/pii/S0923596524000213)]
* Visual Information Processing Lab, SIGS, Tsinghua University
* Advisor: Prof. Wenming Yang

<p align="center">
  <img width="80%" src="../assets/preface_intro.png">
</p>

The detection of indoor 3D objects is a crucial component of single-image scene comprehension, with profound effects on spatial cognition and visual reasoning. Existing works on 3D object detection from a single image either independently predict each object or implicitly reason over all possible objects, failing to exploit relational geometric information between objects. To address this issue, we propose Explicit3D, a dynamic sparse graph pipeline based on object geometry and semantic properties. Considering efficiency, we define a relatedness score and design a novel dynamic pruning algorithm followed by a cluster sampling technique for sparse scene graph generation and updating. In addition, Explicit3D introduces homogeneous matrices and defines new relative loss and corner loss in order to explicitly model the spatial difference between target pairs. Instead of using ground-truth labels as direct supervision, our relative and corner loss are derived from the homogeneous transformation, which allows the model to discover the geometric consistency between objects. The experimental results on the SUN RGB-D dataset demonstrate that Explicit3D achieves a better performance-complexity balance than the current state of the art.

<p align="center">
  <img width="80%" src="../assets/graph_overview.png">
</p>

[[Bachelor Thesis](https://www.jianguoyun.com/p/DcQ3d_IQkOm1CRjFi_cEIAA)]
[[arxiv](https://arxiv.org/abs/2302.06494)]

## sEMG-based Sign Language Recognition for the Hearing-impaired
* 03/2019 - 05/2020
* Human-Robot Collaboration Lab, Faculty of Robot Science and Engineering, Northeastern University
* Publication: one paper in IEEE ROBIO, one paper in IEEE CYBER, one paper in Applied Intelligence
* Advisor: Prof. Fei Wang

<p align="center">
  <img width="30%" src="../assets/myo.jpg">
  <img width="32%" src="../assets/semg.jpg">
</p>

This research aims to develop a Sign Language Recognition (SLR) system to assist the hearing-impaired and to inspire future studies on human-robot collaboration. We captured sign language signals using Myo armbrand (shown on the left) embedded with sEMG(surface-electromyogram)sensors and IMU (inertial measurement unit) (shown on the right). The central idea of this project is to develop a method for classifying sign language words and translating sign sentences using multimodal information fusion.

We proposed a 1D-CNN as the baseline for signal fusion, achieving an accuracy of 96% on a laboratory-constructed dataset of 200 words with approximately 10,000 samples from 20 participants. In addition, several derivative works on the integration system of sign language and visual speech (ROBIO Paper), data generation and amplification (CYBER Paper), and few-shot learning (Applied Intelligence Paper) have been published. Our project has been awarded the Silver Prize in the fifth "Internet Plus" Innovation and Entrepreneurship Competition.

[[IEEE ROBIO Paper](https://ieeexplore.ieee.org/abstract/document/8961831/)]
[[IEEE CYBER Paper](https://ieeexplore.ieee.org/abstract/document/9279125/)]
[[Applied Intelligence Paper](https://link.springer.com/article/10.1007/s10489-020-02170-9)]
[[Competition News](http://www.rse.neu.edu.cn/2019/1016/c2146a145673/page.htm)]


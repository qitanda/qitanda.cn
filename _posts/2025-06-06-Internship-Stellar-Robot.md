---
title: 'Dexterous Algorithm Intern in Stellar-Robot'
date: 2025-08-23
permalink: /projects/Stellar-Robot/
excerpt: "Three-month internship in dexterous manipulation: GeoRT hand retargeting, Realman arm kinematics, camera-to-robot calibration, and garment imitation learning with SAM2 perception and diffusion policies."
tags:
  - Dexterous Hand
  - Imitation Learning
  - Robot Perception and Control
author_profile: false
header:
  teaser: projects/Stellar-Robot/product.png
share: false
project_order: 5
---

During my three-month internship at **Stellar-Robot**, I adapted dexterous manipulation methods to **GaiaHand, PantheonHand, and Realman-75f**, focusing on hand retargeting and garment imitation learning.

## Overview

![Dexterous robot platform](/images/projects/Stellar-Robot/product.png)

My work connected hand retargeting, robot kinematics, calibrated RGB-D perception, and garment-policy training across simulation and real-robot experiments.

## GeoRT-Based Hand Retargeting

Adapted **GeoRT** to GaiaHand and PantheonHand through robot-specific fingertip keypoints and joint mappings. Computed offsets in each finger link's local frame and calibrated hand-size scaling to accommodate differences in human and robot geometry. Verified alignment and motion transfer through forward kinematics and SAPIEN replay.

<video controls playsinline preload="none" poster="/images/projects/Stellar-Robot/retargeting-poster-v2.jpg" style="width:100%;height:auto;" aria-label="GeoRT-based dexterous hand retargeting demonstration">
  <source src="/files/Stellar-Robot/retargeting-demo-v2.mp4" type="video/mp4">
  <a href="/files/Stellar-Robot/retargeting-demo-v2.mp4">Watch the hand retargeting demonstration</a>.
</video>

*Human-to-robot hand motion retargeting based on GeoRT.*

## Arm Kinematics and Extrinsic Calibration

Built a **MoveIt 2** kinematics interface for the seven-joint Realman-75f, supporting **KDL numerical IK and IKFast analytical IK**. Initialized inverse kinematics from measured joint states to account for the current arm configuration.

Integrated hand–eye calibration with a **ROS 2 TF** tree linking the camera and both arm bases, transforming visual grasp targets into the appropriate robot frame for motion execution.

## Garment Imitation Learning

Adapted **DexGarmentLab** in Isaac Sim for robot control, demonstration collection, and imitation-policy training and evaluation.

- **Grasp-point correspondence:** GAM matches learned point descriptors between a reference garment and the current point cloud, transferring manipulation points through cosine similarity.
- **Structure-aware policy inputs:** Combined garment geometry and grasp-affordance features with scene point clouds and robot state to condition diffusion-based action prediction.
- **Robot adaptation:** Integrated arm and hand models with the learning workflow and built a Realman-75f + GaiaHand platform for garment-grasping experiments.

## SAM2-Based Garment Perception

Integrated **SAM2** with aligned RealSense RGB-D observations. Refined prompted masks, back-projected garment pixels into 3D, and applied voxel downsampling and statistical outlier removal to prepare point clouds for grasp-point matching and policy inference.

## Dexterous Manipulation Demo

<video controls playsinline preload="none" poster="/images/projects/Stellar-Robot/demo-poster.jpg" style="width:100%;height:auto;" aria-label="Four dexterous manipulation demonstrations in a two-by-two grid">
  <source src="/files/Stellar-Robot/dexterous-grid.mp4" type="video/mp4">
  <a href="/files/Stellar-Robot/dexterous-grid.mp4">Watch the dexterous manipulation demonstrations</a>.
</video>

*Four dexterous manipulation demonstrations at their original playback speeds.*

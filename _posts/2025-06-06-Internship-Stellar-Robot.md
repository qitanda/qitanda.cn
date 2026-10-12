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

During my three-month internship at **Stellar-Robot**, I worked on adapting dexterous manipulation algorithms to **GaiaHand, PantheonHand, and Realman-75f** hardware. My work covered human-hand retargeting, arm kinematics, camera-to-robot calibration, garment perception, demonstration collection, and imitation-learning experiments.

## Overview

![Dexterous robot platform](/images/projects/Stellar-Robot/product.png)

The work connected five complementary components: **extrinsic calibration → arm kinematics → hand retargeting → garment learning → real-robot perception and deployment interfaces**. Building on GeoRT, DexGarmentLab, and SAM2, I focused on robot-specific adaptation and the interfaces needed to carry observations and actions between simulation, learning, and hardware.

## GeoRT-Based Hand Retargeting

Adapted **GeoRT** within UniRT to transfer human-hand motions to **GaiaHand and PantheonHand**, accounting for differences in hand geometry and joint structure.

- **Robot-specific keypoints and joint mappings.** Configured fingertip links, joint groups, and robot assets so that captured human keypoints correspond to the appropriate fingers and actuated joints.
- **Fingertip offset and scale calibration.** Computed fingertip offsets in each robot link's local coordinate frame and checked their alignment through forward kinematics. Hand-size and finger-specific scaling compensate for differences between human and robot proportions before retargeting.
- **Training, inference, and replay.** Integrated GeoRT's learned finger kinematics with motion-capture inputs and SAPIEN replay tools, allowing retargeted motions and keypoint alignment to be inspected across hand models.

<video controls playsinline preload="none" poster="/images/projects/Stellar-Robot/retargeting-poster.jpg" style="width:100%;height:auto;" aria-label="GeoRT-based dexterous hand retargeting demonstration">
  <source src="/files/Stellar-Robot/retargeting-demo.mp4" type="video/mp4">
  <a href="/files/Stellar-Robot/retargeting-demo.mp4">Watch the hand retargeting demonstration</a>.
</video>

*Human-to-robot hand motion retargeting based on GeoRT.*

## Mechanical-Arm Kinematics and Control Interfaces

Built a **ROS 2 / MoveIt 2 interface for the seven-joint Realman-75f**, with robot descriptions and configurations for the arm and GaiaHand assembly.

- **Forward and inverse kinematics.** Used the robot model to compute end-effector poses and configured interchangeable **KDL numerical** and **IKFast analytical** solvers for pose-to-joint conversion.
- **State-aware IK.** Maintained separate left- and right-arm states and initialized IK from measured joint positions. This gives the solver the current configuration as a starting point when converting successive Cartesian targets into joint commands.
- **Modular motion interfaces.** Separated target poses, joint feedback, and IK outputs through ROS 2 messages. Hardware adapters connect manipulation routines to the Realman SDK, while solver timing and failure reporting support integration and debugging.

## Extrinsic Calibration and Shared Coordinates

Integrated camera-to-robot calibration into a reusable **ROS 2 TF** package. Calibration rotation matrices and translations are converted into static transforms linking the camera and both arm bases.

This allows a garment point detected in camera coordinates to be transformed into the appropriate arm's base frame before motion generation. Keeping the camera extrinsics and inter-arm transform in a shared TF tree makes perception and manipulation use a consistent geometric reference.

## Garment Manipulation through Imitation Learning

Reproduced and adapted the **DexGarmentLab** workflow in Isaac Sim, including robot control, demonstration collection, policy training, and simulation evaluation, and developed the corresponding Realman-and-GaiaHand interfaces for garment-grasping experiments.

- **GAM-based grasp-point transfer.** Applied learned per-point garment descriptors to match selected points on a reference garment to a new observation. Cosine similarity identifies corresponding manipulation points and produces spatial affordance features for the policy.
- **Structure-aware diffusion policy.** Integrated garment geometry and affordance features with environment/object point clouds and robot state. Separate point-cloud encoders preserve these complementary inputs before a conditional diffusion model predicts a sequence of actions.
- **Demonstration-to-training pipeline.** Recorded garment observations and robot states, organized trajectories into training datasets, and used the existing Zarr conversion and sequence-sampling workflow. The training setup includes observation history, DDIM sampling, and exponential-moving-average model weights.
- **Hardware adaptation.** Connected camera-frame grasp targets, calibrated arm coordinates, arm motion commands, and dexterous-hand control for data collection. Prepared policy-inference interfaces for real-robot deployment experiments, alongside the simulation workflow.

## SAM2 Perception for Real-Robot Garment Grasping

Integrated **SAM2** with RealSense RGB-D streams to turn garment masks into the 3D observations needed by grasp-point matching and policy inference.

- **Synchronized RGB-D observations.** Approximately synchronized color, aligned depth, and camera intrinsics through ROS 2 before reconstructing the garment geometry.
- **Prompted segmentation and refinement.** Used a foreground point prompt to obtain candidate masks, selected the highest-scoring result, and refined it using its predicted mask logits.
- **Clean garment point clouds.** Back-projected masked depth into 3D, removed invalid depth, and applied voxel downsampling and statistical outlier filtering. Sampling controls point-cloud size for downstream learning modules.
- **Deployment diagnostics.** Published garment and environment point clouds separately and provided mask overlays, depth views, and point-cloud exports to inspect perception quality before connecting observations to robot actions.

## Dexterous Manipulation Demo

<video controls playsinline preload="none" poster="/images/projects/Stellar-Robot/demo-poster.jpg" style="width:100%;height:auto;" aria-label="Four dexterous manipulation demonstrations in a two-by-two grid">
  <source src="/files/Stellar-Robot/dexterous-grid.mp4" type="video/mp4">
  <a href="/files/Stellar-Robot/dexterous-grid.mp4">Watch the dexterous manipulation demonstrations</a>.
</video>

*Four dexterous manipulation demonstrations shown together at their original playback speeds.*

## Engineering Focus

The main contribution was adapting existing methods into a shared manipulation workflow: aligning coordinate frames, matching robot joint and keypoint conventions, preparing learning observations, and connecting perception to hardware interfaces. Simulation reproduction, calibration, data collection, and policy training formed the core of the work; real-robot policy deployment was an ongoing integration and validation effort.

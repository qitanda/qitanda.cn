---
title: 'Quest 3 VR Teleoperation and Data Collection System'
date: 2026-10-08
permalink: /projects/quest3-teleoperation/
excerpt: "A Quest 3 and ROS 2 system for dual-arm teleoperation and demonstration collection, with calibrated relative-pose mapping, Pinocchio servo integration, and controller-based gripper and dexterous-hand control."
tags:
  - VR Teleoperation
  - Robot Learning
  - Data Collection
author_profile: false
read_time: false
share: false
comments: false
related: false
project_order: 3
header:
  teaser: projects/quest3-teleoperation/demo-cropped-poster.jpg
---

Built a **Quest 3 VR teleoperation and data collection system** for robot-learning demonstrations. The headset and its paired controllers provide the operator interface, while a **ROS 2** pipeline maps controller poses and button inputs to dual-arm motion and end-effector commands.

## Demo Video

<video controls playsinline preload="none" poster="/images/projects/quest3-teleoperation/demo-cropped-poster.jpg" style="width:100%;height:auto;max-height:720px;background:#111;" aria-label="Quest 3 VR robot teleoperation and data collection demonstration">
  <source src="/files/quest3-teleoperation/demo-cropped.mp4" type="video/mp4">
  <a href="/files/quest3-teleoperation/demo-cropped.mp4">Watch the teleoperation demonstration</a>.
</video>

## Control Pipeline

The XR interface publishes left and right controller poses and button states. Each arm has its own mapping node, which converts controller motion into a robot-frame end-effector pose target. The servo backend consumes these targets and connects to the corresponding arm controller. Trigger and squeeze inputs independently control the end effectors.

## Calibrated Relative-Pose Mapping

Controller translation and rotation are mapped **relative to an anchor pose**, rather than directly copying the controller's absolute position. On activation, the system records both the controller pose and the robot end-effector pose from TF, then applies calibrated coordinate transforms to subsequent motion. The calibration utility estimates the device-to-robot rotation from guided controller movements.

Each arm can be paused or resumed independently. The mapping node detects stale tracking data and abrupt pose changes, pauses target output, and re-establishes the anchor after stable tracking returns. This supports repositioning the operator's hands and recovering from tracking interruptions without directly applying a discontinuous target.

## Pinocchio Servo Integration

The workspace launches separate **Pinocchio servo backends for the left and right arms**, passing each arm's end-effector frame, pose-target topic, joint-limit configuration, and controller configuration. The default configured algorithm is **`mpc_pose_follower`**. A force-input admittance variant is also exposed as an optional configuration.

Pinocchio is used in the included integration tests to load the robot URDF, compute forward kinematics and end-effector transforms, and evaluate pose errors in SE(3). This connects the robot model to Cartesian pose tracking and verification.

## Gripper and Dexterous-Hand Control

The controller's trigger and squeeze axes are mapped to end-effector joint commands through **bilinear interpolation**. Configurable input dead zones account for released and fully pressed controller positions. The provided mappings support an **LMG-90 gripper** and a **six-joint Inspire dexterous hand**.

## Demonstration Collection

The documented collection workflow runs the XR interface, robot servo, multi-camera capture, teleoperation mapping, and ROS 2 data recorder together. The camera launch includes head and wrist RGB-D views. Timing-analysis utilities inspect camera timestamps, receive-time differences, and recorded session consistency to help diagnose data quality before downstream robot learning.

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

## ROS 2 and MoveIt 2 Framework

Built an integrated **ROS 2** framework connecting the dual-arm robot, end effectors, cameras, and VR interface. Robot descriptions and TF establish consistent coordinate frames, while **ros2_control** connects the hardware drivers to arm trajectory controllers, gripper and hand controllers, and state feedback. A shared launch setup supports both real hardware and simulated hardware interfaces for integration testing.

Integrated **MoveIt 2** for motion planning, planning-scene monitoring, trajectory execution, and RViz visualization. The control framework supports both MoveIt Servo and a **Pinocchio-based servo backend** for following Cartesian targets from the VR controllers.

## VR Teleoperation

Calibrated controller-to-robot coordinates and mapped relative hand motion to the two robot arms. Independent pause/resume controls, tracking-loss detection, and automatic re-anchoring help maintain continuity during operation. Trigger and grip inputs control the gripper and dexterous hand.

## Data Collection

Integrated head and wrist RGB-D cameras with robot control and a ROS 2 recording workflow to collect manipulation demonstrations. Camera timestamp and receive-time checks help identify timing inconsistencies before using the recordings for robot learning.

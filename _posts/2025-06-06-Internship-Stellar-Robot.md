---
title: 'Dexterous Algorithm Intern in Stellar-Robot'
date: 2025-08-23
permalink: /projects/Stellar-Robot/
excerpt: "I joined Stellar-Robot, a company specializing in dexterous hand manufacturing, as a three-month intern specializing in dexterous hand algorithms. My main task was to reproduce advanced dexterous hand manipulation algorithms, focusing on imitation learning and reinforcement learning, and to attempt to reproduce them using a physical platform."
tags:
  - Dexterous Hand
  - Imitation Learning
  - Reinforcement Learning
author_profile: false
header:
  teaser: projects/Stellar-Robot/product.png
share: false
project_order: 5
---

I joined Stellar-Robot, a company specializing in dexterous hand manufacturing, as a three-month intern specializing in dexterous hand algorithms. My main task was to reproduce advanced dexterous hand manipulation algorithms, focusing on imitation learning and reinforcement learning, and to attempt to reproduce them using a physical platform.

## Overview
![Project](/images/projects/Stellar-Robot/product.png)

## GeoRT-Based Hand Retargeting

Building on **GeoRT**, my work focused on adapting human-hand motion retargeting to **GaiaHand and PantheonHand**. This involved configuring robot keypoints and joint mappings, calibrating fingertip offsets and hand-size scaling, and integrating training, inference, and replay visualization to check how human motions transfer to different robot hand structures.

<video controls playsinline preload="none" poster="/images/projects/Stellar-Robot/retargeting-poster.jpg" style="width:100%;height:auto;" aria-label="GeoRT-based dexterous hand retargeting demonstration">
  <source src="/files/Stellar-Robot/retargeting-demo.mp4" type="video/mp4">
  <a href="/files/Stellar-Robot/retargeting-demo.mp4">Watch the hand retargeting demonstration</a>.
</video>

*Human-to-robot hand motion retargeting based on GeoRT.*

## Dexterous Manipulation Demo

<video controls playsinline preload="none" poster="/images/projects/Stellar-Robot/demo-poster.jpg" style="width:100%;height:auto;" aria-label="Four dexterous manipulation demonstrations in a two-by-two grid">
  <source src="/files/Stellar-Robot/dexterous-grid.mp4" type="video/mp4">
  <a href="/files/Stellar-Robot/dexterous-grid.mp4">Watch the dexterous manipulation demonstrations</a>.
</video>

*Four dexterous manipulation demonstrations. Each clip retains its original playback speed; shorter clips hold their final frame until the longest clip finishes.*

## Simulation and Real-Robot Integration

Combined **DexGarmentLab** and **PyTorch kinematics** to connect GaiaHand and PantheonHand simulation control, data collection, and policy training and evaluation in Isaac Sim. Built a physical platform with **Realman-75f and GaiaHand** for real-world imitation-learning experiments on garment grasping.

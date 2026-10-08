---
title: 'Dexterous Algorithm Intern in Stellar-Robot'
date: 2025-06-06
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

## Demo Video

<video controls playsinline preload="none" poster="/images/projects/Stellar-Robot/demo-poster.jpg" style="width:100%;height:auto;" aria-label="Four dexterous manipulation demonstrations in a two-by-two grid">
  <source src="/files/Stellar-Robot/dexterous-grid.mp4" type="video/mp4">
  <a href="/files/Stellar-Robot/dexterous-grid.mp4">Watch the dexterous manipulation demonstrations</a>.
</video>

*Four dexterous manipulation demonstrations. Each clip retains its original playback speed; shorter clips hold their final frame until the longest clip finishes.*

## Details
Specifically, my work first involved adapting and optimizing the redirection of data gloves to dexterous hands based on GeoRT. Secondly, I combined DexGarmentLab and PyTorch kinematics to build a fully connected imitation learning process for GaiaHand and PantheonHand simulation control, data acquisition, and policy training verification in Isaac Sim. Finally, I built a physical platform based on Realman-75f and GaiaHand and conducted real-world verification of imitation learning for grasping clothing.
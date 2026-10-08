---
title: 'Dual-Arm Robotic Sorting of Mechanical Parts'
date: 2026-10-08
permalink: /projects/dual-arm-sorting/
excerpt: "Trained a π₀.₅ policy on hundreds of teleoperated demonstrations, including successful sorting and recovery from failures. Used workspace cropping to reduce background distractions and Real-Time Chunking (RTC) for continuous policy execution."
tags:
  - Dual-Arm Manipulation
  - Vision-Language-Action Models
  - Imitation Learning
author_profile: false
read_time: false
comments: false
share: false
related: false
header:
  teaser: projects/dual-arm-sorting/policy-deployment.jpg
project_order: 2
---

Developed an automatic mechanical-part sorting system for a **dual-arm robot**, covering teleoperated data collection, **π₀.₅ policy training**, and real-robot deployment with **Real-Time Chunking (RTC)**.

## Overview

![Dual-arm robot sorting mechanical parts on a tabletop]({{ '/images/projects/dual-arm-sorting/policy-deployment.jpg' | relative_url }})

- **Demonstration collection.** Recorded hundreds of teleoperated demonstrations, including routine successful sorting trajectories and corrective actions after failures, to provide examples of both task completion and recovery.
- **Workspace-focused training.** Cropped visual observations to the tabletop workspace during training to reduce distractions from the surrounding environment.
- **Policy training and deployment.** Trained π₀.₅ on the collected demonstrations and deployed the policy on the dual-arm robot with RTC.

## Policy Deployment

<video controls playsinline preload="none" poster="{{ '/images/projects/dual-arm-sorting/policy-deployment.jpg' | relative_url }}" style="width:100%;height:auto;" aria-label="Dual-arm robotic sorting policy deployment, sped-up footage">
  <source src="{{ '/files/dual-arm-sorting/policy-deployment.mp4' | relative_url }}" type="video/mp4">
  <a href="{{ '/files/dual-arm-sorting/policy-deployment.mp4' | relative_url }}">Watch the policy deployment video</a>.
</video>

*Automatic mechanical-part sorting with the trained policy. This video is sped up and does not represent real-time execution speed.*

## Teleoperation and Data Collection

<video controls playsinline preload="none" poster="{{ '/images/projects/dual-arm-sorting/teleoperation.jpg' | relative_url }}" style="width:100%;height:auto;max-height:680px;background:#111;" aria-label="Teleoperated demonstration collection for dual-arm robotic sorting">
  <source src="{{ '/files/dual-arm-sorting/teleoperation.mp4' | relative_url }}" type="video/mp4">
  <a href="{{ '/files/dual-arm-sorting/teleoperation.mp4' | relative_url }}">Watch the teleoperation video</a>.
</video>

*Teleoperation setup used to collect training demonstrations, including successful task executions and recovery trajectories after failures.*

## Real-Time Chunking

RTC addresses the delay between predicting an action sequence and executing it. It generates the next action chunk asynchronously while the robot continues executing the current one, conditioning the new prediction on committed actions to maintain continuity across chunk boundaries. This is intended to reduce inference-related pauses and abrupt transitions during deployment.

See Physical Intelligence's [Real-Time Action Chunking](https://www.pi.website/research/real_time_chunking) for the method and its underlying mechanism.

---
title: 'Champion of CMU Vision-Language-Autonomy Challenge'
date: 2025-09-10
permalink: /projects/CMU-VLA-CHALLENGE/
excerpt: "Independently developed a VLA framework for semantic navigation in unknown environments, overcoming generalization bottlenecks. Validated via Sim-to-Real, the system won dual championships in both simulation and physical robot tracks."
tags:
  - Vision Language Navigation
  - Path Planning
  - Semantic Perception
author_profile: false
header:
  teaser: projects/CMU-VLA-CHALLENGE/result.png
---

We independently designed a large-scale visual language action model algorithm framework, overcoming several key technologies such as scene understanding based on natural language commands, object spatial semantic recognition, and autonomous motion trajectory planning for robots. This enabled autonomous generation and task execution of navigation actions based on semantic and spatial relationships in unknown environments. The algorithm was comprehensively evaluated and validated in both the Unity simulation environment system and a real robot platform, breaking through the bottlenecks of generalization and autonomy in real-world scenarios. Its outstanding performance earned it dual championships in both the simulation environment and physical platform competitions.

## Overview
![Pipeline](/images/projects/CMU-VLA-CHALLENGE/result.png)

## Demo Video
<!-- <iframe width="100%" height="100%" src="https://www.youtube.com/watch?v=mqkMAY0yAAk" frameborder="0" allowfullscreen></iframe> -->
<iframe width="100%" height="320"
  src="https://youtu.be/DmPtxXcwUDU"
  frameborder="0"
  allowfullscreen>
</iframe>

## Details
The CMU Vision-Language-Autonomy Challenge leverages computer vision and natural language understanding in navigation autonomy. The challenge aims at pushing the limit of embodied AI in real environments and on real robots - providing a robot platform and a working autonomy system to bring higher-level reasoning and learning models a step closer to real-world deployment. 
The characteristic of the challenge is to develop a model that takes in natural language queries or commands about a scene and generate the appropriate navigation-based response through reasoning about semantic and spatial relationships. The environment is initially unknown and the system will have to navigate to appropriate viewpoints to discover and validate the spatial relations and attributes. A real-robot system equipped with a 3D LiDAR and a 360 camera is provided, which has base autonomy onboard that can estimate the sensor pose, analyze the terrain, avoid collisions, and navigate to waypoints. Teams will develop a reasoning module for the robot's onboard computer to interface with the system and navigate the robot. 
---
title: 'CMU Vision-Language-Navigation Challenge'
date: 2025-09-10
permalink: /projects/CMU-VLA-CHALLENGE/
excerpt: "Champion in both simulation and real-robot tracks. A vision-language navigation system combining multimodal frontier exploration, scene-graph reasoning, and instruction-guided navigation."
tags:
  - Vision Language Navigation
  - Path Planning
  - Semantic Perception
author_profile: false
read_time: false
share: false
header:
  teaser: projects/CMU-VLA-CHALLENGE/reasoning.png
project_order: 4
---

## Problem and Tasks

The challenge requires a robot to interpret natural-language requests, explore an initially unknown environment, and reason about objects and their spatial relationships. Inputs include **instructions, RGB observations, LiDAR, odometry, and object information**.

![Problem definition and examples of numerical, object-reference, and instruction-following tasks](/images/projects/CMU-VLA-CHALLENGE/problem.png)

The system addresses three task types:

- **Numerical reasoning:** count objects satisfying spatial constraints, such as blue chairs between a table and a wall.
- **Object reference:** identify an object through multiple relations, such as the orange chair between a table and a sink that is closest to a window.
- **Instruction following:** complete an ordered sequence of navigation goals using object and spatial descriptions.

## Overall Pipeline

![Overall reasoning and navigation pipelines](/images/projects/CMU-VLA-CHALLENGE/overview.png)

Reasoning tasks proceed through problem identification and goal-graph construction, exploration, scene-graph matching and object grounding, then answer generation. Navigation tasks additionally decompose the instruction into subtasks and repeatedly identify and navigate to the next target.

## Multimodal Exploration

![BLIP-based view-language similarity and frontier scoring pipeline](/images/projects/CMU-VLA-CHALLENGE/exploration.png)

The panoramic image is projected into **12 viewpoints**. BLIP estimates view-language similarity to the instruction, while LiDAR and odometry support frontier mapping. The resulting scores guide the planning and control module toward regions relevant to the target.

## Spatial Reasoning and Object Grounding

![Qwen3, scene-graph memory, perception, and planning architecture](/images/projects/CMU-VLA-CHALLENGE/reasoning.png)

**Qwen3** identifies the problem, builds the goal graph, and produces the answer. Perception maintains an instance map and constructs a scene graph from RGB, LiDAR, odometry, and object information. Graph matching connects the requested relations, such as **on** and **near**, to observed objects. Multimodal frontier scoring guides further exploration when additional evidence is needed.

## Instruction-Guided Navigation

![Three navigation strategies using Grounded SAM, visual waypoint selection, and frontier scoring](/images/projects/CMU-VLA-CHALLENGE/navigation.png)

![Instruction-guided navigation pipeline](/images/projects/CMU-VLA-CHALLENGE/result.png)

The navigation module combines three strategies: **Grounded SAM** builds scene-graph information about distant objects; numbered waypoints projected onto images let the VLM select a navigation target; view-language similarity updates frontier priorities during exploration.

## Demo Videos

### Spatial Reasoning

<video controls playsinline preload="none" poster="/images/projects/CMU-VLA-CHALLENGE/reasoning-poster.jpg" style="width:100%;height:auto;" aria-label="Spatial reasoning demonstration">
  <source src="/files/CMU-VLN-CHALLENGE/reasoning.mp4" type="video/mp4">
  <a href="/files/CMU-VLN-CHALLENGE/reasoning.mp4">Watch the spatial reasoning demonstration</a>.
</video>

*Spatial reasoning demonstration from slide 9.*

### Instruction-Guided Navigation

<video controls playsinline preload="none" poster="/images/projects/CMU-VLA-CHALLENGE/navigation-poster.jpg" style="width:100%;height:auto;" aria-label="Instruction-guided navigation with instruction and task breakdown">
  <source src="/files/CMU-VLN-CHALLENGE/navigation.mp4" type="video/mp4">
  <a href="/files/CMU-VLN-CHALLENGE/navigation.mp4">Watch the navigation demonstration</a>.
</video>

*Navigation demonstration from slide 12, with the instruction and task breakdown preserved alongside the robot view: approach the fireplace, go to the window closest to the bookcase, and stop at the chair farthest from the mirror.*

Both source clips are marked **2× speed**; no additional speed-up is applied.

## Competition Result

**NROS Team** ranked first in the preliminary simulation evaluation (**36.03**) and achieved the highest final score (**44.26**). [Challenge website](https://www.ai-meets-autonomy.com/cmu-vln-challenge).

![2025 challenge leaderboard showing NROS Team in first place](/images/projects/CMU-VLA-CHALLENGE/leaderboard.png)

[![NROS Team challenge certificate](/images/projects/CMU-VLA-CHALLENGE/certificate.png)](/files/CMU-VLN-CHALLENGE/certificate.pdf)

[View the certificate PDF](/files/CMU-VLN-CHALLENGE/certificate.pdf)

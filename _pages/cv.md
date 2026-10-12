---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

[Download Chinese CV · 中文简历（PDF）]({{ '/files/简历-朱骥.pdf' | relative_url }})

## Ji Zhu

**Embodied AI Research Intern**  
Research interests: Robotic Manipulation · Vision-Language-Action Models · World Models and World Action Models · Vision-Language Navigation

[Email](mailto:1602771147@qq.com) · [GitHub](https://github.com/qitanda) · Phone: +86 157 1849 9428

## Education

**Harbin Institute of Technology, Shenzhen** — M.S. in Control Science and Engineering  
September 2025 – March 2028 (expected)

- Admitted through the recommendation-based admission program.
- GPA: **3.931 / 4.0**; class rank: **6 / 86**.

**Harbin Institute of Technology, Shenzhen** — B.Eng. in Automation  
September 2021 – June 2025

- GPA: **3.764 / 4.0**; class rank: **12 / 255**.
- Honors: National Scholarship, Academic Scholarship, Outstanding Graduate, Outstanding Student, and Outstanding Youth League Member.
- English: CET-6, **538**.

## Publications and Research

### CA-WAM: Learning Contact-Aware World Action Models via Force Prediction for Robot Manipulation

**First author · Under review, submitted to ICRA 2027**  
March 2026 – September 2026 · [Project](/projects/CA-WAM/)

- Learned contact-aware representations through future 3D end-effector force supervision, jointly modeling video, force, and actions with conditional flow matching. Combined asymmetric attention masks with training-time VGGT geometric alignment.
- Inference uses current observations without measured force or future-video generation; predicted force changes guide the action execution horizon.
- Achieved **98.5%** success on LIBERO, **94.9%** on Meta-World, and **71.0%** on real-robot tasks; a **19% improvement over Fast-WAM** was reported across standard and contact-intensive real-world tasks.

### GSON: A Group-based Social Navigation Framework with Large Multimodal Model

**Co-first author · IEEE Robotics and Automation Letters (RA-L), 2025**  
September 2024 – July 2025 · [Project](/projects/GSON/)

- Used visual prompting with a large multimodal model to infer pedestrian social relationships without task-specific training.
- Introduced an intermediate planner between global and local planning to preserve social context while responding to obstacles. Evaluated in real-world queues, conversations, and group-photo scenarios, reducing disruption to groups while maintaining navigation performance.

## Internship Experience

**Dexterous Manipulation Algorithm Intern — Stella Robot, Shenzhen**  
June 2025 – September 2025 · [Project](/projects/Stellar-Robot/)

- Adapted GeoRT to **GaiaHand and PantheonHand** through keypoint/joint mappings, fingertip offsets, and hand-scale calibration.
- Integrated DexGarmentLab, PyTorch Kinematics, MoveIt, and Isaac Sim for simulation control, demonstration collection, and DP3 imitation-learning training and evaluation for garment grasping.
- Built a **Realman-75f + GaiaHand** platform, completed hand–eye calibration, and integrated SAM2 and FoundationPose for real-robot imitation-learning deployment experiments and garment-grasping validation.

## Selected Projects

### Dual-Arm Robotic Sorting of Mechanical Parts

March 2026 – May 2026 · [Project](/projects/dual-arm-sorting/)

- Trained **π₀.₅** on hundreds of teleoperated demonstrations, including successful executions and failure recovery. Cropped observations to the tabletop workspace to reduce background distractions.
- Deployed the policy with **Real-Time Chunking (RTC)**: asynchronously predicted upcoming actions while executing the current chunk, conditioning predictions on committed actions to maintain continuity.

### Dual-Arm Teleoperation and Data Collection System

November 2025 – January 2026 · [Project](/projects/quest3-teleoperation/)

- Integrated dual arms, end effectors, and cameras with **ROS 2, MoveIt 2, MoveIt Servo, and Pinocchio**, using Quest 3 controllers for relative-pose teleoperation.
- Implemented controller calibration, pose-jump detection, and re-anchoring; integrated head/wrist RGB-D recording and timestamp checks, with gripper and dexterous-hand control and interfaces for simulation and hardware testing.

### CMU Vision-Language-Navigation Challenge

July 2025 – September 2025 · [Project](/projects/CMU-VLA-CHALLENGE/)

- Built a system combining multimodal exploration, scene-graph reasoning, and instruction-guided navigation. BLIP image–text similarity guided frontier exploration; Qwen3 goal graphs were matched against scene graphs for object localization and spatial reasoning.
- Combined Grounded SAM with visual waypoint selection for semantic navigation. **Won both the simulation and real-world tracks** of the IROS 2025 CMU VLN Challenge.

## Technical Skills

- **Programming and development:** Python, C/C++, PyTorch, Linux, Git, Docker, CMake, ROS 1/2, OpenCV, and PCL.
- **Robot learning:** Deep learning, reinforcement learning, and imitation learning; ACT and Diffusion Policy; OpenVLA and π₀; Cosmos Policy and Fast-WAM; flow matching, mixture of experts, and mixture of transformers. Experience with LIBERO, Meta-World, and RoboTwin.
- **Robotics systems:** Isaac Sim, Gazebo, MuJoCo, MoveIt 2, and Pinocchio; teleoperation and data collection; perception, pose estimation, planning, control, decision making, and sim-to-real integration. Hands-on experience with mobile robots, dual-arm platforms, and UAVs.

## Selected Competitions

- **2025:** International Champion, IROS CMU VLN Challenge — simulation and real-world tracks.
- **2024:** National First Prize, National University Student Intelligent Car Competition.
- **2024:** International Second Prize, ICRA RoboMaster University Sim2Real Challenge.
- **2023:** National Second Prize, RoboMaster RMUA Unmanned Aerial Vehicle Intelligent Sensing Technology Competition.

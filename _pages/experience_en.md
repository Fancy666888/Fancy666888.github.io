---
layout: page
title: Experience
permalink: /en/experience/
description: Education, technical interests, project experience, skills, and honors.
lang: en
nav: false
zh_url: /cv/
---

## Education

**Beijing Forestry University, School of Engineering** — B.Eng. candidate in Automation, September 2024–June 2028 (expected)

- Weighted average: **91.69/100**, ranked **8/84** in the major
- CET-6: **622**

## Technical Interests

- Robotics and embodied intelligence
- Robotic-arm control and state-machine design
- Computer vision and RGB-D perception
- Bayesian inference, MCMC, and data-driven decision-making

Available for an on-site internship **3–4 days per week**.

## Research and Project Experience

### Embodied Robotic Collaboration for Precision Assembly — 2026

- Used a multimodal model to parse task cards into structured assembly steps, followed by deterministic whitelist, sequence, and range validation before execution.
- Triggered VisionMaster processes over TCP and waited for measured coordinate messages before entering the motion stage, preserving vision–motion sequencing.
- Mapped visual coordinates to robot coordinates and executed MoveJ/MoveL commands through the AUBO ARCS SDK/RPC interface.
- Organized grasping, placement, reset, and exception handling with a state machine while retaining state, timestamp, and execution logs.

### Blueberry Maturity Detection and RGB-D Data Management — 2026

- Trained a YOLO model to identify unripe, semi-ripe, and ripe blueberries and built an application with confidence adjustment, dashboards, and CSV export.
- Integrated Intel RealSense D435i/D405 cameras for single-frame and continuous acquisition, session metadata, dataset indexing, and integrity auditing.
- Computed valid-depth ratio, center depth, median depth, and related quality metrics to generate standardized acquisition reports for 3D localization and model training.

### OpenMV and STM32F407 Intelligent Rescue Vehicle — April 2026

- Used an OpenMV4 H7 Plus for color thresholding, blob filtering, and target localization, including horizontal-offset estimation for multiple target categories.
- Implemented mecanum-wheel inverse kinematics on the STM32F407 and drove four motors through TB6612 PWM outputs, using encoder feedback and PID at an approximately 10 ms update period.
- Organized search, tracking, approach, grasp/transport, and return behaviors with a task state machine.

### Bayesian Inference and Dynamic Scoring in Voting Systems — 2026

- Received **Finalist (F Award)** in the 2026 MCM/ICM; the related paper was accepted by **Axioms**, with me as the third author.
- Built a Bayesian model under hierarchical constraints, using a Dirichlet prior and Metropolis–Hastings MCMC to infer latent audience votes.
- Compared ranking, percentage, and judges' intervention mechanisms and used Lasso to analyze influential factors.
- Proposed an uncertainty-aware Expert–Public Fusion framework and evaluated it on 34 seasons and 2,777 observations, achieving **0.9655** reconstruction accuracy.

## Publication

_Constrained Bayesian Reconstruction of Latent Public Preferences under Dynamic Elimination Rules: An Uncertainty-Aware Expert–Public Fusion Framework_ — **Axioms**, accepted, 2026; third author. Volume, issue, pages, and DOI will be added after online publication.

## Skills

- **Programming:** Python, C, Git, LaTeX
- **Robotics and control:** AUBO ARCS, STM32 HAL, PID motion control
- **Vision and perception:** YOLO model training, VisionMaster, Intel RealSense D435i/D405, OpenMV4 H7 Plus

## Honors

- **National Scholarship**, 2024–2025 academic year
- **Finalist (F Award)**, Mathematical Contest in Modeling / Interdisciplinary Contest in Modeling, 2026
- **First Prize and Advancement**, Beijing–Tianjin–Hebei Regional Embodied Intelligence Precision Assembly Competition, 2026
- **Second Prize, Beijing**, China Undergraduate Mathematical Contest in Modeling, September 2025
- **Third Prize, Beijing**, National Undergraduate Electronics Design Contest, August 2026
- **Second Prize, University Level**, Intelligent Rescue Track, Engineering Practice and Innovation Competition, April 2026

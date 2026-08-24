---
layout: page
title: Projects
permalink: /en/projects/
description: Research exploration, engineering competitions, and technical projects.
lang: en
nav: false
zh_url: /projects/
---

## Blueberry Maturity Detection and RGB-D Data Management

This project develops visual perception and data infrastructure for a blueberry harvesting robot. It combines a YOLOv8-based maturity detector with an RGB-D acquisition and dataset-management system.

{% include figure.liquid loading="eager" path="assets/img/projects/blueberry-rgbd-system.png" title="Blueberry RGB-D data management system" class="img-fluid rounded z-depth-1" %}

- Detects unripe, semi-ripe, and ripe blueberries with YOLOv8
- Provides image inference, confidence adjustment, history, dashboards, and CSV export
- Supports Intel RealSense D435i/D405 cameras, continuous capture, depth-quality metrics, session reports, and data-integrity audits
- Uses Python, FastAPI, SQLAlchemy, SQLite, OpenCV, Intel RealSense, and ECharts

## Embodied Robotic Collaboration for Precision Assembly

Developed for the 2026 China College Students Mechanical Engineering Innovation and Creativity Competition, this system connects multimodal task understanding, VisionMaster visual communication, and an AUBO robotic-arm environment through a Python GUI console.

{% include figure.liquid loading="eager" path="assets/img/projects/precision-assembly-architecture.png" title="Precision assembly system architecture" class="img-fluid rounded z-depth-1" %}

- Uses a multimodal model to parse task cards into structured assembly steps
- Applies deterministic validation rules before any robotic action is executed
- Connects VisionMaster through TCP and AUBO ARCS through its SDK/RPC interface
- Organizes coordinate conversion, motion control, recovery, and logging with a state machine

Our team, “具身不由己,” won **First Prize in the Beijing–Tianjin–Hebei regional competition and advanced to the next stage**.

## Bayesian Inference and Dynamic Scoring in Voting Systems

This modeling project originated from the 2026 MCM/ICM Problem C competition paper, _Who Really Keeps Dancing? A Bayesian MCMC Inference and Logistic Dynamic Scoring Framework in Voting Systems_. It estimates hidden audience votes and compares alternative judging and elimination mechanisms.

- Uses Bayesian MCMC under hierarchical constraints to infer latent vote shares
- Compares ranking, percentage, and judges' intervention mechanisms
- Proposes a Logistic Dynamic Weighted System whose audience and judges' weights evolve during a season
- Archives the competition paper and ongoing reproducibility experiments

[Read the competition paper (PDF)]({{ '/assets/pdf/2026-mcm-problem-c.pdf' | relative_url }})

## Additional Engineering Projects

### Three-Axis Gantry Puzzle Device

An electronic-design competition project. Details about its mechanical structure, control strategy, and demonstration results will be added later.

### Intelligent Rescue Vehicle

An autonomous rescue robot integrating OpenCV-based color vision with an STM32F407-controlled mecanum-wheel chassis. The system identifies colored rescue targets, estimates their horizontal offsets, and coordinates search, tracking, grasping, and transportation through encoder-based PID motion control.

The project received **Second Prize in the university-level competition in April 2026**.

[Read the project details]({{ '/en/projects/intelligent-rescue-car/' | relative_url }})

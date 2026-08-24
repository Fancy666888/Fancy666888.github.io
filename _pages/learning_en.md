---
layout: page
title: Learning
permalink: /en/learning/
description: Notes on automation, robotics, papers, experiments, and engineering tools.
lang: en
nav: false
zh_url: /blog/
---

This timeline records when the learning or project work actually took place, rather than when the website entry was written. Full technical notes are maintained in Chinese; the English summaries below provide the same chronological overview.

## Learning Timeline

### July 2025 — STM32 peripherals and communication {#stm32-peripherals-and-communication}

I connected the basic roles of GPIO, external interrupts, UART, and I²C into a single microcontroller learning path. The main lesson was to relate every software configuration to its electrical behavior and to select polling, interrupts, or communication peripherals according to the system requirement.

[Read the full Chinese note]({{ '/blog/2025/stm32-peripherals-and-communication/' | relative_url }})

### September 2025 — Modern optimization algorithms {#modern-optimization-algorithms}

I compared simulated annealing, genetic algorithms, and ant colony optimization through their search mechanisms, parameters, strengths, and failure modes. This study shifted my attention from simply choosing an algorithm name to defining the representation, objective function, constraints, and repeatable evaluation protocol.

[Read the full Chinese note]({{ '/blog/2025/modern-optimization-algorithms/' | relative_url }})

### April 2026 — Intelligent rescue vehicle {#intelligent-rescue-car-retrospective}

For a university engineering competition, our team developed an autonomous rescue vehicle and received Second Prize. The system evolved from a K210-based vision prototype to a final OpenCV and STM32F407 architecture, integrating color perception, a task state machine, mecanum-wheel motion, encoder feedback, and PID control.

[Read the full Chinese note]({{ '/blog/2026/intelligent-rescue-car-retrospective/' | relative_url }})

### April–July 2026 — Reproducible engineering toolchain {#reproducible-engineering-toolchain}

I organized a workflow covering isolated AnyLabeling environments, human verification of automatic annotations, scoped AI-assisted coding, and a local RGB-D dataset manager. The key principles were immutable raw data, explicit directories, fixed class mappings, batch manifests, and verifiable commands.

[Read the full Chinese note]({{ '/blog/2026/reproducible-engineering-toolchain/' | relative_url }})

### May 2026 — RealSense D435i RGB-D acquisition {#realsense-d435i-rgbd-data-collection}

I studied how to collect blueberry RGB-D data that could support maturity recognition, instance segmentation, and 3D localization. The workflow included stream alignment, camera intrinsics, scene metadata, depth-quality checks, structured storage, and controlled coverage of distance, viewpoint, illumination, maturity, and occlusion.

[Read the full Chinese note]({{ '/blog/2026/realsense-d435i-rgbd-data-collection/' | relative_url }})

### July 2026 — Blueberry instance segmentation and 3D localization {#blueberry-instance-segmentation-and-3d-localization}

I reframed the perception task from detecting blueberries to estimating per-fruit masks, maturity, robust depth, and 3D position for robotic harvesting. The current work separates proposed research directions from completed results and emphasizes baselines, layered evaluation, ground-truth measurement, and hand–eye calibration.

[Read the full Chinese note]({{ '/blog/2026/blueberry-instance-segmentation-and-3d-localization/' | relative_url }})

### July 2026 — Reproducible YOLO segmentation and error analysis {#yolo-segmentation-workflow-and-error-analysis}

I standardized annotation conversion, dataset splits, experiment metadata, training, validation, and failure analysis. In one YOLO11s-seg test, most errors on semi-ripe blueberries came from confusion with the two neighboring maturity classes rather than missed detections, motivating clearer labels and condition-aware evaluation.

[Read the full Chinese note]({{ '/blog/2026/yolo-segmentation-workflow-and-error-analysis/' | relative_url }})

[View all Chinese learning notes]({{ '/blog/' | relative_url }})

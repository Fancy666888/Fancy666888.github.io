---
layout: page
title: MaixCAM2 and STM32F407 Three-Axis Gantry Puzzle Device
permalink: /en/projects/gantry-puzzle-device/
description: A vision-guided gantry system for puzzle teaching, piece matching, pick-and-place motion, and rotation correction.
lang: en
nav: false
zh_url: /projects/gantry-puzzle-device/
---

## Overview

This project was developed for the 2026 Beijing College Student Electronic Design Competition. Four blue puzzle pieces are randomly placed in the upper half of an A4 board. The system identifies each piece, calculates its pickup point, target point, and rotation, and then uses a three-axis gantry to reconstruct the taught rectangular layout in the lower half.

The prototype combines a **MaixCAM2 vision and interaction unit**, an **STM32F407 motion controller**, a lead-screw gantry, an electromagnetic gripper, and an external rotation tray. The team received **Third Prize in the Beijing undergraduate division in August 2026**.

{% include figure.liquid loading="eager" path="assets/img/projects/gantry-puzzle-device.jpg" title="Three-axis gantry puzzle prototype" class="img-fluid rounded z-depth-1" %}

## System Architecture

- **Perception:** MaixCAM2 locates the orange A4 board, applies perspective rectification, and segments the blue pieces with HSV thresholds; edge-based and LAB color-difference methods provide fallback paths
- **Teaching and planning:** the four fixed pieces are assembled correctly and taught once before the run; their target contours are stored in A4 millimeter coordinates and reused to solve randomized layouts
- **Motion control:** STM32F407 receives each piece's source coordinates, destination coordinates, and rotation, then drives the X/Y/Z steppers, electromagnetic gripper, servo, and rotation tray
- **Interaction:** a touch interface provides teaching, dry-run, start, and exit actions and displays contours, transport arrows, angles, and matching residuals

## Vision and Piece Matching

The vision pipeline first detects the four corners of the A4 board and rectifies it into a top-down view. It also uses the half containing the pieces to resolve the board's 180-degree orientation ambiguity. Up to 30 frames are examined until three valid four-piece observations have accumulated, which improves tolerance to short reflections and exposure changes.

Each piece is represented by a three- to five-vertex polygon. For every current-to-target candidate, the solver enumerates cyclic vertex correspondences and applies a non-reflective Kabsch rigid fit to estimate rotation, translation, and residual error. It then evaluates the one-to-one assignments of all four pieces and selects the assignment with the smallest total residual. The result contains the pickup centroid, placement centroid, and rotation-tray angle for every piece.

After assembly, the software can verify that the corresponding vertices satisfy the competition's 20 mm tolerance.

## Communication and Automatic Handling

MaixCAM2 communicates with STM32F407 over a 115200-baud UART link. It sends one ASCII job for each piece, in ID order from 1 to 4:

```text
JOB ID=1 SX=20.00 SY=30.00 ANGLE=90.00 DX=100.00 DY=80.00
```

For each job, the STM32 controller picks the piece at the source, places it on the external tray, rotates the tray, picks the piece again, and releases it at the destination. It replies with `READY NEXT_JOB` after the first three pieces and `DONE ALL_4_PIECES` after the fourth, before returning to the camera position. Software limits and job-sequence checks are applied before motion begins.

## Engineering and Verification

- Modular MaixCAM2 application covering vision, geometry, teaching data, planning, communication, control, and touch UI
- STM32F407 state machine for camera position, puzzle origin, pickup, lift, placement, tray rotation, and automatic jobs
- A motion-free dry-run mode for reviewing contours, coordinates, rotations, residuals, and job order before hardware execution
- 26 passing offline tests covering rigid fitting, global assignment, vertex verification, coordinate conversion, serial protocol, controller behavior, UI layout, and synthetic vision scenes
- Existing Keil build log reports zero errors and zero warnings; camera thresholds, hand-eye coordinates, and grasping accuracy still require calibration on the physical prototype

## Technology

MaixCAM2 · MaixPy · Python · OpenCV · NumPy · STM32F407 · C · STM32 HAL · UART · Stepper Motors · Electromagnetic Gripper · Servo · Kabsch Rigid Fitting

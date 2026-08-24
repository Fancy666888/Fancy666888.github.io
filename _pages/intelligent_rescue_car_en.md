---
layout: page
title: OpenCV and STM32F407 Intelligent Rescue Vehicle
permalink: /en/projects/intelligent-rescue-car/
description: An autonomous rescue robot combining color vision, mecanum-wheel motion, and encoder-based PID control.
lang: en
nav: false
zh_url: /projects/intelligent-rescue-car/
---

## Overview

This project was developed for a university-level Engineering Practice and Innovation Competition in April 2026. The robot was required to operate autonomously in a simulated rescue field, identify colored rescue targets, and transport them to a designated safe zone.

Our system integrated vision, task logic, omnidirectional motion, and a front grasping mechanism. It received **Second Prize at the university level**.

{% include figure.liquid loading="eager" path="assets/img/projects/rescue-car.jpg" title="Intelligent rescue vehicle prototype" class="img-fluid rounded z-depth-1" %}

## Final Architecture

Early prototypes explored K210 and OpenMV-based embedded vision. After iterative testing, the final architecture used **OpenCV for visual processing and an STM32F407 as the main controller**.

- **Visual perception:** OpenCV-based color-space conversion, thresholding, contour filtering, and target localization
- **Task logic:** search, tracking, approach, grasp/transport, and return-to-search modes organized around the competition rules
- **Main controller:** STM32F407 for motion-mode transitions, velocity commands, serial communication, and actuator control
- **Chassis:** a four-wheel mecanum platform driven through TB6612 channels, with quadrature-encoder feedback and PID wheel-speed control

## Motion Control

The vision subsystem provides the target category, horizontal offset, and an approximate scale cue. The STM32F407 converts these observations into chassis commands \(v_x\), \(v_y\), and \(\omega_z\). Mecanum-wheel inverse kinematics then produces four wheel-speed targets.

At approximately 10 ms intervals, the controller reads each encoder, estimates the actual wheel speed, computes the PID output, and updates the TB6612 direction signals and PWM duty cycles. This closed loop helps reduce drift caused by motor differences and improves alignment during target approach and transportation.

## Grasping Demonstration

The animation below shows the robot approaching a colored target and using its front mechanism to grasp and transport it.

{% include figure.liquid loading="lazy" path="assets/img/projects/rescue-car-grasping.gif" title="Rescue target grasping demonstration" class="img-fluid rounded z-depth-1" %}

## Engineering Work

- Decomposed the task into perception, decision, chassis-motion, and grasping subsystems
- Iterated through K210, OpenMV, and OpenCV vision approaches before selecting the final solution
- Integrated STM32F407, TB6612 motor drivers, mecanum wheels, quadrature encoders, and PID control
- Debugged target-centering direction, wheel mapping, serial-frame parsing, and motion-control parameters

## Technology

OpenCV · Python · STM32F407 · C · STM32 HAL · Mecanum Wheels · TB6612 · Encoders · PID · UART

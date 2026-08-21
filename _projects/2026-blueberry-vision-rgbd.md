---
layout: page
title: 蓝莓成熟度检测与 RGB-D 数据采集管理系统
description: 面向蓝莓采摘机器人的成熟度识别、深度采集和数据质量管理。
img: assets/img/projects/blueberry-rgbd-system.png
importance: 1
category: 研究项目
published: true
---

## 项目概述

项目围绕蓝莓采摘机器人的视觉感知需求，建设了两个相互衔接的子系统：蓝莓成熟度目标检测应用，以及 RGB-D 数据采集与数据集管理工具。前者提供识别能力，后者为三维定位、算法训练和实验复现积累规范化数据。

{% include figure.liquid loading="eager" path="assets/img/projects/blueberry-detection-result.jpg" title="蓝莓成熟度检测结果示例" class="img-fluid rounded z-depth-1" %}

## 成熟度检测

- 基于 YOLOv8 识别未熟、半熟和成熟蓝莓
- 支持单图检测、置信度调整、历史记录、统计看板与 CSV 导出
- 使用 FastAPI、SQLAlchemy、SQLite、OpenCV 和响应式 Web 界面完成端到端应用

## RGB-D 数据系统

- 接入 Intel RealSense D435i/D405，提供 RGB 与深度伪彩色实时预览
- 支持单帧/连续采集、Session 元数据、数据集索引和完整性审计
- 计算有效深度比例、中心深度、中位深度等质量指标，并生成采集报告
- 同时提供真实相机和演示模式，便于无硬件环境下开发与验证

## 技术栈

Python · YOLOv8 · FastAPI · SQLAlchemy · SQLite · OpenCV · Intel RealSense · ECharts

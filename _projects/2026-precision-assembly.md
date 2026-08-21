---
layout: page
title: 面向精密有序装配的具身智能机械臂协同控制系统
description: 任务语义理解、机器视觉与 AUBO 机械臂协同的精密装配系统。
img: assets/img/projects/precision-assembly-architecture.png
importance: 1
category: 工程实践
published: true
---

## 项目概述

本项目参加 2026 年中国大学生机械工程创新创意大赛具身智能精密装配赛。系统以 Python GUI 控制台为中枢，连接多模态任务理解、VisionMaster 视觉通信和 AUBO ARCS 机械臂仿真/执行环境，完成场景物体识别与六步有序装配任务。

团队“具身不由己”（参赛编号 2340）获**京津冀赛区一等奖并晋级**。

{% include figure.liquid loading="eager" path="assets/img/projects/precision-assembly-task.png" title="精密装配赛任务分析" class="img-fluid rounded z-depth-1" %}

## 系统设计

- **语义理解：** 多模态模型读取任务卡并输出结构化步骤；确定性规则负责白名单、顺序和范围校验
- **视觉通信：** 通过 TCP 触发 VisionMaster 流程，等待真实坐标报文后再进入运动阶段
- **运动控制：** 完成视觉坐标到机械臂坐标的映射，通过 AUBO SDK/RPC 执行 MoveJ、MoveL 等动作
- **流程管理：** 以状态机组织抓取、放置、复位和异常处理，并保留状态、时间戳与执行日志

项目坚持让大模型负责“理解任务”，而由可验证的规则和状态机负责“安全执行”，避免模型直接生成机械臂坐标。

## 技术栈

Python · Qt GUI · 多模态大模型 · VisionMaster · TCP · AUBO ARCS · 状态机

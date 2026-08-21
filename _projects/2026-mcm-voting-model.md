---
layout: page
title: 投票系统的贝叶斯推断与动态评分研究
description: 2026 MCM/ICM Problem C：隐藏观众投票推断与评委—观众评分机制设计。
importance: 2
category: 研究项目
published: true
related_publications: true
---

## 论文概述

本项目源于 2026 MCM/ICM Problem C 参赛论文 _Who Really Keeps Dancing? A Bayesian MCMC Inference and Logistic Dynamic Scoring Framework in Voting Systems_。研究针对只有淘汰结果、缺少真实观众票数的投票节目数据，估计隐藏的粉丝投票，并比较不同评分与淘汰机制。

[阅读参赛论文 PDF]({{ '/assets/pdf/2026-mcm-problem-c.pdf' | relative_url }})

## 方法

- 在分层约束下建立贝叶斯模型，以 Dirichlet 分布描述投票份额先验
- 使用 Metropolis–Hastings MCMC 对隐藏粉丝投票进行抽样推断
- 比较排名制、百分比制及评委干预机制，并使用 Lasso 分析影响因素
- 提出 Logistic Dynamic Weighted System（LDWS），使评委与观众权重随赛程动态变化

## 实验记录

论文使用 34 个赛季、2777 条观测开展分析。后续整理的可复现实验中，LDWS 在已观测周重构任务上取得 0.9655 的准确率，并与排名制基线进行了统计比较。该结果属于当前数据与实验设定下的研究记录，不代表论文已经正式发表。

## 当前状态

参赛论文、实验代码和中间结果已经归档；期刊化框架、复现实验和文字审校仍在继续整理。

---
layout: page
title: Unsupervised Cellular Anomaly Detection
description: Deep unsupervised representation learning and tissue irregularity segmentation
img: assets/img/3.jpg
importance: 3
category: work
related_publications: false
---

## Overview

Labeling histopathology slides requires extensive pathologist annotation time, creating a bottleneck for supervised deep learning models.

This project implements an unsupervised anomaly detection system:
- **Feature Embedding Extraction**: Leveraging self-supervised representations to encode healthy tissue morphology distributions.
- **Anomaly Scoring & Localization**: Measuring latent distance deviations to generate heatmaps highlighting out-of-distribution cellular irregularities.
- **Evaluation Pipeline**: Evaluating segmentation performance using Macro Dice and Per-Class Dice metrics.

### Key Performance Metrics
- **Accuracy**: Achieved **0.942 Macro Dice score** on out-of-distribution tissue patches without requiring manual pixel-level masks during training.
- **Tech Stack**: PyTorch, Computer Vision, Segmentation, Dice & IoU Metrics.

---
layout: page
title: Multi-Class Histopathology Defect Segmentation
description: ConvNeXt-Tiny + UNet pipeline resolving severe 602:1 class imbalance with Log-Smoothed Focal-Dice Loss (0.8003 Dice)
img: assets/img/3.jpg
importance: 1
category: work
related_publications: false
---

## Overview

In automated digital pathology quality control, detecting slide preparation and scanning defects (e.g., knife lines, air bubbles, blur, tissue folds, Venetian blinds) is critical to prevent downstream diagnostic errors. However, defect segmentation poses an extreme class imbalance challenge: normal background and tissue constitute ~4.4 billion pixels, whereas severe artifacts like knife lines account for only ~7.3 million pixels (a **602:1 ratio**).

## Architectural & Engineering Innovations

- **Backbone Architecture**: Engineered a **UNet** framework equipped with a pretrained **`convnext_tiny`** encoder operating at **$512 \times 512$** resolution, capturing fine single-pixel artifact lines while leveraging modern depthwise separable convolutions and $7\times7$ receptive fields.
- **Logarithmic Inverse Frequency Loss**: Standard Cross-Entropy biases predictions toward background, while raw inverse-frequency weighting ($602\times$) destabilizes gradients. Implemented a combined **Multiclass Focal Loss ($\gamma = 2.0$) + Dice Loss**:
  $$\mathcal{L}_{\text{total}} = 0.5 \cdot \mathcal{L}_{\text{Focal}} + 0.5 \cdot \mathcal{L}_{\text{Dice}}$$
  with log-smoothed class alphas creating an optimal $28\times$ relative weighting between rare defects and background without gradient explosion.
- **End-to-End Pipeline**: Modular training, validation, and inference harness supporting multi-scanner normalization and post-processing morphological noise filtration.

## Quantitative Results

| Defect Class | Baseline Dice | Our Model (Dice) | Relative Improvement |
| :--- | :---: | :---: | :--- |
| **Overall Validation** | 0.6200 | **0.8003** | **+29.1% overall** |
| **Knife Line** | 0.3700 | **0.6576** | **+28.76%** |
| **Venetian Blind** | 0.1500 | **0.5361** | **+38.61%** |
| **Penmark / Spot** | 0.6000 | **0.7395** | **+13.95%** |
| **Air Bubble** | 0.9300 | **0.9515** | **+2.15%** |
| **Blur** | 0.7300 | **0.7677** | **+3.77%** |

**Tech Stack**: PyTorch, ConvNeXt, UNet, Albumentations, Multiclass Focal Loss, Dice Loss, Scikit-learn, OpenCV.

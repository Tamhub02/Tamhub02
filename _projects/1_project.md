---
layout: page
title: Histopathology Defect Segmentation
description: ConvNeXt-Tiny + UNet pipeline for Whole Slide Images using Log-Smoothed Focal-Dice Loss (0.8003 Dice)
img: assets/img/3.jpg
importance: 1
category: work
related_publications: false
---

## Overview

Quality control in digital pathology involves identifying slide preparation and scanning defects (such as knife lines, air bubbles, blur, folds, and Venetian blinds) before downstream analysis. This poses a major class imbalance challenge: normal tissue and background constitute ~4.4 billion pixels in the dataset, while knife lines account for only ~7.3 million pixels (a 602:1 ratio).

## Approach

- **Model**: UNet with a `convnext_tiny` encoder operating on $512 \times 512$ patches to capture single-pixel defect lines.
- **Loss Formulation**: Standard cross-entropy collapses on majority classes, while naive inverse-frequency weighting destabilizes training. Used a combined Multiclass Focal Loss ($\gamma = 2.0$) and Dice Loss with log-smoothed class weighting:
  $$\mathcal{L}_{\text{total}} = 0.5 \cdot \mathcal{L}_{\text{Focal}} + 0.5 \cdot \mathcal{L}_{\text{Dice}}$$
- **Post-processing**: Applied morphological filtering (connected component filtering and Gaussian smoothing) to clean boundary noise.

## Results

The model achieved an overall Validation Dice score of **0.8003**, showing notable gains on rare artifact classes:

| Defect Class | Baseline Dice | Model Dice |
| :--- | :---: | :---: |
| Overall Validation | 0.6200 | **0.8003** |
| Knife Line | 0.3700 | **0.6576** |
| Venetian Blind | 0.1500 | **0.5361** |
| Penmark / Spot | 0.6000 | **0.7395** |
| Air Bubble | 0.9300 | **0.9515** |
| Blur | 0.7300 | **0.7677** |

**Stack**: PyTorch, ConvNeXt, UNet, Albumentations, OpenCV.

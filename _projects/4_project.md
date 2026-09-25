---
layout: page
title: Histopathology Object Detection & Backbone Benchmarking
description: MMDetection-based framework benchmarking Faster R-CNN, RetinaNet, RTMDet, and YOLOX with custom interactive COCO/YOLO verification tools
img: assets/img/11.jpg
importance: 4
category: work
related_publications: false
---

## Overview

Accurate localization of cellular structures, mitoses, and morphological defects requires balancing localization precision with high inference speed. Selecting optimal object detection architectures requires rigorous empirical benchmarking against domain-specific histopathology datasets.

This project built a comprehensive detection experimentation, training, and benchmarking framework based on OpenMMLab (**MMDetection**).

## Architectural & Engineering Highlights

- **Multi-Model Benchmark**: Configured, trained, and comparatively evaluated top-tier detector families:
  - **Two-Stage**: *Faster R-CNN* with ResNet-50 Feature Pyramid Networks (FPN).
  - **One-Stage Focal**: *RetinaNet* utilizing focal loss for class imbalance.
  - **Modern Real-Time**: *RTMDet* (including Tiny variants for edge and low-latency deployments) and *YOLOX*.
  - **Anchor-Free / Classic**: *SSD* with VGG-16 backbone.
- **Automated Experimentation Harness**: Standardized config generators for input resolutions ($320\text{px}$, $640\text{px}$), learning rate schedules, and data augmentations (photometric distortions, multi-scale resizing).
- **Interactive Verification Utilities**:
  - Developed custom GUI and CLI visualization viewers (`coco_viewer.py`, `yolo_viewer.py`, `viewer_app.py`) for rapid visual inspection of bounding box predictions, IoU overlaps, and ground-truth alignment.
  - Automated quantitative evaluation reporting mAP@50, mAP@50:95, and inference latency per slide tile.

## Key Outcomes

- Identified optimal trade-offs between two-stage localization precision (Faster R-CNN) and low-latency real-time throughput (RTMDet/YOLOX).
- Integrated model checkpoints and custom verification tooling for rapid pipeline onboarding.

**Tech Stack**: OpenMMLab / MMDetection, PyTorch, CUDA, COCO API, OpenCV, Albumentations, Matplotlib.

---
layout: page
title: Cellular Object Detection Benchmarking
description: MMDetection benchmark comparing Faster R-CNN, RetinaNet, RTMDet, and YOLOX on cellular targets
img: assets/img/11.jpg
importance: 4
category: work
related_publications: false
---

## Overview

Accurate localization of cellular structures requires balancing detection accuracy with inference throughput. This project set up an empirical evaluation pipeline to compare detector families on histopathology targets.

## Approach

- **Model Benchmarking**: Evaluated two-stage (Faster R-CNN with ResNet-50 FPN), one-stage (RetinaNet), and real-time models (RTMDet, YOLOX) using MMDetection.
- **Standardized Pipeline**: Unified input resolutions (320px, 640px), augmentation strategies, and learning rate schedules.
- **Inspection Tools**: Built lightweight viewer utilities (`coco_viewer.py`, `yolo_viewer.py`) to inspect bounding box predictions, IoU overlaps, and ground-truth alignments interactively.

## Results

- Quantified latency vs. accuracy trade-offs across candidate models, identifying suitable backbones for real-time and high-precision use cases.
- Streamlined model evaluation workflows with reusable visualization tooling.

**Stack**: MMDetection, PyTorch, CUDA, COCO API, OpenCV.

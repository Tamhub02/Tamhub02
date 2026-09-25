---
layout: page
title: HPC Whole Slide Image (WSI) Pipeline
description: High-throughput gigapixel tile loading, non-rigid stitching, and deep learning inference
img: assets/img/12.jpg
importance: 1
category: work
related_publications: false
---

## Overview

In digital pathology, Whole Slide Images (WSIs) often exceed **50 gigabytes** per pyramidal TIFF file, containing billions of pixels that cannot fit into standard GPU memory all at once.

This project engineered an end-to-end WSI reconstruction and multi-tile inference pipeline capable of:
- **Asynchronous Tile Loading**: Multi-processed I/O queues utilizing `OpenSlide` and memory-mapped shared memory.
- **Non-Rigid Tile Stitching**: Fast spatial alignment algorithm handling microscopic shift and optical distortion.
- **Batched CUDA Inference**: Feeding segmented tissue patches directly into PyTorch/TensorRT pipelines with zero GPU memory starvation.

### Key Performance Metrics
- **Throughput**: 4.2x faster slide assembly compared to traditional sequential loaders.
- **Scale**: Seamlessly processes 50GB+ slides with flat memory footprints and zero memory leaks.
- **Tech Stack**: Python, PyTorch, CUDA, OpenSlide, Multi-processing, NumPy.

---
layout: page
title: WSI Tile Streaming and Reconstruction
description: Multithreaded tile streaming, coordinate mapping, and canvas stitching for 50GB+ pyramidal slides
img: assets/img/12.jpg
importance: 2
category: work
related_publications: false
---

## Overview

Whole Slide Images (WSIs) often exceed 50GB per pyramidal TIFF or SVS file. Processing gigapixel canvases requires streaming patches efficiently without exhausting host memory or stalling GPU queues.

## Approach

- **Concurrent Tile Loading**: Built streaming batch generators using `ThreadPoolExecutor` and OpenSlide, decoupling disk I/O from preprocessing.
- **Coordinate-Space Stitching**: Automatically calculates canvas geometry from tile coordinates $(x, y)$ and places patches into memory-mapped arrays.
- **Processing Pipeline**: Standardized preprocessing (normalization), threshold-based artifact masking, and morphological post-processing.
- **Config-Driven**: Handled paths, tile dimensions, batch sizes, and execution modes (sequential vs. parallel) through a unified config schema.

## Results

- Reduced slide reconstruction time by **4.2x** compared to single-threaded loading.
- Maintained a bounded memory footprint across 50GB+ slides with zero memory leaks.

**Stack**: Python, OpenSlide, ThreadPoolExecutor, NumPy, OpenCV.

---
layout: page
title: TensorRT & AMP Low-Latency Accelerator
description: Deep learning model compilation, latency benchmarking, and mixed precision optimization
img: assets/img/7.jpg
importance: 2
category: work
related_publications: false
---

## Overview

High-throughput medical AI workloads require sub-10ms inference latencies to enable real-time interactive pathologist workflows.

This project developed a comprehensive compilation and benchmarking engine:
- **TensorRT Engine Compilation**: Serializing PyTorch models via ONNX into hardware-tailored NVIDIA TensorRT execution engines.
- **Automatic Mixed Precision (AMP)**: Analyzing FP32 vs FP16 vs INT8 quantization tradeoffs across latency, memory bandwidth, and Macro Dice segmentation accuracy.
- **Layer & Kernel Profiling**: Identifying compute vs memory bound operators using NVIDIA Nsight Systems and PyTorch Profiler.

### Key Performance Metrics
- **Latency**: Reduced end-to-end inference latency from **18.4 ms** down to **4.1 ms** (3.5x+ boost).
- **Fidelity**: Maintained **99.8%** segmentation fidelity relative to FP32 baselines.
- **Tech Stack**: NVIDIA TensorRT, ONNX Runtime, PyTorch AMP, CUDA, Docker.

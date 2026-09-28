---
layout: page
title: Vision-Language Models for Pathology
description: LoRA fine-tuning on Qwen2.5-VL and multi-agent consensus workflows for histopathology evaluation
img: assets/img/7.jpg
importance: 3
category: work
related_publications: false
---

## Overview

Applying Vision-Language Models (VLMs) to pathology requires connecting visual tissue features with structured clinical terminology. Standard zero-shot prompts often miss fine histopathological nuances.

## Approach

- **Model Adaptation**: Fine-tuned Qwen2.5-VL using LoRA (Low-Rank Adaptation) on domain-specific pathology datasets for parameter-efficient training.
- **Structured Reasoning**: Implemented Chain-of-Thought (CoT) prompts to guide inspection from cell morphology to tissue architecture and artifact checks.
- **Multi-Agent Consensus**: Designed a multi-agent deliberation setup where specialized agents inspect distinct features and an aggregation step reconciles disagreements.
- **Semi-Supervised Training**: Incorporated pseudo-labeling on unlabeled slide tiles and cross-validation to improve cross-scanner consistency.

## Results

- Improved diagnostic consistency across multiple slide scanners compared to single zero-shot prompts.
- Structured reasoning logs allow complete inspection of intermediate steps.

**Stack**: Qwen2.5-VL, LoRA, PyTorch, Hugging Face Transformers, Ollama, OpenRouter.

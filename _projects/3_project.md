---
layout: page
title: Medical Vision-Language Model (VLM) & Multi-Agent Deliberation
description: Fine-tuning Qwen2.5-VL with LoRA, Chain-of-Thought clinical reasoning, and a 7-agent consensus framework for automated pathology review
img: assets/img/7.jpg
importance: 3
category: work
related_publications: false
---

## Overview

Integrating multimodal Vision-Language Models (VLMs) into digital pathology requires bridging complex visual tissue features with structured clinical diagnostics. Standard zero-shot VLM outputs often struggle with nuanced histopathological findings and lack the robustness required for mission-critical diagnostics.

This project engineered a hybrid VLM fine-tuning and multi-agent deliberation framework that delivers validated, interpretable diagnostic conclusions.

## Key Engineering Highlights

- **VLM Adaptation with LoRA**: Fine-tuned state-of-the-art multimodal vision-language architectures (**Qwen2.5-VL**) on domain-specific histopathology datasets using Low-Rank Adaptation (LoRA), unlocking higher parameter efficiency and preserving general reasoning capabilities.
- **Chain-of-Thought (CoT) Prompt Engineering**: Formulated structured CoT reasoning templates enforcing systematic tissue inspection: cellular morphology $\rightarrow$ tissue architecture $\rightarrow$ artifact differentiation $\rightarrow$ final diagnostic decision.
- **Multi-Agent Consensus Framework**:
  - Developed a **7-agent sequential and ensemble architecture** (`pathology_multiagent`) where specialized sub-agents independently evaluate cell types, defect patterns, and clinical risks.
  - Implemented an automated consensus arbiter that aggregates predictions, resolves inter-agent discrepancies, and calibrates confidence metrics before producing the final clinical verdict.
- **Multi-Task & Semi-Supervised Learning**: Leveraged pseudo-labeling on unlabeled WSI tiles and K-Fold cross-validation, substantially lifting diagnostic consistency across disparate slide scanners.

## Results & Capabilities

- **Diagnostic Alignment**: High consensus agreement across diverse biopsy specimens, outperforming standalone single-agent prompts.
- **Auditability**: Complete diagnostic rationale tracing through intermediate agent deliberation logs.
- **Extensible Integration**: Designed for deployment with local Ollama runners or cloud-based OpenRouter API endpoints.

**Tech Stack**: Qwen2.5-VL, LoRA (PEFT), PyTorch, Hugging Face Transformers, Ollama, OpenRouter, JSON Schema Validation.

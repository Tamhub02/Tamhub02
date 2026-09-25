---
layout: about
title: about
permalink: /
subtitle: AI Engineer at <a href="https://www.airamatrix.com/" target="_blank">Airamatrix</a>

profile:
  align: right
  image: prof_pic.jpg
  image_circular: true # crops the image to make it circular
  more_info: >
    <p>AI Engineer</p>
    <p>Airamatrix</p>
    <p>Mumbai, India</p>

selected_papers: false # includes a list of papers marked as "selected={true}"
social: true # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

Hi, I am **Tamajit Mondal**! I am an **AI Engineer at Airamatrix** specializing in deep learning architectures, computational pathology (Whole Slide Imaging - WSI), vision-language models (VLM), and high-throughput computer vision pipelines.

My primary engineering and research focus spans:

- **🔬 Multi-Class Histopathology Defect Segmentation**: Engineering UNet architectures with ConvNeXt backbones at $512 \times 512$ resolution to detect scanning and preparation defects, solving extreme 602:1 class imbalance using log-smoothed Focal and Dice loss to achieve a **0.8003 Validation Dice score** (+28.8% on knife lines, +38.6% on Venetian blind artifacts).
- **⚡ High-Throughput WSI Streaming & Reconstruction**: Designing production-grade, asynchronous multithreaded tile streaming and coordinate-space stitching frameworks capable of processing **50GB+ pyramidal TIFF/SVS slides** with OpenSlide and ThreadPool parallelization, delivering 4.2x faster assembly with zero memory leaks.
- **🤖 Vision-Language Models (VLM) & Multi-Agent Deliberation**: Fine-tuning multimodal models (**Qwen2.5-VL**) with LoRA and Chain-of-Thought (CoT) diagnostic reasoning, building a **7-agent consensus deliberation system** for automated clinical pathology review.
- **🎯 Cellular Object Detection & Benchmark Harness**: Benchmarking modern detection backbones (Faster R-CNN, RetinaNet, RTMDet, YOLOX) using **MMDetection** on cellular tissue structures with custom interactive inspection and verification tooling.
- **🧠 Feature Embeddings & Unsupervised Anomaly Detection**: Building patch-level representation pipelines with high-dimensional feature embeddings and k-NN anomaly scoring to detect out-of-distribution cellular irregularities.

Feel free to explore my [projects](/Tamhub02/projects/), view my [CV](/Tamhub02/cv/), check my GitHub repositories, or reach out via email for collaborations!

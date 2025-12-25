---
layout: single
title: "End-to-end open-vocabulary video visual relationship detection using multi-modal prompting (TPAMI 2025)"
collection: portfolio
teaser: "/images/tpami_method.png"
paper_url: "https://ieeexplore.ieee.org/abstract/document/10966052/"  # 替换为你的 PDF 链接
code_url: "https://github.com/wangyongqi558/EOV-MMP-VidVRD"      # 替换为你的代码链接
author_profile: false
abstract_short: "An end-to-end framework that eliminates the dependency on pre-trained trajectory detectors, allowing for a more seamless open-vocabulary detection."
---

## Abstract
Open-vocabulary Video Visual Relationship Detection (Open-VidVRD) aims to detect subject-predicate-object triplets where some categories are unseen during training. We propose a **Multi-modal Prompting** method to effectively adapt the pre-trained CLIP model for this task. By optimizing prompts on both visual and textual branches, the model gains the ability to generalize to novel relationship categories without extensive retraining.

## Methodology
The framework focuses on two key adaptations of the CLIP architecture:
1.  **Dual-side Prompt Tuning**: We introduce learnable prompt tokens into both the image encoder and text encoder. This allows the model to align video features with semantic descriptions more flexibly.
2.  **Vision-guided Language Prompting**: Instead of static text prompts, we use visual context to guide the generation of language prompts, helping the model "see" the relationship before naming it.
3.  **Spatial-Temporal Context**: Learnable conditional prompts are used to capture the dynamic changes in video frames.

![Methodology](/images/aaai24_method.png)

## Key Results
* **Performance**: Achieved a significant boost in mAP (Mean Average Precision) on the VidVRD benchmark.
* **Zero-shot Generalization**: Showed strong ability to detect relationships like "standing on" or "chasing" even when they were not in the training set.
* **Efficiency**: Outperformed previous state-of-the-art methods while maintaining a more efficient tuning process.

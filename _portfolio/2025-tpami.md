---
layout: single
title: "End-to-end open-vocabulary video visual relationship detection using multi-modal prompting (TPAMI 2025)"
collection: portfolio
teaser: "/images/tpami_method.png"
paper_url: "https://ieeexplore.ieee.org/abstract/document/10966052/"  # 替换为你的 PDF 链接
code_url: "https://github.com/wangyongqi558/EOV-MMP-VidVRD"      # 替换为你的代码链接
author_profile: false
abstract_short: "This work proposes a unified end-to-end framework for Open-vocabulary Video Visual Relationship Detection. By integrating a relationship-aware trajectory detector with CLIP-based multi-modal prompting, our method eliminates the dependency on pre-trained closed-set detectors and significantly enhances generalization to novel objects and interactions."
---

## Abstract
Open-vocabulary video visual relationship detection aims to expand video visual relationship detection beyond anno
tated categories by detecting unseen relationships between both seen and unseen objects in videos. Existing methods usually use
trajectory detectors trained on closed datasets to detect object trajectories, and then feed these trajectories into large-scale
pre-trained vision-language models to achieve open-vocabulary classification. Such heavy dependence on the pre-trained trajec
tory detectors limits their ability to generalize to novel object categories, leading to performance degradation. To address this
challenge, we propose to unify object trajectory detection and relationship classification into an end-to-end open-vocabulary
framework. Under this framework, we propose a relationship aware open-vocabulary trajectory detector. It primarily consists
of a query-based Transformer decoder, where the visual encoder of CLIP is distilled for frame-wise open-vocabulary object detec
tion, and a trajectory associator. To exploit relationship context during trajectory detection, a relationship query is embedded
into the Transformer decoder, and accordingly, an auxiliary relationship loss is designed to enable the decoder to perceive
the relationships between objects explicitly. Moreover, we propose an open-vocabulary relationship classifier that leverages the rich
semantic knowledge of CLIP to discover novel relationships. To adapt CLIP well to relationship classification, we design a
multi-modal prompting method that employs spatio-temporal visual prompting for visual representation and vision-guided
language prompting for language input. Extensive experiments on two public datasets, VidVRD and VidOR, demonstrate the
effectiveness of our framework. Our framework is also applied to a more difficult cross-dataset scenario to further demonstrate
its generalization ability.

## Methodology

We propose a novel **end-to-end framework** for Open-vocabulary Video Visual Relationship Detection (Open-VidVRD) that jointly models object trajectory detection and relationship classification. Unlike existing methods that rely on trajectory detectors pre-trained on closed datasets, our framework eliminates the domain gap and enhances generalization to novel object and relationship categories.

The framework consists of two primary components:

### 1. Relationship-aware Open-vocabulary Trajectory Detector

This component performs frame-wise detection and associates them into coherent trajectories.

* **Query-based Transformer Decoder**: We distill the visual encoder of CLIP into the decoder to enhance open-vocabulary object representation.
* **Relationship Queries**: To explicitly perceive interaction context during detection, we embed dedicated "relationship queries" and utilize an auxiliary relationship loss.
* **Auxiliary Object Classifier**: To improve novel object category detection, we use a vision-guided prompting method that combines learnable continuous and conditional language prompts for CLIP.

### 2. Open-vocabulary Relationship Classifier

This module predicts relationship categories between the generated object trajectories using CLIP’s rich semantic knowledge.

* **Multi-modal Prompting**: We apply prompting to both the visual and textual branches of CLIP to better adapt it to the video domain.
* **Spatio-temporal Visual Prompting**: This module decouples spatial and temporal modeling to capture dynamic contexts across frames.
* **Vision-guided Language Prompting**: We generate dynamic language prompts based on visual features to discover novel relationships.


![Methodology](/images/aaai24_method.png)

## Key Results
* **Performance**: Achieved a significant boost in mAP (Mean Average Precision) on the VidVRD benchmark.
* **Zero-shot Generalization**: Showed strong ability to detect relationships like "standing on" or "chasing" even when they were not in the training set.
* **Efficiency**: Outperformed previous state-of-the-art methods while maintaining a more efficient tuning process.

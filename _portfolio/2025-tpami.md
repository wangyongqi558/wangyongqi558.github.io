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


![Methodology](/images/tpami_method.png)

## Experiments

### Datasets & Evaluation Metrics
We evaluated our framework on two large-scale benchmarks for video relationship detection:
* **VidVRD**: Contains 1,000 videos with 35 object and 132 predicate categories.
* **VidOR**: Contains 10,000 videos with 80 object and 50 predicate categories.
* **Metrics**: We used **mean Average Precision (mAP)** and **Recall@K (R@50/100)** to evaluate triplet detection and **$mAP_o$** for object trajectory quality.
* **Settings**: Experiments were conducted under **Novel-split** (unseen categories) and **All-split** (standard) settings.

### Main Results
Our end-to-end framework consistently outperformed existing methods (e.g., RePro, VidVRD-II, ALPro) that rely on pre-trained closed-set trajectory detectors.
* **VidVRD Dataset**: On the **Novel SGDet** task, our method achieved a **21.94% improvement in $mAP_o$** and a **2.89% gain in mAP**.
* **VidOR Dataset**: Our method improved $mAP_o$ by 1.22% and mAP by 1.61% in the novel split, demonstrating strong generalization in complex, long-video scenarios.
* **Cross-Dataset Generalization**: When trained on VidOR and tested on VidVRD, our method surpassed the "upper bound" results of several previous state-of-the-art models, proving its robustness in real-world, open-world scenarios.

![Experiment](/images/tpami_result.png)
![Experiment](/images/tpami_result2.png)
![Experiment](/images/tpami_result3.png)

### 3.3 Ablation Studies
Detailed ablations confirmed the effectiveness of each component:
* **End-to-End Training**: Unifying trajectory detection and relationship classification yielded better results than training them separately.
* **Relationship-Aware Detector**: The inclusion of **Relationship Queries** and the **Auxiliary Object Classifier** significantly enhanced the perception of interactions and novel objects.
* **Multi-modal Prompting**: Combining spatio-temporal visual prompting with vision-guided language prompting was found to be critical for discovering novel relationships.

### 3.4 Qualitative Analysis
* **Trajectory Visualization**: Qualitative examples demonstrate that our method accurately detects novel objects (e.g., "lizard") that are missed by baseline models like RePro.

<div style="text-align: center; margin-top: 20px;">
  <img src="/images/tpami_results.png" alt="Experimental Results" style="width: 80%; border: 1px solid #eee; border-radius: 8px;">
  <p style="color: #666; font-size: 0.9em;">Table: Performance comparison on VidVRD and VidOR benchmarks.</p>
</div>

---
layout: single
title: "METOR: A Unified Framework for Mutual Enhancement of Objects and Relationships (IJCAI 2025)"
collection: portfolio
teaser: "/images/ijcai25_method.png"
paper_url: "https://arxiv.org/pdf/2505.06663"  # 替换为你的 PDF 链接
code_url: "https://github.com/wangyongqi558/METOR"      # 替换为你的代码链接
author_profile: false
abstract_short: "Open-vocabulary Video Visual Relationship Detection (Open-VidVRD) aims to identify subject-predicate-object triplets without being restricted by pre-defined categories. Most existing approaches adopt a cascaded pipeline—detecting object trajectories first and then classifying their relationships. However, such decoupled designs suffer from error propagation and fail to capture the inherent correlation between objects and interactions. To overcome these challenges, we propose METOR (Mutual EnhancemenT of Objects and Relationships), a novel query-based unified framework. METOR is designed to jointly model both tasks, allowing them to mutually inform and enhance one another. By shifting from a sequential to a collaborative architecture, METOR significantly mitigates suboptimal performance caused by detection inaccuracies and achieves robust open-vocabulary generalization."
---

## Abstract
Open-vocabulary video visual relationship detection aims to detect objects and their relationships in videos without being restricted by predefined object or relationship categories. Existing methods leverage the rich semantic knowledge of pre-trained vision-language models suchas CLIP to identify novel categories. They typically adopt a cascaded pipeline to first detect objects and then classify relationships based on the detected objects, which may lead to error propagation and thus suboptimal performance. In this paper, we propose Mutual EnhancemenT of Objects and Relationships (METOR), a query-based unified framework to jointly model and mutually enhance object detection and relationship classification in open-vocabulary scenarios. Under this framework, we first design a CLIP-based contextual refinement encoding module that extracts visual contexts of objects and relationships to refine the encoding of text features and object queries, thus improving the generalization of encoding to novel categories. Then we propose an iterative enhancement module to alternatively enhance the representations of objects and relationships by fully exploiting their interdependence to improve recognition performance. Extensive experiments on two public datasets, VidVRD and VidOR, demonstrate that our framework achieves state-of-the art performance. 

## Methodology
The framework focuses on two key adaptations of the CLIP architecture:
1.  **Dual-side Prompt Tuning**: We introduce learnable prompt tokens into both the image encoder and text encoder. This allows the model to align video features with semantic descriptions more flexibly.
2.  **Vision-guided Language Prompting**: Instead of static text prompts, we use visual context to guide the generation of language prompts, helping the model "see" the relationship before naming it.
3.  **Spatial-Temporal Visual Prompting**: Learnable conditional prompts are used to capture the dynamic changes in video frames.

![Methodology](/images/aaai24_method.png)

## Experiments

### Datasets and Evaluation
We evaluate our method on two large-scale benchmarks:
* **VidVRD**: 1,000 videos covering 35 object and 132 predicate categories.
* **VidOR**: 10,000 videos covering 80 object and 50 predicate categories.
* **Settings**: Training on **Base** categories and testing on **Novel** and **All** splits.

### Main Results
Our method consistently outperforms existing works like RePro, VidVRD-II, and ALPro. Notably, we achieve a **nearly 10% mAP improvement** on the Novel split of VidVRD.

![Experiments](/images/aaai24_result.png)

### Qualitative Analysis
T-SNE visualizations demonstrate that our spatio-temporal visual prompting effectively adapts the CLIP image encoder, pulling features of the same categories closer while pushing different categories apart for both base and novel predicates.

<div style="text-align: center;">
  <img src="/images/aaai24_tsne.png" alt="T-SNE Visualization" style="width: 50%; max-width: 500px; border-radius: 8px;">
</div>

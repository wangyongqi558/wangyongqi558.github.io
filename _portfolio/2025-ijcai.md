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
METOR (Mutual EnhancemenT of Objects and Relationships) is a query-based unified framework designed to jointly model object detection and relationship classification. By moving away from traditional cascaded pipelines, METOR exploits the interdependence between entities and their interactions to achieve superior open-vocabulary performance.

### Contextual Refinement Encoding (CRE)
To enhance generalization to novel categories, the CRE module extracts specific visual contexts for both objects and relationships to refine the initial encoding process.
* **Contextual Token Integration**: Learnable object and relationship context tokens are inserted into the CLIP visual encoder to capture global semantic information from the video.
* **Semantic Refinement**: These contexts are used to refine the CLIP text features and object queries, providing instance-specific knowledge that helps the model recognize unseen categories more accurately.

### Iterative Enhancement Module (IEM)
The IEM module is the core of our "mutual enhancement" strategy, consisting of multiple layers that alternately update object and relationship representations.
* **Spatio-Temporal Modeling**: In each layer, subject and object features are combined with global embeddings to generate relationship features through a spatio-temporal Transformer.
* **Mutual Feedback Loop**: The extracted relationship features are fed back to refine the subject and object representations. This cyclical process ensures that localization and classification tasks benefit from each other's context.

### Unified Modeling & Training
METOR simplifies the Open-VidVRD process by optimizing all components in an end-to-end manner:
* **Joint Optimization**: By modeling objects and relationships simultaneously, the framework significantly reduces the error propagation common in decoupled systems.
* **Training Objective**: The model is trained using a combination of contrastive losses for classification and trajectory losses for precise spatio-temporal localization.

![Methodology](/images/ijcai25_method.png)

## Experiments

### 3.1 Experimental Setup
* **Datasets**: We evaluated METOR on the **VidVRD** (1,000 videos) and **VidOR** (10,000 videos) benchmarks.
* **Settings**: The model was trained only on base categories and tested on both **Novel** (unseen relationships) and **All** (standard) splits.
* **Metrics**: We used **mean Average Precision (mAP)** and **Recall@K (R@50/100)** for relationship classification, and **$mAP_o$** to evaluate object trajectory quality.

### 3.2 Main Results (SGDet Task)
METOR achieves state-of-the-art performance across both datasets, significantly reducing error propagation compared to traditional cascaded pipelines.

![Experiments](/images/ijcai25_result.png)

### 3.3 Key Findings
* **Significant Improvement**: On the VidOR Novel-split, METOR outperforms the best competing method by a relative margin of **53.06%** (3.75% vs. 2.45% mAP).
* **Mutual Enhancement**: The iterative refinement process effectively reduces both **Object Errors (OE)** and **Relationship Errors (RE)** by ensuring that localization and classification tasks benefit from each other's context.
* **Superior Generalization**: By leveraging CLIP-based contextual refinement, the model demonstrates a robust ability to identify novel interactions in dynamic and complex real-world video scenes.

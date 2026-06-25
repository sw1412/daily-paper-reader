---
title: Anomaly Detection by an Ensemble of  Random Pairs of Hyperspheres
title_zh: 基于随机超球对的集成异常检测
authors: "Walid Durani, Collin Leiber, Khalid Durani, Claudia Plant, Christian Böhm"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vM4PIjsJDG"
tags: ["query:hsi"]
score: 6.0
evidence: 随机超球集成异常检测
tldr: 该论文提出ADERH，一种基于随机超球对的集成异常检测方法。它利用异常点稀疏且偏离正常模式的特性，通过多尺度超球构建隔离异常。该方法无需训练，可应用于高光谱异常检测，但未考虑光谱维度特性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vm4pijsjdg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 369, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vm4pijsjdg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 372, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vm4pijsjdg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 1049, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vm4pijsjdg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1234, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vm4pijsjdg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1417, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vm4pijsjdg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 663, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 825, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 886, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1581, \"height\": 848, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1207, \"height\": 609, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1049, \"height\": 832, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 766, \"height\": 1643, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1393, \"height\": 1029, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 944, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1450, \"height\": 663, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vm4pijsjdg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 743, \"height\": 956, \"label\": \"Table\"}]"
motivation: 现有异常检测方法复杂且依赖假设，需要简单高效方案。
method: 构建多尺度超球对，利用Pitch和Concept概念区分异常。
result: 在多种异常检测任务上达到竞争性能。
conclusion: 通用异常检测方法适用于高光谱场景。
---

## Abstract
Anomaly detection is a crucial task in data mining, focusing on identifying data points that deviate significantly from the main patterns in the data. This paper introduces Anomaly Detection by an Ensemble of Random Pairs of Hyperspheres (ADERH), a new isolation-based technique leveraging two key observations: (i) anomalies are comparatively rare, and (ii) they typically deviate more strongly from general patterns than normal data points. Drawing on a delta-separation argument, ADERH constructs an ensemble of multi-scale hyperspheres built upon randomly paired data points to identify anomalies. To address inevitable overlaps between anomalous and normal regions in the feature space, ADERH integrates two complementary concepts: Pitch, which highlights points near hypersphere boundaries, and NDensity, which down-weights hyperspheres centered on sparse (and often anomalous) regions. By averaging these local, density-adjusted ``isolation'' indicators across many random subsets, ADERH yields robust anomaly scores that clearly separate normal from abnormal samples. Extensive experiments on diverse real-world datasets show that ADERH consistently outperforms state-of-the-art methods while maintaining linear runtime scalability and stable performance across varying hyperparameter settings.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的中文总结。

# 论文中文总结：基于随机超球对的集成异常检测（ADERH）

## 1. 核心问题与整体含义
*   **研究动机与背景**：异常检测旨在识别数据中显著偏离主流模式的少数点，是数据挖掘中的关键任务。现有方法（如基于密度、深度学习的算法）在处理大规模数据时面临计算复杂度高的问题。基于隔离的方法（如Isolation Forest， INNE）虽然效率较高，但存在局限性，例如无法捕捉局部复杂模式、对参数敏感等。本文旨在提出一种更高效、鲁棒且能有效处理异常与正常样本重叠问题的新方法。

## 2. 提出的方法论
*   **核心思想**：基于异常的“稀疏性”和“偏离性”两大特性，通过构建一个由多个随机点对生成的超球组成的集成系统来隔离异常。该方法利用“δ-分隔”假设，即正常点形成紧凑区域，而异常点位于这些区域边界之外。

*   **关键技术细节与算法流程**：
    1.  **构建集成系统**：
        *   从数据集中随机抽取n个大小为ω的子集。
        *   在每个子集中，为每个点随机配对另一个点，形成一个点对。
        *   对于每一个点对，以其两个点为中心，以两点间欧氏距离的一半为半径，构建两个超球。所有超球构成一个多尺度集。
    2.  **处理重叠问题**：为了解决异常可能落入正常超球内（Anomaly Contamination）或异常点自身成为超球中心（Anomaly Hyperspheres）的问题，引入两个互补概念：
        *   **Pitch**：衡量一个点距离某个超球中心的相对位置（距离与半径之比）。靠近边界的异常点会获得较高的Pitch值。
        *   **NDensity** (归一化密度)：衡量一个超球的局部密度。位于稀疏区域的异常点为中心的超球密度较低，其NDensity会被降低权重。
    3.  **计算异常分数**：
        *   对于每个超球，结合NDensity和Pitch计算一个**加权Pitch（WPitch）**。高异常分数仅在点靠近边界（Pitch高）且超球密度低（NDensity低）时出现。
        *   对每个数据点，在其覆盖的所有超球中找到WPitch最小（即最“正常”）的覆盖（Smallest Cover， SC），该值作为该点在该子集的**基础异常分数（F）**。
        *   最终，将一个数据点在**所有n个子集中的基础异常分数取平均**，作为其全局**集成隔离得分I**。这种平均化降低了单个超球带来的方差。
    *   **总结公式与逻辑**：本质上，算法通过随机配对和减半半径来构建紧凑的、多尺度的超球，然后通过一个结合边界距离（Pitch）和局部密度（NDensity）的乘性指标来为每个点打分，最后通过集成平均来提升鲁棒性。

## 3. 实验设计
*   **数据集**：使用了来自ADBenchmark的**19个真实世界数据集**，包括低维到高维、不同异常比例的数据，例如Optdigits, Wbc, Lymphography, Celeba, Skin, Pendigits, Wdbc, AD-Toothbrush, Musk等。
*   **Benchmark**：与**15种**现有方法进行了对比，主要分为几类：
    *   **基于隔离的方法**：IForest, EIF, INNE, PIDForest, Deep Isolation Forest (DIF)。
    *   **基于距离/密度的方法**：LOF。
    *   **边界/单类方法**：OCSVM, DeepSVDD。
    *   **集成方法**：LODA, LSCP (文中提及，但未在主要结果表中出现)。
    *   **深度学习方法**：RCA, RDP, SLAD, DTE, UniCAD。
    *   **经典覆盖方法**：GEM, DTM。
*   **评估指标**：主要使用AUC-ROC和AUC-PR。

## 4. 资源与算力
*   文中提到实验运行在 **Intel Core i7-10700K (3.8 GHz, 32 GB RAM)** 的CPU平台上。
*   并未明确说明使用的GPU型号、数量或具体的总训练时长。论文主要强调其线性时间复杂度，并提到了其在CPU上的高效性。

## 5. 实验数量与充分性
*   **实验数量**：非常充分。
    *   **主实验**：在19个数据集上使用默认参数，与15个基线进行比较。
    *   **网格搜索实验**：对ADERH和主要基线（IForest, INNE, PIDForest, EIF, LOF, LODA, DeepSVDD, RDP, SLAD）进行了超参数网格搜索。
    *   **消融实验**：评估了去除Pitch或NDensity、使用全半径超球等不同配置的性能。
    *   **稳定性实验**：测试了不同超球缩放因子（α=0.25, 0.5, 0.75, 1.0）。
    *   **集成 vs 单子集实验**：证明了集成的必要性。
    *   **可扩展性实验**：展示了算法随数据量和维度增加的运行时间变化。
*   **实验充分性与公平性**：非常充分和公平。实验设置了多种操作模式的对比，进行了统计显著性检验（Wilcoxon符号秩检验），并报告了平均排名。所有对比都尽量遵循原论文的默认参数，并补充了网格搜索，确保了对比的全面性和公平性。

## 6. 主要结论与发现
*   **性能优越**：ADERH在AUC-ROC和AUC-PR两项指标上，无论是在默认参数还是最优参数下，都显著优于所有15种先进的对比方法，取得了最高的平均排名（AUC-ROC: 1.68, AUC-PR: 2.26）。
*   **鲁棒性强**：ADERH对超参数（子集大小、子集数量）的变化不敏感，性能稳定，其标准差在所有方法中最低。
*   **效率高**：算法时间复杂度为O(n ω m)，呈线性，可扩展到大规模数据集。
*   **组件有效**：消融实验证实，Pitch、NDensity以及半径缩放因子（使用一半距离）都是该方法取得优异性能的关键组成部分。特别是**乘性融合**（Pitch * (1 - NDensity)）相比**加性融合**效果更好。

## 7. 优点
*   **方法新颖**：提出了“随机点对超球”的构建方式，用简单的操作生成了多尺度的局部结构，设计巧妙。
*   **设计有效**：Pitch和NDensity的结合分别解决了“边界异常”和“稀疏中心异常”两个核心难题，提升了在复杂重叠场景下的判别能力。
*   **鲁棒高效**：通过集成平均显著降低了方差，对参数不敏感。同时保持线性复杂度，兼顾了性能和效率。
*   **理论支撑充分**：基于“δ-分隔”假设，对方法的有效性（通过概率不等式）和方差（通过Rademacher复杂度或类似理论）进行了理论分析，并证明了集成能降低方差。

## 8. 不足与局限
*   **高维挑战**：作为一个基于距离的方法，ADERH仍可能受“维数灾难”影响。在高维空间中，点间距离分布趋于集中，会削弱正常与异常点的区分度。文中也承认了这一点。
*   **应用局限性**：在像高光谱异常检测这样的领域，可能无法直接利用光谱的物理特性或空间上下文信息。这是一个通用方法，需要结合深度特征变换等方法才能更好地适应特定领域（如高光谱）。
*   **实验覆盖**：虽然数据集多样，但主要集中在表格数据和部分视觉（特征）数据，没有涉及纯粹的图像、视频或序列数据。这对其通用性的验证有一定限制。
*   **默认参数依赖经验**：子集大小ω和数量n的默认设定（ω=18, n=256）基于经验观察，虽然鲁棒，但缺少更严谨的选择机制。

（完）

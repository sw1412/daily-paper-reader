---
title: "Mahalanobis++: Improving OOD Detection via Feature Normalization"
title_zh: Mahalanobis++：通过特征归一化改进分布外检测
authors: "Maximilian Müller, Matthias Hein"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vutMcZl50l"
tags: ["query:hsi"]
score: 5.0
evidence: 分布外检测方法可用于异常检测
tldr: 该论文针对基于马氏距离的OOD检测方法在不同模型上性能波动的问题，发现特征范数变化违反了高斯假设。提出对预对数特征进行L2归一化，使其更符合正态分布假设，从而稳定提升检测性能。在44个模型上实验验证了有效性。该方法可迁移至高光谱异常检测任务，通过特征归一化提高异常检测的鲁棒性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1710, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 818, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 892, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1783, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1788, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1752, \"height\": 1049, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1399, \"height\": 2002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vutmczl50l/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 903, \"height\": 999, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 774, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1760, \"height\": 636, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1744, \"height\": 1342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 777, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1759, \"height\": 1348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 787, \"height\": 526, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1813, \"height\": 1341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1810, \"height\": 1340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1742, \"height\": 1341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1812, \"height\": 1340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1595, \"height\": 1346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1771, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1773, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1769, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 805, \"height\": 1787, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 627, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1639, \"height\": 2103, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vutmczl50l/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 979, \"height\": 458, \"label\": \"Table\"}]"
motivation: 马氏距离OOD检测性能在不同模型上差异大，源于特征范数变化违反高斯假设。
method: 对预对数特征进行L2归一化，使其更好地满足共享协方差的高斯分布假设。
result: 在44个模型上显著提升了OOD检测的一致性和性能。
conclusion: 简单特征归一化可有效改善基于马氏距离的OOD检测。
---

## Abstract
Detecting out-of-distribution (OOD) examples is an important task for deploying reliable machine learning models in safety-critial applications. While post-hoc methods based on the Mahalanobis distance applied to pre-logit features are among the most effective for ImageNet-scale OOD detection, their performance varies significantly across models. We connect this inconsistency to strong variations in feature norms, indicating severe violations of the Gaussian assumption underlying the Mahalanobis distance estimation. We show that simple $\ell_2$-normalization of the features mitigates this problem effectively, aligning better with the premise of normally distributed data with shared covariance matrix. Extensive experiments on 44 models across diverse architectures and pretraining schemes show that $\ell_2$-normalization improves the conventional Mahalanobis distance-based approaches significantly and consistently, and outperforms other recently proposed OOD detection methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题背景**：基于马氏距离（Mahalanobis distance）的后验分布外（OOD）检测方法在ImageNet级任务中效果显著，但其性能在不同模型间波动极大。例如，SwinV2-B-In21k模型的FPR高达58.2%，而ViT-B16-In21k-augreg仅31.3%。这种不一致性严重限制了该方法在安全关键应用中的可靠性。
- **核心动机**：论文发现性能波动的根本原因是**特征范数（feature norm）的强烈变化**严重违背了马氏距离估计所依赖的**类条件高斯分布且共享协方差矩阵**这一基本假设。特征范数不仅在不同类别间差异巨大，还在同一类别内呈重尾分布，导致马氏得分与特征范数高度相关，使得小范数的OOD样本被错误分类为ID样本。
- **整体含义**：该工作旨在诊断并修复马氏距离方法的内在缺陷，提供一种简单、通用的后验修复方案，使OOD检测性能在不同模型上稳定且显著提升。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：通过**ℓ2归一化**将特征投影到单位球面上，消除特征范数的影响，使特征更符合高斯分布假设，从而改善协方差矩阵的估计。
- **关键技术细节**：
  - **特征归一化**：对于原始预逻辑特征向量 \(\phi(x)\)，计算归一化版本 \(\hat{\phi}(x) = \phi(x) / \|\phi(x)\|_2\)。
  - **重新估计参数**：使用归一化后的训练特征重新计算每类的均值 \(\hat{\mu}_c\) 和共享协方差矩阵 \(\hat{\Sigma}\)：
    \[
    \hat{\mu}_c = \frac{1}{N_c}\sum_{i:y_i=c} \hat{\phi}(x_i),\quad \hat{\Sigma} = \frac{1}{N}\sum_{c}\sum_{i:y_i=c}(\hat{\phi}(x_i)-\hat{\mu}_c)(\hat{\phi}(x_i)-\hat{\mu}_c)^T.
    \]
  - **OOD得分**：对于测试样本 \(x_t\)，计算归一化特征 \(\hat{\phi}(x_t)\) 到各类的马氏距离，取最小值并取负作为OOD得分：
    \[
    s_{\text{Maha++}}(x_t) = -\min_c (\hat{\phi}(x_t)-\hat{\mu}_c)^T \hat{\Sigma}^{-1} (\hat{\phi}(x_t)-\hat{\mu}_c).
    \]
  - **相对马氏距离的扩展**：同样对相对马氏距离（Relative Mahalanobis）应用相同的归一化处理，得到rMaha++。
- **算法流程**（文字说明）：
  1. 取训练集所有样本的预逻辑特征。
  2. 对每个特征进行ℓ2归一化。
  3. 计算归一化后的每类均值向量。
  4. 计算归一化后的共享协方差矩阵（加权平均）。
  5. 对测试样本，先归一化其特征，再计算到各类的马氏距离，输出最小的距离取负作为OOD得分。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **ImageNet级实验**：
  - **ID数据集**：ImageNet-1k。
  - **OOD数据集**：OpenOOD基准的五个数据集：NINCO（已清洗的OOD）、iNaturalist、SSB-hard、OpenImages-O、Texture。
  - **模型**：44个公开预训练模型，涵盖多种架构（ConvNeXt、Swin、DeiT、EVA、ViT、ResNet、Mixer、EfficientNet等）和预训练方案（ImageNet-21k预训练、CLIP、Supervised Contrastive等）。
  - **对比方法**：MSP、MaxLogit、Energy、Energy+ReAct、ViM、KNN、NNguide、Neco、GMM、GEN、fDBD、Relative Mahalanobis、Mahalanobis（原始），以及它们的归一化版本。
  - **评价指标**：主要报告FPR@TPR95%（假阳性率在真阳性率95%时），同时也报告AUC。
- **CIFAR-100实验**：
  - **ID数据集**：CIFAR-100。
  - **OOD数据集**：tiny ImageNet、MNIST、SVHN、Texture、Places、CIFAR-10（OpenOOD设置）。
  - **模型**：8个模型（SwinV2-S、DeiT3-S、ConvN-T、ViT-B32、ViT-S16、RN18、RN34、RNxT29-32）。
  - **对比方法**：MSP、Ash、KNN、ViM、Mahalanobis等，以及它们的归一化版本。
- **噪声鲁棒性测试**：使用Bitterwolf等人提出的17个“单元测试”（噪声分布），统计FPR≥10%的失败个数。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **未明确说明**：论文正文及附录中均未提及使用的GPU型号、数量或训练时长。仅致谢了DFG、Carl Zeiss Foundation以及BMBF的资助，无具体硬件信息。

### 5. 实验数量与充分性：大概做了多少组实验，这些实验是否充分、是否客观、公平

- **实验数量**：
  - ImageNet级：44个模型 × 5个OOD数据集 × 约15种方法，主要结果表（Table 4/6/8/9/10）包含大量对比，且每个模型都计算了FPR和AUC。
  - CIFAR-100：8个模型 × 6个OOD数据集，结果在Table 3/15/16。
  - 消融与分析：特征范数分布（Fig.3）、QQ图（Fig.4/9）、方差对齐（Table 1/7）、特征范数与得分的相关性（Fig.5/7）、分布对比（Fig.10/11）等。
  - 噪声鲁棒性：17个单元测试 × 44模型（Table 5/17）。
  - 总共数百组实验。
- **充分性与公平性**：
  - 模型覆盖广泛，包括不同架构、规模、预训练方式。
  - 对比方法均为近年来有影响力的后验方法，且实现遵循原文/官方代码（如OpenOOD标准配置）。
  - 所有方法使用相同的训练集统计量（无额外数据），马氏距离及归一化版本均正确计算。
  - 实验设计客观、公平，尤其强调了在augreg等模型上归一化不改善但也不损害性能的情况。

### 6. 论文的主要结论与发现

- **主要发现**：
  - 马氏距离OOD检测的性能波动源于特征范数的强烈方差，导致严重偏离高斯假设（重尾分布、协方差不一致）。
  - 特征范数与马氏得分高度相关：小范数OOD样本被误判为ID，大范数ID样本可能被误判为OOD。
- **核心结论**：
  - **Mahalanobis++**（即ℓ2归一化后使用马氏距离）在**41/44个模型**上优于原始马氏距离，平均FPR降低**7.6%**。
  - 相对马氏距离归一化版本（rMaha++）也在39/44个模型上优于其未归一化版本。
  - 在ImageNet数据集上，Mahalanobis++平均FPR为**34.9%**，优于最接近的对比方法ViM（42.5%），提升约**7个百分点**。
  - 在CIFAR-100上同样一致提升，但幅度较小（平均FPR从52.52%降至44.13%）。
  - 对噪声分布的检测鲁棒性显著提升：大部分模型“单元测试”失败数量降为零。
- **对比其他方法**：Mahalanobis++在大多数模型上优于KNN、NNguide、ViM、Energy等，尤其是在高精度模型上表现突出。

### 7. 优点：方法或实验设计上有哪些亮点

- **方法简洁有效**：仅需在预处理阶段增加特征归一化步骤，无需修改训练过程，计算开销与原始马氏距离相同，即插即用。
- **理论支撑充分**：从马氏距离的基本假设出发，通过统计检验（QQ图、方差偏差得分）系统诊断问题根源，再提出针对性修复。
- **实验规模宏大**：覆盖44个模型、多个OOD基准，且公开代码，确保可复现性。
- **实验设计客观**：考虑不同预训练方案（CLIP、监督对比学习、各种ViT微调），并特别讨论了augreg这类特例，展示了方法的鲁棒性。
- **开源贡献**：代码已公开在GitHub，便于社区使用和进一步研究。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **覆盖的局限性**：
  - 主要限于ImageNet和CIFAR-100两个ID数据集，未在更大规模（如ImageNet-21k作为ID）或更多领域（医学、工业检测）进行验证。
  - 仅评估了后验OOD检测方法，未与需要修改训练的方法（如CIDER、SSD+）在公平条件下直接比较（但文中指出后者需要改变训练，不适用于后验场景）。
- **对特定模型的失效**：有3个模型（其中两个是augreg训练的ViT）归一化后性能未改善，但该模型原始性能已很好，且归一化也未造成明显损害。
- **理论假设的近似性**：归一化后特征的类条件高斯性更好，但并非完美高斯；在某些方向上仍有偏差，可能影响极端OOD检测。
- **计算与存储**：共享协方差矩阵的维度与特征维度平方成正比，对于高维特征（如d=1024），求逆和存储成本较高，但这是马氏距离方法的固有代价，归一化不增加此开销。
- **噪声检测的残余问题**：尽管噪声鲁棒性大幅提升，但仍有极少数模型在某些噪声分布上FPR>10%（如Table 17中ConvNeXt-B的16个失败降为15个，但未完全消除）。

（完）

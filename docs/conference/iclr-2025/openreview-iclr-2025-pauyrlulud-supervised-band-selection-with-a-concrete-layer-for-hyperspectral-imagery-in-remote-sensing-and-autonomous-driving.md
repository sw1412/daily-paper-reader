---
title: Supervised Band Selection with a Concrete Layer for Hyperspectral Imagery in Remote Sensing and Autonomous Driving
title_zh: 基于具体层的高光谱图像监督波段选择在遥感和自动驾驶中的应用
authors: "Yaniv Zimmer, Ofir Lindenbaum, Oren Glickman"
date: 2024-09-27
pdf: "https://openreview.net/pdf?id=PauyrluLud"
tags: ["query:hsi"]
score: 8.0
evidence: 高光谱图像监督波段选择有助于分类
tldr: 针对高光谱数据维度高、现有波段选择方法计算复杂且难以适应下游任务的问题，本文提出一种基于Gumbel-Softmax具体选择层的即插即用监督波段选择方法，可动态选择最优波段并无需预处理。实验表明该方法在分类等任务上有效提升性能，为高光谱图像分类提供了一种高效的预处理手段。
source: ICLR-2025-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 681, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1346, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1164, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1373, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1385, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 646, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 639, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-pauyrlulud/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 712, \"height\": 156, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-iclr-2025-pauyrlulud/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-pauyrlulud/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1255, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-pauyrlulud/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-pauyrlulud/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-pauyrlulud/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1140, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-pauyrlulud/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1140, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-pauyrlulud/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1140, \"height\": 461, \"label\": \"Table\"}]"
motivation: 高光谱数据维度高，现有波段选择方法计算复杂且无法针对特定任务自适应选择。
method: 提出一种基于Gumbel-Softmax具体选择层的即插即用监督波段选择方法，可无缝集成到下游模型中。
result: 在多个高光谱数据集上验证了方法的有效性和鲁棒性。
conclusion: 该方法为高光谱图像分类等任务提供了一种高效、自适应的波段选择方案。
---

## Abstract
Hyperspectral imagery captures rich spectral information, which is valuable for a wide range of applications but poses challenges due to high data dimensionality. Current band selection methods are often computationally intensive, non-embedded, or lack adaptability for specific tasks. We address this gap by introducing a novel plug-and-play embedded method for supervised band selection in hyperspectral imagery, utilizing a concrete selector layer based on the Gumbel-Softmax re-parameterization trick. Our approach allows for dynamic and task-specific selection of optimal bands, eliminating the need for pre-processing and enabling seamless integration with downstream models. We evaluated the method on four hyperspectral datasets, covering three remote sensing benchmarks and an autonomous driving task, demonstrating consistent improvements over state-of-the-art methods. This is the first work to perform comprehensive band-selection research on an autonomous driving dataset of this type, and the first to employ a concrete layer for supervised band selection. Our findings highlight the potential of this approach for real-time hyperspectral analysis in applications such as autonomous driving and environmental monitoring, laying the groundwork for further exploration of efficient, domain-specific band selection.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

高光谱成像（HSI）能够捕获每个像素点的完整光谱信息，显著提升材料区分能力，在遥感、自动驾驶、农业、医疗等领域具有巨大潜力。然而，高光谱数据的高维度特性带来了硬件成本、存储传输、实时处理等多重挑战。现有波段选择方法要么计算密集，要么作为独立的预处理步骤，缺乏针对特定下游任务的适应性，导致所选波段可能并非最优。

针对此问题，本文提出一种**即插即用、嵌入式、监督式的波段选择方法**，利用**基于Gumbel-Softmax重参数化技巧的具体选择层（Concrete Selector Layer）**，在训练过程中动态、任务特定地选出最优波段子集，无需任何预处理，并能无缝集成到任意下游深度学习模型（如CNN、UNet）中。该方法首次在自动驾驶高光谱数据集上进行了全面的波段选择研究，也是首个将具体层用于监督波段选择的工作。其意义在于为实时、低成本的高光谱分析系统（如自动驾驶、环境监测）提供了一种高效解决方案。

## 2. 方法论：核心思想与关键技术细节

### 2.1 问题形式化

给定输入 \(X \in \mathbb{R}^{n \times s_1 \times s_2}\)（\(n\)个光谱波段，每个波段为\(s_1 \times s_2\)图像），目标为选择一个指标向量 \(I \in \{0,1\}^n\)（\(\|I\|_0 = k\)，\(k<n\)），以及一个下游模型 \(f_\theta\)，使得：
\[
\arg\min_{\theta, I} \frac{1}{m}\sum_{i=1}^m \text{Loss}\big(f_\theta(x_i \odot I), y_i\big)
\]

### 2.2 具体选择层（Concrete Selection Layer）

- **结构**：在输入层之后插入一个具体选择层，其核心是一个可学习的logits矩阵 \(L \in \mathbb{R}^{k \times n}\)，\(k\)为目标波段数，\(n\)为总波段数。每个\(n\)维行向量对应一个波段选择器。
- **Gumbel-Softmax重参数化**：在前向传播时，对矩阵\(L\)的每一行施加Gumbel-Softmax操作，得到软掩码矩阵 \(M \in \mathbb{R}^{k \times n}\)：
  \[
  M_{i,j} = \frac{\exp((L_{i,j} + G_{i,j}) / \tau)}{\sum_{r=1}^n \exp((L_{i,r} + G_{i,r}) / \tau)},
  \quad G_{i,j} = -\log(-\log(u_{i,j})), \; u_{i,j} \sim \text{Uniform}(0,\beta)
  \]
  其中 \(\tau>0\) 为温度参数（控制离散程度），\(\beta\) 为Gumbel噪声尺度。
- **训练过程**：初始温度 \(\tau\) 较大，每个batch后乘以衰减系数 \(\alpha\)，逐步降低温度，使软掩码逐渐接近离散的one-hot向量。通过梯度下降联合优化\(L\)和下游模型参数。
- **推理过程**：直接取logits矩阵每行argmax得到one-hot掩码，确定性选择。
- **组掩码机制**：标准特征选择作用于单个特征，但波段选择需要保留或剔除整个波段（即该波段所有像素）。本文修改具体层使其**对整个波段（即所有空间位置）施加相同的掩码**，实现分组选择。

### 2.3 新颖初始化方案

为解决随机初始化导致的重复选择问题（多个选择器收敛到相同波段），提出**分段初始化**：将\(n\)个波段均匀划分为\(k\)段，每个logits行向量初始化时对对应段内的元素赋予正均值，其它段赋予负均值（保持整体Xavier分布）。该初始化引导每个选择器关注不同的光谱区域，提高了所选波段的多样性，且学习过程中仍然允许调整（例如可以跳过某些段或在一个段内选多个波段）。

## 3. 实验设计

### 3.1 数据集与任务

| 类型 | 数据集 | 波段数 | 光谱范围 (nm) | 类别数 | 样本量 | 任务 |
|------|--------|--------|---------------|--------|--------|------|
| 遥感 | Pavia University | 103 | 430-860 | 9 | ~42k pixels | 像素级分类（语义分割） |
| 遥感 | Salinas | 204 | 430-2500 | 16 | ~54k pixels | 同上 |
| 遥感 | Chikusei | 128 | 363-1018 | 19 | ~5.9M pixels | 同上 |
| 自动驾驶 | HSI-Drive V2 | 25 | 598-976 | 10 (简化5类) | 756 images | 场景语义分割 |

### 3.2 下游模型

- **遥感任务**：采用3D CNN（来自Ben Hamida等2018），输入为5×5像素块，包含三个3D卷积层和一个全连接层，使用交叉熵损失，batch size=256，10折交叉验证。
- **自动驾驶任务**：采用UNet架构，编码器4个卷积块（下采样0.5，kernel 3），解码器对称上采样，使用加权交叉熵损失。按7:1:2划分训练/验证/测试。

### 3.3 对比的基线方法

- **全对比**（Pavia, Salinas）：SNMF、Genetic、BS-Net-Conv、TAttMSRecNet、DARecNet-BS、DRL、PCA、SpaBS、EHBS。
- **部分对比**（Chikusei, HSI-Drive V2）：仅对比在Pavia/Salinas上表现最好的三个方法（SNMF、BS-Net-Conv、Genetic），涵盖三大主流家族（稀疏聚类、重构自编码器、进化搜索）。

### 3.4 评估指标

- **遥感**：Overall Accuracy (OA), Average Accuracy (AA), Kappa系数。
- **自动驾驶**：Mean IoU, Overall IoU, Weighted IoU, Mean Precision, Mean Recall, Overall Accuracy, Mean Accuracy。

### 3.5 超参数设置

遥感数据集：\(\tau=1.5\), \(\alpha=0.99998\), \(\beta=0.15\)；自动驾驶数据集：\(\tau=8.5\), \(\alpha=0.9999\), \(\beta=0.15\)。logits矩阵采用分段Xavier初始化。

## 4. 资源与算力

- **硬件**：NVIDIA GeForce GTX 1080 Ti（单卡）。
- **软件**：Python 3.8, PyTorch 2.2.2。
- **内存**：自动驾驶数据集需~400MB，遥感数据集需~1GB。
- **时间**：每个epoch 1-5分钟。**未明确给出总epoch数和总训练时长**，但文中提到“the number of epochs is reported in the experiment settings”，实际实验设置部分未具体说明（附录中也未提及）。推测每个实验（不同k值）运行了数十到数百epoch。

## 5. 实验数量与充分性

### 5.1 实验数量

- **数据集**：4个（3遥感+1自动驾驶）。
- **目标波段数**：多个（3, 5, 8等），各数据集不同。
- **基线方法**：最多9种（Pavia/Salinas），最少3种（Chikusei/Drive）。
- **重复次数**：遥感任务使用10折交叉验证报告均值和标准差；自动驾驶使用固定划分但报告均值（未说明重复次数，可能单次运行或多次平均）。
- **消融实验**：
  - 对比两种初始化方案（随机 vs. 分段），展示了选择多样性差异（图6）。
  - 分析了所选波段的稳定性和一致性（图5b）。
  - 测试了不同超参数（\(\tau, \alpha\)）的影响（在方法部分提到，但未给出具体消融表格）。
- **额外分析**：展示了训练过程中波段选择的变化（图6），以及不同方法所选波段的差异（图5a）。

### 5.2 实验充分性与公平性

- **充分性**：在四个不同场景（城市、农业、混合、自动驾驶）的数据集上验证，覆盖像素级和图像级语义分割任务，且包括少量波段（3个）的极端情况，证明了方法的泛化能力。
- **公平性**：所有基线方法均采用原始作者推荐的设置或同一框架下的公平比较（如使用相同的下游模型骨干）。但未对所有基线进行大规模超参数调优，可能对某些基线不公平（文中未明确说明是否对基线也进行了调优）。
- **统计显著性**：报告了均值和标准差，但**未进行统计显著性检验**（如t检验或ANOVA），结论的可靠性依赖数值大小和方差。
- **缺失实验**：未在更多样化的数据集（如医疗、农业高光谱）上测试；未与最新的基于注意力或Transformer的波段选择方法对比；未进行更多超参数鲁棒性分析（如温度衰减率的影响）。

## 6. 主要结论与发现

1. **方法性能领先**：在所有四个数据集上，提出的Gumbel具体选择层方法在**几乎所有目标波段数下均优于所有基线方法**，尤其当选择少量波段（如3个）时提升显著。
2. **任务自适应**：方法倾向于选择对特定任务最关键的波段，而非像重构方法那样覆盖全光谱，因此**能以更少波段获得更高精度**，有利于低成本传感器设计。
3. **选择一致性**：在自动驾驶数据集上，随着目标波段数增加，最初选出的最重要波段保持不变（图5b），表明学习到的选择具有稳定性和可解释性。
4. **初始化重要性**：分段初始化解决了随机初始化导致的**重复选择**问题，提升了所选波段的多样性，进而提高精度。
5. **计算效率**：虽然需要调优多个超参数，但方法本身可嵌入训练，无需预处理，推理时仅需一个矩阵乘法，具有实时潜力。

## 7. 优点

- **创新性**：首次将具体层（Concrete Layer/Gumbel-Softmax）应用于**监督式、分组**的高光谱波段选择，并且是首个在自动驾驶高光谱数据集上开展完整波段选择研究的工作。
- **嵌入式设计**：作为即插即用层，可无缝集成到任意深度学习模型，**无需独立预处理步骤**，避免了预处理与下游任务目标不一致的问题。
- **可微性与端到端训练**：利用Gumbel-Softmax实现离散选择的梯度传播，使整个系统可以端到端优化。
- **新颖初始化**：提出的分段初始化简单有效，增强了选取的多样性和稳定性。
- **广泛验证**：在遥感（像素级）和自动驾驶（图像级）两个不同领域的语义分割任务上均取得SOTA结果，证明了方法的通用性。

## 8. 不足与局限

1. **超参数敏感**：温度参数 \(\tau\)、衰减率 \(\alpha\)、噪声尺度 \(\beta\) 需要精细调优，且不同任务/数据集的最佳设置差异较大（遥感 \(\tau=1.5\)，自动驾驶 \(\tau=8.5\)），影响了方法的易用性和泛化性。
2. **计算开销**：虽然每个epoch时间较短，但需要多轮实验以调整超参数和不同目标波段数，总体调优成本较高。
3. **未进行充分的统计显著性检验**：仅报告均值和标准差，未证明差异显著，削弱了结论的统计力度。
4. **对比基线不全面**：未与最新的基于Transformer或注意力机制的波段选择方法（如TA-CNN、光谱注意力网络）对比，缺少对当前技术前沿的覆盖。
5. **应用场景有限**：仅验证了语义分割任务，未测试分类、目标检测等其他常见高光谱任务；也未在更大规模、更多噪声的真实部署数据上验证。
6. **理论分析不足**：缺少对学习到的波段可解释性的深入分析（如哪些波段对哪些类别重要），以及收敛性证明。

（完）

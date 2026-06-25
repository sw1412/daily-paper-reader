---
title: "Leaving No OOD Instance Behind: Instance-Level OOD Fine-Tuning for Anomaly Segmentation"
title_zh: 不留任何OOD实例：用于异常分割的实例级分布外微调
authors: "YUXUAN ZHANG, Zhenbo Shi, Han ye, Shuchang Wang, Zhidong Yu, Shaowei Wang, Wei Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=oCOOe8tt8v"
tags: ["query:hsi"]
score: 6.0
evidence: 实例级分布外微调用于异常分割
tldr: 该论文针对异常分割中小目标性能差的问题，提出实例级分布外（OOD）微调框架LNOIB。通过理论分析全局目标的不足，设计实例级损失和特征分离约束。在多个数据集上，该方法有效提升了小异常的分割精度。该方法可迁移至高光谱异常检测任务中。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ocooe8tt8v/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1417, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ocooe8tt8v/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1357, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ocooe8tt8v/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1314, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ocooe8tt8v/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1381, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ocooe8tt8v/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1408, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ocooe8tt8v/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1133, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ocooe8tt8v/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1418, \"height\": 348, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 724, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 700, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 635, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 847, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 705, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 705, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 725, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1308, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ocooe8tt8v/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 722, \"height\": 165, \"label\": \"Table\"}]"
motivation: 现有全局级OOD微调对小异常分割效果差。
method: 提出实例级OOD目标及特征分离约束。
result: 在分割基准上显著提升小异常检测性能。
conclusion: 实例级方法通用性强，适用于高光谱异常分割。
---

## Abstract
Out-of-distribution (OOD) fine-tuning has emerged as a promising approach for anomaly segmentation. Current OOD fine-tuning strategies typically employ global-level objectives, aiming to guide segmentation models to accurately predict a large number of anomaly pixels. However, these strategies often perform poorly on small anomalies. To address this issue, we propose an instance-level OOD fine-tuning framework, dubbed LNOIB (Leaving No OOD Instance Behind). We start by theoretically analyzing why global-level objectives fail to segment small anomalies. Building on this analysis, we introduce a simple yet effective instance-level objective. Moreover, we propose a feature separation objective to explicitly constrain the representations of anomalies, which are prone to be smoothed by their in-distribution (ID) surroundings. LNOIB integrates these objectives to enhance the segmentation of small anomalies and serves as a paradigm adaptable to existing OOD fine-tuning strategies, without introducing additional inference cost. Experimental results show that integrating LNOIB into various OOD fine-tuning strategies yields significant improvements, particularly in component-level results, highlighting its strength in comprehensive anomaly segmentation.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在自动驾驶等场景中，语义分割模型通常基于封闭集训练，遇到未见过类别（分布外 OOD 实例）时无法正确预测，带来安全风险。异常分割（Anomaly Segmentation, AS）旨在识别这些 OOD 区域。现有一种有效策略是 OOD 微调（OOD fine-tuning），它使用包含 ID 和 OOD 区域的混合内容图像来增强模型泛化能力。然而，当前 OOD 微调方法大多采用**全局级目标**（global-level objectives），旨在尽可能精确地预测尽可能多的异常像素，导致**小异常**（small anomalies）被忽略。而小异常的误判（如小动物、小障碍物）可能造成重大安全风险。
- **整体含义**：论文提出实例级 OOD 微调框架 **LNOIB**（不留任何 OOD 实例），确保模型检测所有 OOD 实例（无论大小），从而提升异常分割的安全性和全面性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：
  1. 对全局级目标进行理论分析，证明小异常因占像素比例小而被忽视，进而提出**实例级目标**（instance-level objective）使每个异常获得同等优化权重。
  2. 针对卷积操作中 OOD 特征被 ID 环绕平滑的问题，提出**特征分离目标**（feature separation objective），使 OOD 原型与 ID 原型明确分离。
- **关键技术细节**：
  - **全局级目标**（式 1）：\( L_{glob} = \frac{1}{N_{in}}\sum_{i\in\Omega_{in}} l_{in}(s(x_i),y_i) + \frac{1}{N_{out}}\sum_{j\in\Omega_{out}} l_{out}(s(x_j),y_j) \)
  - **实例级目标**（式 5）：\( L_{ins} = L_{in} + \frac{1}{N}\sum_{o_k\in\mathcal{O}}\sum_{x_j\in\Omega_{o_k}}\frac{1}{|\Omega_{o_k}|} l_{out}(s(x_j),y_j) \)，确保每个异常独立优化。
  - **预测目标**（式 6）：\( L_{pred} = \alpha L_{glob} + (1-\alpha)L_{ins} \)，平衡全局质量和实例完整性。
  - **特征分离目标**：
    - ID 语义损失（式 9）：\( L_{sem} = \frac{1}{N\cdot K}\sum_{p_{o_k}\in\mathcal{P}}\sum_{q_c\in\mathcal{Q}} \text{cosSim}(p_{o_k}, q_c) \)
    - 最近邻损失（式 12）：\( L_{near} = \frac{1}{N\cdot M}\sum_{p_{o_k}\in\mathcal{P}}\sum_{q_c\in\mathcal{Q}_{o_k}} \text{cosSim}(p_{o_k}, q_c) \)
    - 特征分离目标（式 13）：\( L_{feat} = \beta L_{sem} + (1-\beta)L_{near} \)
  - **总目标**（式 14）：\( L_{LNOIB} = \gamma_1 L_{pred} + \gamma_2 L_{feat} \)
- **算法流程**：
  1. 使用混合数据集（COCO 目标粘贴到 Cityscapes）进行 OOD 微调。
  2. 计算全局级损失和实例级损失的加权和作为预测目标。
  3. 从骨干网络中间特征（阶段 2/3/4）上采样到 1/4 尺寸，计算 OOD 实例原型和 ID 类别原型，然后计算 ID 语义损失和最近邻损失作为特征分离目标。
  4. 将两目标加权求和作为总损失进行反向传播。
  5. 推理时沿用原方法生成异常分数，不增加额外计算。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **ID 数据集**：Cityscapes（19 类城市场景，2975 训练 + 500 验证）。
- **OOD 数据集**：
  - Fishyscapes Static (FS Static) – 30 张验证图像（来自 Pascal 混合）。
  - Fishyscapes Lost & Found (FS L&F) – 100 张验证图像。
  - SMIYC-RA (RoadAnomaly) – 10 张验证图像（道路异常）。
  - SMIYC-RO (RoadObstacle) – 30 张验证图像（道路障碍）。
  - Road Anomaly – 60 张验证图像。
- **Benchmark**：SMIYC 官方组件级指标（sIoU, PPV, F1*）和像素级指标（AuPRC, FPR95），以及实例级指标（iAP, iAP50）。
- **对比方法**：SynBoost, FlowEneDet, RbA, RPL, CSL, RWPM, PixOOD 等 SOTA 方法，以及 OOD 微调基线：EM, PEBAL, M2A。

## 4. 资源与算力

- **硬件**：一台 Ubuntu 22.04 服务器配备 4 块 RTX 3090Ti GPU（每块 24 GB 显存），以及另一台配备 2 块 NVIDIA A100 GPU（每块 80 GB 显存）。
- **训练框架**：PyTorch。
- **未明确说明**：具体训练时长、总 GPU 小时数未在文中给出，仅说明了硬件配置。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 在 5 个数据集上报告组件级和像素级结果（表 1、表 2）。
  - 在 FS Static 和 FS L&F 上报告实例级指标（表 5）。
  - 对 EM、PEBAL、M2A 三种基线进行消融实验：
    - 分别消融全局/实例目标（表 3a）、特征分离组件（表 3b）。
    - 在不同数据集（FS L&F 和 Road Anomaly）上验证组件通用性（表 6、表 7）。
    - 超参数 α、β、γ₂、M、τ 的调优（图 5、图 6、图 7）。
  - 模拟不完美实例掩膜的鲁棒性实验（表 8）。
  - 封闭集性能对比（表 4）。
- **充分性**：实验覆盖了多个数据集、多种基线、全面的消融和超参数分析，使用 3 次运行取均值并报告标准差，确保公平性和可复现性。实验设计较为充分、客观。

## 6. 论文的主要结论与发现

- 实例级目标（Lins）能有效弥补全局目标对小异常的忽略，但与全局目标结合（Lpred）效果最佳。
- 特征分离目标（Lfeat）通过 ID 语义损失与最近邻损失互补，进一步优化 OOD 特征的区分性。
- LNOIB 可无缝集成到现有 OOD 微调策略（EM、PEBAL、M2A），显著提升组件级和实例级指标，对像素级指标也有一定改善，且不增加推理成本。
- 封闭集性能几乎无损失（mIoU 下降 <1%）。
- 对不完美实例掩膜具有鲁棒性。

## 7. 优点：方法或实验设计上的亮点

- **理论分析**：通过 Lemma、Theorem 和 Corollary 严格证明了全局目标忽视小异常的原因（dominant instance effect），为实例级设计提供了理论基础。
- **范式通用性**：LNOIB 不是具体损失函数，而是可适应多种全局目标的范式，只需替换 lin 和 lout 即可扩展到 EM、PEBAL、M2A。
- **无额外推理成本**：训练后沿用原方法生成异常分数，保持效率。
- **全面消融**：不仅从预测目标、特征分离目标两个维度消融，还考虑了不同数据集、超参数、不完美掩膜等，实验覆盖全面。
- **实例级指标**：引入 iAP/iAP50 进一步佐证对小异常的提升，增加评估维度。

## 8. 不足与局限

- **超参数依赖**：对于某些全局目标值显著不同的方法，可能需要额外调优 γ₁、γ₂（文中采用统一值 γ₁=γ₂=1）。
- **小异常质量仍不完美**：定性结果（图 4 第一行）显示小异常分割仍可能不完全。
- **评测局限于验证集**：仅使用验证图像，未在更挑战的测试集上评估泛化能力（但 SMIYC 等基准的测试集不提供组件级 API）。
- **OOD 微调本身局限性**：仅模拟有限 OOD 场景，无法覆盖真实世界全部分布外模式。
- **未扩展到高光谱等其他场景**：论文未直接验证高光谱异常检测，但提到可作为未来工作。

（完）

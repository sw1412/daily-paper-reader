---
title: "HSOD-BIT-V2: A Challenging Benchmark for Hyperspectral Salient Object Detection"
title_zh: "HSOD-BIT-V2: 具有挑战性的高光谱显著目标检测基准"
authors: "Yuhao Qiu, Shuyan Bai, Tingfa Xu, Peifu Liu, Haolin Qin, Jianan Li"
date: 2025-04-11
pdf: "https://ojs.aaai.org/index.php/AAAI/article/download/32711/34866"
tags: ["query:hsi"]
score: 8.0
evidence: 高光谱显著目标检测
tldr: 高光谱显著目标检测（HSOD）因缺乏大规模数据集而发展受限。本文构建了目前最大的高光谱显著目标检测基准HSOD-BIT-V2，包含小目标、前后景相似等挑战样本。同时提出Hyper-HRNet高分辨率网络，充分利用光谱信息实现精准检测。实验表明，在五个挑战场景中，该方法显著优于RGB和现有高光谱方法。该基准和网络将推动高光谱目标检测研究和应用。
source: AAAI-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32711/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 876, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32711/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 884, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32711/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 879, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32711/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1841, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32711/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32711/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 835, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32711/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 848, \"height\": 550, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 887, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 877, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1859, \"height\": 655, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 884, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 871, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 870, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32711/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 869, \"height\": 237, \"label\": \"Table\"}]"
motivation: 现有显著目标检测在复杂场景下表现不佳，高光谱数据有潜力但缺乏大规模标注数据集。
method: 构建最大HSOD数据集，并提出Hyper-HRNet网络，利用高光谱丰富光谱特征进行高分辨率显著目标检测。
result: 在五个挑战性场景中，所提方法在各项指标上均超越当前最优RGB和高光谱方法。
conclusion: 该研究为高光谱目标检测提供了基准与方法，展示了光谱信息在困难场景中的优势。
---

## Abstract
Salient Object Detection (SOD) is crucial in computer vision, yet RGB-based methods face limitations in challenging scenes, such as small objects and similar color features. Hyperspectral images provide a promising solution for more accurate Hyperspectral Salient Object Detection (HSOD) by abundant spectral information, while HSOD methods are hindered by the lack of extensive and available datasets. In this context, we introduce HSOD-BIT-V2, the largest and most challenging HSOD benchmark dataset to date. Five distinct challenges focusing on small objects and foreground-background similarity are designed to emphasize spectral advantages and real-world complexity. To tackle these challenges, we propose Hyper-HRNet, a high-resolution HSOD network. Hyper-HRNet effectively extracts, integrates, and preserves effective spectral information while reducing dimensionality by capturing the self-similar spectral features. Additionally, it conveys fine details and precisely locates object contours by incorporating comprehensive global information and detailed object saliency representations. Experimental analysis demonstrates that Hyper-HRNet outperforms existing models, especially in challenging scenarios.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：传统 RGB 显著目标检测（SOD）在小目标、前景‑背景颜色相似等挑战场景中性能受限，而高光谱图像（HSI）能提供丰富的光谱信息，有望提升检测鲁棒性。然而，高光谱显著目标检测（HSOD）因缺乏大规模、高质量、多样化标注数据集而发展滞后。
- **核心贡献**：本文构建了目前最大、最具挑战性的 HSOD 基准数据集 **HSOD‑BIT‑V2**，包含 500 张高光谱图像、8 类自然场景背景和 5 种挑战属性（小目标、颜色相似、材质相似、复杂背景、高动态范围），重点突出光谱优势。同时提出 **Hyper‑HRNet** 高分辨率网络，通过高效利用光谱信息并精确描绘目标轮廓，在多个挑战场景中超越现有 RGB 和 HSI 方法。

## 2. 方法论
- **整体架构**：Hyper‑HRNet 由 Hyperspectral Attention Reconstruction (HAR) 和 Global Ternary Perception Decoder (GTPD) 两部分组成，骨干网络为 HRNet。
- **核心模块**：
  - **HAR（高光谱注意力重建）**：首先对原始 HSI 沿通道方向每 4 个通道插值为 1 个通道，实现降维；然后通过级联的 Hybrid Perceptual Spectral Attention Blocks (HPSAB) 进行重建。每个 HPSAB 包含：
    - **Multi‑head Spectral‑wise Self‑Attention (MSSA)**：将特征映射视为谱维 token，计算多头的谱维自注意力，并通过可学习参数 σ 适应不同波段的密度变化。
    - **Adaptive Spectral Attention Mechanism (ASAM)**：并行使用最大池化和平均池化提取高低频谱特征，并用可学习参数 α、β 加权融合，生成自适应谱注意力权重。
  - **GTPD（全局三元感知解码器）**：融合 HRNet 的多尺度高分辨率流，包含三个子模块：
    - **CMFI（跨层级多尺度特征交互）**：将特征按通道拆分，分别通过全局卷积和跨尺度交互，增强尺度适应性。
    - **GAFA（全局注意力特征聚合器）**：使用 Pixel Shuffle 将各层特征统一至 20×20 大小，拼接后经 Transformer 生成全局显著图，与全分辨率像素不洗牌得到的真值进行监督。
    - **TAW（三元感知权重）**：将每层显著预测转换为三值权重（前景、背景、不确定区域），引导后续解码关注轮廓区域，提升边缘定位精度。
- **损失函数**：`L = Ls + Lsod + Lg`，分别对应重建损失、显著检测损失（BCE + IoU）和全局引导损失（对全局显著图与下采样真值计算 BCE）。

## 3. 实验设计
- **数据集**：
  - **HSOD‑BIT‑V2**：自建最大数据集，500 张图像（406 训练 / 94 测试），空间分辨率 1240×1680，200 光谱波段，覆盖 8 种自然背景。
  - **HSOD‑BIT**：319 张图像，前身数据集。
  - **HS‑SOD**：60 张图像，早期小规模数据集。
- **对比方法**：
  - **RGB 方法**：Itti, BASNet, U2Net, SelfReformer。
  - **HSI 方法**：SAD, SED, SG, SED‑SAD, SED‑SG, SUDF, SMN, DMSSN。
- **评价指标**：MAE, PRE, REC, avgF1, AUC, CC。
- **实验设置**：所有对比方法在三个数据集上独立训练与测试，保持相同条件。
- **消融实验**：
  - 关键组件（HAR + GTPD）的有效性。
  - HAR 与其它降维方法（插值、PCA、卷积）对比。
  - HAR 内部结构（MSSA、ASAM 消融，以及替换为 ViT 自注意力、MSS 注意力）。
  - GTPD 内部模块（CMFI、GAFA、TAW 消融）。
- **属性评估**：在 HSOD‑BIT‑V2 的五种挑战属性（CB、CS、HDR、SO、MS）上分别报告 MAE 和 AUC。
- **效率分析**：提供参数量和 FLOPs，并引入轻量版 Lite‑HRNet 骨干的 Hyper‑HRNet‑Lite。

## 4. 资源与算力
- **文中未明确说明使用的 GPU 型号、数量或训练时长**。仅报告了各方法的参数量和 FLOPs（例如 Hyper‑HRNet 为 29.57M 参数、18.96G FLOPs；Lite 版为 7.24M / 7.85G）。传统方法（如 Itti）未统计计算量。
- **不足**：缺乏训练硬件和超参数细节，不利于复现和公平的效率对比。

## 5. 实验数量与充分性
- **实验数量**：包含三个数据集上的全量对比、五种属性子集评估、多个消融系列（至少 6 组消融表）、以及效率分析。总计约 10 余组实验。
- **充分性与公平性**：
  - 对比方法覆盖了经典和 SOTA 的 RGB 与 HSI 方法，训练测试条件一致。
  - 消融实验覆盖了主要模块和替代方案，验证了每个设计的必要性。
  - **客观性**：报告了标准的六项指标，未进行统计显著性检验（如 t 检验），但数值差距明显。
  - **不足**：缺少跨数据集泛化测试（如从 HSOD‑BIT‑V2 训练直接测试其他数据集），未讨论数据增强或预处理影响。

## 6. 主要结论与发现
- HSOD‑BIT‑V2 作为目前最大、最具挑战的 HSOD 基准，能有效评估模型在复杂场景下的性能。
- Hyper‑HRNet 在所有数据集上全面超越现有 RGB 和 HSI 方法，尤其在颜色相似、小目标、材质相似等属性上优势显著（例如在 MS 属性上 AUC 提升至 0.994，远超 SMN 的 0.857）。
- HAR 模块通过谱维自注意力与自适应注意力结合，有效降维并保留关键光谱信息；GTPD 模块通过全局注意力与三元轮廓感知显著提升边缘定位精度。
- 消融实验表明，每个模块均对最终性能有正向贡献，不可替代。

## 7. 优点
- **数据集建设**：HSOD‑BIT‑V2 规模大、背景多样（首次引入雪地、落叶）、挑战属性平衡且贴近真实复杂场景，为 HSOD 提供了高质量基准。
- **方法创新**：HAR 巧妙结合 CNN 和 Transformer 处理谱维冗余，避免了传统 PCA 的信息损失；GTPD 中的 TAW 三元权重机制新颖，针对轮廓模糊区域进行强化。
- **实验结果全面**：不仅在完整数据集上对比，还细粒度的按挑战属性评估，验证了光谱信息在困难场景中的优势。
- **效率可调**：提供 Lite 版本，在参数量和 FLOPs 上具有竞争力，便于实际部署。

## 8. 不足与局限
- **实验覆盖**：未报告在跨数据集（如卫星遥感高光谱图像）上的迁移能力，仅测试了自然场景；未进行误差分析或失败案例讨论。
- **偏差风险**：数据集包含 8 种背景，但可能难以覆盖工业、医疗等特殊领域；小目标比例高（38.4%），但大目标样本不充分，可能导致模型对大目标敏感。
- **训练细节缺失**：未说明 GPU 型号、批量大小、学习率调度、训练轮次、数据扩充策略等，影响复现性。
- **计算成本**：Hyper‑HRNet 参数量（29.57M）和 FLOPs（18.96G）虽低于部分 RGB 方法，但仍高于轻量 HSI 方法（如 DMSSN 1.76M），在资源受限设备上可能受限。
- **评价指标**：仅使用图像级指标，未采用 F-measure 曲线、PR 曲线等更全面的评估，也未进行人眼主观评估。

（完）

---
title: "InstructSAM: A Training-free Framework for Instruction-Oriented Remote Sensing Object Recognition"
title_zh: InstructSAM：面向指令的遥感目标识别无训练框架
authors: "Yijie Zheng, Weijie Wu, Qingyun Li, Xuehui Wang, Xu Zhou, Aiai Ren, Jun Shen, Long Zhao, Guoqing Li, Xue Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=7yRwAEWxto"
tags: ["query:hsi"]
score: 7.0
evidence: 遥感目标识别框架
tldr: 该论文提出InstructSAM，一种无需训练的指令导向遥感目标识别框架，覆盖目标计数、检测和分割任务。构建了首个遥感指令理解基准EarthInstruct。该方法可直接用于高光谱图像目标检测，因其处理的是遥感图像，但未针对高光谱多波段特性优化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1404, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1418, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 646, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 1187, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1072, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 793, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1402, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1431, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1423, \"height\": 1375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1247, \"height\": 891, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7yrwaewxto/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1162, \"height\": 848, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1243, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1325, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 620, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 653, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 1032, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1459, \"height\": 585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1451, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 482, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1356, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1385, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7yrwaewxto/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1293, \"height\": 258, \"label\": \"Table\"}]"
motivation: 现有遥感目标识别依赖显式类别名，无法处理复杂隐式查询。
method: 利用预训练模型和语言指令，无需训练即可完成检测任务。
result: 在遥感基准上表现良好，支持开放词汇和开放子类场景。
conclusion: 为遥感目标检测提供了灵活方案，可扩展至高光谱数据。
---

## Abstract
Language-guided object recognition in remote sensing imagery is crucial for large-scale mapping and automated data annotation. However, existing open-vocabulary and visual grounding methods rely on explicit category cues, limiting their ability to handle complex or implicit queries that require advanced reasoning.
To address this issue, we introduce a new suite of tasks, including Instruction-Oriented Object Counting, Detection, and Segmentation (InstructCDS), covering open-vocabulary, open-ended, and open-subclass scenarios. We further present EarthInstruct, the first InstructCDS benchmark for earth observation. It is constructed from two diverse remote sensing datasets with varying spatial resolutions and annotation rules across 20 categories, necessitating models to interpret dataset-specific instructions.
Given the scarcity of semantically rich labeled data in remote sensing, we propose InstructSAM, a training-free framework for instruction-driven object recognition. InstructSAM leverages large vision-language models to interpret user instructions and estimate object counts, employs SAM2 for mask proposal, and formulates mask-label assignment as a binary integer programming problem. By integrating semantic similarity with counting constraints, InstructSAM efficiently assigns categories to predicted masks without relying on confidence thresholds. Experiments demonstrate that InstructSAM matches or surpasses specialized baselines across multiple tasks while maintaining near-constant inference time regardless of object count, reducing output tokens by 89\% and overall runtime by over 32\% compared to direct generation approaches. We believe the contributions of the proposed tasks, benchmark, and effective approach will advance future research in developing versatile object recognition systems. The code is available at https://VoyagerXvoyagerx.github.io/InstructSAM.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

遥感图像中语言引导的目标识别对于大尺度制图和自动化数据标注至关重要。然而，现有的开放词汇（open-vocabulary）和视觉定位（visual grounding）方法严重依赖显式的类别提示（如固定的类别名），无法处理需要高级推理的复杂或隐式查询（例如“检测所有运动场”这样的开放子类指令）。此外，遥感领域标注数据稀缺且类别有限（通常仅几十类），导致模型泛化能力不足。针对这些问题，本文提出了一套新的任务套件——指令导向的目标计数、检测与分割（InstructCDS），涵盖开放词汇、开放端（open-ended）和开放子类（open-subclass）三种设置，并构建了第一个遥感指令理解基准 EarthInstruct。同时，为了克服标注数据稀缺和阈值敏感性等挑战，提出了无需训练（training-free）的框架 InstructSAM，利用预训练的大视觉语言模型（LVLM）、SAM2 和遥感专用 CLIP 模型，实现灵活、高效的指令驱动遥感目标识别。

## 2. 方法论：核心思想、关键技术细节

**核心思想**：将指令驱动目标识别分解为三个可解耦的步骤：（1）用 LVLM 理解用户指令并预测目标类别和计数；（2）用 SAM2 生成类别无关的掩码提案；（3）将掩码-标签分配建模为带计数约束的二元整数规划（BIP）问题，通过优化语义相似度和全局计数约束得到最终识别结果。整个过程无需任务特定训练，也不需要置信度阈值。

**关键技术细节**：
- **LVLM 计数器**：采用 GPT-4o 或 Qwen2.5-VL，使用结构化 JSON 提示（包含角色、任务、指令、输出格式和示例），通过指令字段融入数据集特定的标注规则（如“低分辨率下不计数车辆”），输出目标类别及其计数。
- **SAM2 掩码提案**：使用 SAM2-hiera-large 的自动掩码生成模式，配置点网格（points_per_side=24）和裁剪层（crop_n_layers=1）以提高小目标召回率。
- **CLIP 语义相似度**：采用遥感预训练的 GeoRSCLIP-ViT-L 计算掩码提案裁剪区域与类别文本的余弦相似度（文本模板：“a satellite image of a {category}”）。
- **计数约束的掩码-标签匹配**：构建二元整数规划问题，目标是最小化总不相似度（1 - sij）·xij，约束条件包括：每个掩码最多分配一个类别（约束2）、每个类别的分配数等于 LVLM 预测的计数（约束3，当提案数足够时）、若提案数不足则分配所有提案（约束4）。使用 PuLP 求解器高效求解。

**公式与算法**：见论文式(1)-(4)，本质上是一个线性整数规划，融合了视觉信息（掩码嵌入）、语义信息（类别嵌入）和定量信息（计数）。

## 3. 实验设计

- **数据集/场景**：使用两个主流遥感目标检测数据集构建 EarthInstruct 基准：NWPU-VHR-10（10类，0.08-2m 分辨率）和 DIOR（20类，0.3-30m 分辨率）。三种设置：开放词汇、开放端、开放子类。此外，还在 xBD（建筑物检测）和 Aerial Maritime Drone Large（无人机视角）上进行了零样本跨域评估。
- **Benchmark**：EarthInstruct 是首个 InstructCDS 基准，包含计数、检测、分割三个子任务。评估指标：计数任务使用 F1-score（代替传统 MAE，以区分过计数和欠计数）；检测/分割使用无置信度指标 mF1 和 mAPnc（mAP without confidence），以公平对比无置信度模型和传统检测器。
- **对比方法**：
  - 开放词汇：Grounding DINO、OWLv2、Qwen2.5-VL、GSNet、SegEarth-OV 等。
  - 开放端：Qwen2.5-VL、GPT-4o+OWL、SkySenseGPT、EarthDial、LAE-Label、GeoPixel。
  - 开放子类：Qwen2.5-VL、GPT-4o+OWL。
  - 零样本跨域：CASTDet、LAE-DINO。
- **消融实验**：提示设计、模型缩放（不同 LVLM、SAM2、CLIP 组合）、阈值敏感性分析、错误分析。

## 4. 资源与算力

论文中未明确报告完整训练所需的算力（因为该方法无需训练），但提供了推理时间分析。实验在一张 RTX 4090 GPU 上进行，对比了 InstructSAM 与直接生成方法（如 Qwen2.5-VL）的推理时间。InstructSAM 的推理时间主要消耗在 SAM2 掩码提议阶段，PuLP 求解仅需 0.07 秒，整体时间随目标数量几乎不变（R²≈0.01），而对比方法呈线性增长（R²>0.9）。未报告训练算力需求，因为框架是 training-free 的。

## 5. 实验数量与充分性

论文进行了大量实验，覆盖三个设置（开放词汇、开放端、开放子类）、两个主数据集、两个额外跨域数据集，以及多种消融和分析（提示格式、模型缩放、阈值敏感性、错误分布、推理时间）。实验设计较为全面：
- 开放词汇表 1 和表 10 对比了 6-7 种方法。
- 开放端表 2 对比了 6 种方法。
- 开放子类表 3 对比了 3 种方法。
- 消融实验（表 4-5、图 6）分析了提示设计和模型缩放的影响。
- 跨域实验（表 11）在 xBD 和 Aerial Maritime Drone 上评估。
- 统计显著性（附录 D.3）对提示格式进行了 5 次独立重复。
- 错误分析（图 7）对比了 OWLv2、Qwen2.5-VL 和 InstructSAM 的错误分布。

整体实验充分，对比方法多样，覆盖了通用和遥感专用模型，且使用了公平的无置信度指标。不过，部分基线（如 GSNet、SegEarth-OV）仅报告分割指标，而 InstructSAM 同时报告检测和分割，跨任务可比性略受限于指标差异。另外，跨域实验仅评估了单类（xBD 仅“building”）和少数类别（Aerial Maritime Drone 五类），覆盖范围有限。

## 6. 主要结论与发现

1. InstructSAM 在开放词汇、开放端和开放子类三个设置上均匹配或超越专用基线，尤其在计数和分割任务上表现突出（NWPU-VHR-10 计数 F1: 83.0 vs. 闭集 Faster-RCNN 的 77.0）。
2. 推理时间几乎不随目标数量增加，相比 Qwen2.5-VL 直接生成，输出 token 减少 89%，总时间减少 32% 以上。
3. 无需置信度阈值，通过计数约束的匹配避免了传统检测器的阈值敏感性，在零样本场景下更具鲁棒性。
4. 使用遥感专用 CLIP（GeoRSCLIP）比通用 CLIP 性能更好，且模型组件越大性能越佳，体现框架的可扩展性。
5. 结构化 JSON 提示能有效提升 LVLM 的计数准确性，尤其对包含数据集特定规则的指令。
6. 错误分析显示，InstructSAM 主要受限于 CLIP 的场景级训练导致的背景混淆，而分类误差较少。

## 7. 优点

- **训练自由**：无需任何任务特定训练或微调，直接利用预训练模型，大大降低了数据和计算成本。
- **阈值无关**：通过计数约束的全局优化规避了传统检测器的置信度阈值问题，适合零样本和开放世界识别。
- **高效推理**：推理时间与目标数量解耦，适合大规模遥感应用。
- **多功能性**：同时支持计数、检测、分割三种任务，且可处理开放词汇、开放端和开放子类等复杂指令。
- **可扩展性**：框架可集成更强大的 LVLM、SAM 和 CLIP 变体，性能随组件规模提升。
- **基准贡献**：构建了第一个遥感指令理解基准 EarthInstruct，推动该方向研究。

## 8. 不足与局限

- **依赖基础模型性能**：InstructSAM 的性能受限于 LVLM 的计数准确性、SAM2 的掩码质量以及 CLIP 的语义对齐能力。SAM2 可能遗漏复杂几何形状（如篮球场）；CLIP 场景级训练导致对象级背景混淆（误差分析中背景误判占较大比例）。
- **光学图像限制**：基础模型（GPT-4o、SAM）主要基于光学图像训练，对 SAR 等遥感模态效果差，限制了多模态应用。
- **实验覆盖有限**：跨域评估仅涉及两个额外数据集，且类别较少；开放子类仅测试两个父类（运动场和交通工具），泛化性验证不够充分。
- **推理成本**：尽管推理时间与目标数量无关，但 SAM2 的掩码提议仍需 GPU 计算（一张 RTX 4090），可能不适合实时或边缘部署。
- **未讨论小样本/少样本场景**：虽然 training-free，但在极低分辨率或罕见类别上性能可能大幅下降，文中未深入分析。
- **潜在偏差风险**：预训练模型中的偏见（如地理、文化偏见）可能影响识别结果，尤其在高分辨率遥感图像可能涉及隐私问题，文中仅简要提及。

（完）

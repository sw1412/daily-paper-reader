---
title: "Unraveling Metameric Dilemma for Spectral Reconstruction: A High-Fidelity Approach via Semi-Supervised Learning"
title_zh: 解同色异谱难题：基于半监督学习的高保真光谱重建
authors: "Xingxing Yang, Jie Chen, Zaifeng Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=59TL8MpBzX"
tags: ["query:hsi"]
score: 7.0
evidence: 半监督高光谱重建，可提升分类与检测性能
tldr: 针对RGB到高光谱重建中的同色异谱问题，本文提出Diff-Spectra方法，通过自适应照度色度解耦模块和学习型光谱响应函数，结合半监督学习实现高保真HSI重建。在多个数据集上的实验表明，该方法能有效提升重建精度，为下游高光谱图像分类与目标检测任务提供更优质的光谱输入。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1386, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 718, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1001, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1350, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-59tl8mpbzx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1360, \"height\": 454, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-59tl8mpbzx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-59tl8mpbzx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 685, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-59tl8mpbzx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 742, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-59tl8mpbzx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-59tl8mpbzx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 580, \"label\": \"Table\"}]"
motivation: 从RGB重建高光谱存在同色异谱问题，现有方法无法区分不同光谱分布。
method: 提出Diff-Spectra，包含自适应照色解耦模块（AICD）和半监督学习框架，结合物理感知的谱估计。
result: 在标准数据集上实现了高保真HSI重建，显著优于现有方法。
conclusion: 该方法为高光谱图像分类与检测提供了高质量的光谱先验。
---

## Abstract
Spectral reconstruction from RGB images often suffers from a metameric dilemma, where distinct spectral distributions map to nearly identical RGB values, making them indistinguishable to current models and leading to unreliable reconstructions.
In this paper, we present Diff-Spectra that integrates supervised physics-aware spectral estimation and unsupervised high-fidelity spectral regularization for HSI reconstruction.
We first introduce an Adaptive illumiChroma Decoupling (AICD) module to decouple illumination and chrominance information, which learns intrinsic and distinctive feature distributions, thereby mitigating the metameric issue.
Then, we incorporate the AICD into a learnable spectral response function (SRF) guided hyperspectral initial estimation mechanism to mimic the physical image formation and thus inject physics-aware reasoning into neural networks, turning an ill-posed problem into a constrained, interpretable task. 
We also introduce a metameric spectra augmentation method to synthesize comprehensive hyperspectral data to pre-train a Spectral Diffusion Module (SDM), which internalizes the statistical properties of real-world HSI data, enforcing unsupervised high-fidelity regularization on the spectral transitions via inner-loop optimization during inference.
Extensive experimental evaluations demonstrate that our Diff-Spectra achieves SOTA performance on both Spectral reconstruction and downstream HSI classification.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：RGB 图像到高光谱图像（HSI）的重建面临同色异谱问题（metameric dilemma），即多种不同的光谱分布可能映射到几乎相同的 RGB 值，现有模型无法区分它们，导致重建结果不可靠。
- **问题根源**：现有方法存在三大局限：① 训练数据中缺少丰富的同色异谱样本（数据匮乏）；② 未显式建模真实光谱分布的统计特性（光谱流形盲目）；③ 将光谱辐亮度视为整体，未分离光照与色度信息（架构短视）。
- **整体目标**：通过引入辅助信息缓解同色异谱问题，实现高保真光谱重建，并提升下游 HSI 分类的性能。

## 2. 论文提出的方法论

- **核心思想**：采用半监督学习范式，融合有监督的物理感知光谱估计与无监督的高保真光谱正则化。
- **关键模块**：
  - **自适应照度色度解耦模块（AICD）**：基于 Retinex 理论解耦光照（L）与反射率（R），再通过可学习参数和正交 UV 分解（公式 5）得到 U、V 特征，增强同色异谱样本的判别性。
  - **SRF 引导的 HSI 初始估计机制（SRF-guided HIE）**：利用光谱响应函数（SRF）的逆变换（公式 8-9），将 AICD 特征与 RGB 融合，并通过 UNet 网络获得粗估计 HSI，注入物理约束。
  - **同色异谱光谱增强（Metameric Spectra Augmentation）**：基于正交子空间分解（公式 11）生成与原光谱同色异谱的新样本，扩大训练数据多样性。
  - **光谱扩散模块（SDM）**：采用 1D MLP-UNet 架构的扩散模型，在增强数据集上预训练，学习真实光谱分布；在微调阶段通过内循环优化（每个时间步 K 次梯度更新）弥合粗估计 HSI 与真实分布的差异。
- **训练流程（三阶段）**：
  1. 联合预训练 AICD 和 SRF-guided HIE，优化式 (10)；
  2. 冻结前两者，预训练 SDM，优化式 (13)；
  3. 冻结 SDM，联合微调 AICD 和 SRF-guided HIE，优化式 (14)（含光谱先验正则项 λ=0.1）。
- **推理**：加载预训练模型，将粗估计 HSI 作为可学习参数，通过 SDM 的逆扩散过程进行测试时适应（内循环 K=5，扩散步数 S=50）。

## 3. 实验设计

- **数据集**：
  - 重建任务：ARAD-1K（900 训练/50 验证，482×512，31 波段）和 ICVL（147 训练/36 测试，1300×1392，31 波段）。
  - 分类任务：Indian Pines（145×145，200 波段）和 Pavia University（610×340，103 波段）。
- **基准方法**：AWAN、HINet、HDNet、MST-L、MST++、SST、PADUT、CESST、SPECAT 等共 9 种 SOTA。
- **评估指标**：
  - 重建：ERGAS、SAM（光谱质量），SSIM、PSNR（空间质量）。
  - 分类：总体精度（OA）、平均精度（AA）、Kappa 系数（κ）。
- **对比设置**：定量表格（表 1、表 2a、表 2b）、可视化（图 4-8）、同色异谱专门评估（表 2a）、分类下游任务（表 2b 和附录表 4）。

## 4. 资源与算力

- **文中说明**：未明确提及使用的 GPU 型号、数量及总训练时长，仅提供了训练超参数（学习率 4e-4/1e-2/1e-4，批大小 20/1024/20，各阶段 Epoch 数 300/300/100）。
- **结论**：资源与算力信息不完整，无法直接复现硬件需求。

## 5. 实验数量与充分性

- **实验数量**：共进行了约 8 组关键实验（2 个重建数据集 × 9 方法对比 + 1 组同色异谱评估 + 2 个分类数据集 × 9 方法对比 + 消融实验 + 内循环分析），加上附录中的额外分类结果和更多可视化。
- **充分性与公平性**：
  - 覆盖了主流指标和多个数据集，消融实验（表 3a、图 6）逐一验证了 AICD、SRF、SDM 和内循环的贡献。
  - 内循环步数 K 的分析（表 3b）说明了测试时适应的必要性。
  - 对比方法均为公开 SOTA，重现了其预训练模型在标准/同色异谱数据上的表现，结论客观。
- **不足之处**：部分实验（如同色异谱评估）仅在一个数据集上进行（原始 ARAD-1K 生成的 metamer 数据），泛化性可进一步加强。

## 6. 论文的主要结论与发现

- Diff-Spectra 在 ARAD-1K 和 ICVL 上获得了最高的 PSNR（35.47/34.71）和最低的 ERGAS（4.63/2.84），综合指标领先 SOTA。
- 在同色异谱数据上，现有方法性能剧烈下降（PSNR 下降至 27 左右），而 Diff-Spectra 仍保持较高水平（PSNR 31.61，SAM 24.11），显著缓解了同色异谱问题。
- 在下游 HSI 分类任务中，使用 Diff-Spectra 重建的 HSI 作为输入，在 Indian Pines 和 Pavia University 上均取得最高 OA、AA 和 Kappa，验证了重建光谱的真实性与实用性。
- 消融实验表明，AICD 主要提升空间细节，SRF 约束增强物理合理性，SDM 提供光谱先验，内循环优化克服分布差异。

## 7. 优点

- **方法创新性强**：将物理模型（SRF 逆变换）与数据驱动扩散先验有机结合，形成半监督范式，逻辑清晰。
- **针对同色异谱问题的设计**：AICD 模块通过照度-色度解耦和正交变换增强判别性，同色异谱数据增强扩大了训练覆盖。
- **轻量化与可解释性**：1D 光谱扩散模型避免高维计算，SRF 引导使网络具有物理可解释性。
- **实验全面且有深度**：包括标准/同色异谱对比、消融、内循环分析、下游分类验证，充分支撑了论点。
- **测试时适应机制**：内循环优化有效弥合了预训练与真实场景的分布差异，提升了泛化能力。

## 8. 不足与局限

- **实验覆盖有限**：仅在四个特定数据集上进行测试，未涉及更多样化的场景（如遥感大尺度、医学 HSI），泛化能力有待进一步验证。
- **资源公开不足**：未说明 GPU 型号、数量及训练时间，影响可复现性；三阶段训练加测试时内循环可能带来较高的计算开销。
- **理论分析不足**：对同色异谱问题的数学刻画和 AICD 的收敛性缺乏严格证明，主要依赖实验验证。
- **应用限制**：方法依赖于已知或可学习的 SRF，若 SRF 未知或在不同传感器间差异较大，可能需要额外适配；内循环步数 K 需要人工设定，对计算资源敏感。
- **偏差风险**：消融实验仅在一个数据集（ICVL）上展示，可能存在结果偏差；同色异谱增强仅针对光谱维度，未考虑空间结构差异。

（完）

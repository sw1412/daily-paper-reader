---
title: "HyperFree: A Channel-adaptive and Tuning-free Foundation Model for Hyperspectral Remote Sensing Imagery"
title_zh: "HyperFree: 面向高光谱遥感图像的自适应通道与免调参基础模型"
authors: "Li, Jingtao, Liu, Yingyi, Wang, Xinyu, Peng, Yunning, Sun, Chen, Wang, Shaoyu, Sun, Zhendong, Ke, Tian, Jiang, Xiao, Lu, Tangwei, Zhao, Anran, Zhong, Yanfei"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Li_HyperFree_A_Channel-adaptive_and_Tuning-free_Foundation_Model_for_Hyperspectral_Remote_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 10.0
evidence: 面向高光谱遥感的基础模型，可用于分类、检测等多种任务
tldr: 该文提出HyperFree，一种通道自适应且免调参的高光谱遥感基础模型。针对现有基础模型无法处理高光谱图像通道数变化的问题，设计全谱权重字典动态构建嵌入层，结合视觉提示工程实现免调参推理。在多个高光谱分类和检测任务上达到SOTA，且推理效率高，为高光谱遥感基础模型提供了新路线。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 833, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1268, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1645, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 771, \"height\": 943, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 780, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 872, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 779, \"height\": 604, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1794, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 874, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1823, \"height\": 1072, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1811, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-li-hyperfree-a-channel-adaptive-and-tuning-free-foundation-model-for-hyperspectral-remote-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1810, \"height\": 234, \"label\": \"Table\"}]"
motivation: 现有基础模型无法处理高光谱图像通道数变化，需逐图像调参。
method: 设计全谱权重字典动态构建嵌入层，结合视觉提示工程实现免调参推理。
result: 在多个高光谱分类和检测任务上达到SOTA，且推理效率高。
conclusion: 开创了高光谱遥感基础模型免调参的新路线。
---

## Abstract
Advanced interpretation of hyperspectral remote sensing images benefits many precise Earth observation tasks. Recently, visual foundation models have promoted the remote sensing interpretation but concentrating on RGB and multispectral images. Due to the varied hyperspectral channels, existing foundation models would face image-by-image tuning situation, imposing great pressure on hardware and time resources. In this paper, we propose a tuning-free hyperspectral foundation model called HyperFree, by adapting the existing visual prompt engineering. To process varied channel numbers, we design a learned weight dictionary covering full-spectrum from 0.4 2.5um, supporting to build the embedding layer dynamically. To make the prompt design more tractable, HyperFree can generate multiple semantic-aware masks for one prompt by treating feature distance as semantic-similarity. After pre-training HyperFree on constructed large-scale high-resolution hyperspectral images, HyperFree (1 prompt) has shown comparable results with specialized models (5 shots) on 5 tasks and 11 datasets. Code and dataset would be accessible at https://rsidea.whu.edu.cn/hyperfree.htm#.

---

## 论文详细总结（自动生成）

# HyperFree 论文深度分析与总结

## 1. 核心问题与整体含义（研究动机和背景）

高光谱遥感图像（HSI）具有高光谱分辨率、宽波长范围（400–2500 nm）和大量谱段（几十到几百个通道），能够支持精确的地球观测任务（环境监测、农业、国防等）。然而，**不同高光谱传感器之间存在通道数、光谱分辨率和波长范围的巨大差异**，这导致现有视觉基础模型（如 SAM、SatMAE、SpectralGPT）无法直接处理高光谱图像：

- **预训练+微调（P-T）范式**：需针对每张高光谱图像重新构建嵌入层并微调，计算资源和时间开销极大。
- **提示工程（P-E）范式**（如 SAM）：虽可免微调，但固定通道数的设计无法适配变化的高光谱通道，且通常每个提示只生成单一掩码，需大量先验知识。

因此，论文提出 **HyperFree**——首个 **通道自适应、免调参的高光谱遥感基础模型**，旨在：
- 直接处理任意通道数、任意波长范围的高光谱图像，无需微调。
- 通过单个点提示即可生成**多个语义一致的掩码**，实现高效、用户友好的推理。

## 2. 方法论：核心思想与关键技术细节

### 2.1 总体架构
HyperFree 基于 SAM 的元架构，包含三个核心组件：
- **通道自适应嵌入层（Channel-adaptive Embedding）**
- **全频谱可提示训练（Full-spectrum Promptable Training）**
- **提示-掩码-特征交互推理（PMF Interactive Inferring）**

### 2.2 通道自适应嵌入层
- **动机**：不同传感器通道数可变（如 46–274 通道），需要一种统一编码方式。
- **实现**：
  - 构建一个 **可学习的权重字典** β，覆盖 400–2500 nm 全部频谱，以 10 nm 为间隔，共 221 个索引通道。
  - 每个索引通道存储一个卷积核 \( W \in \mathbb{R}^{p \times p \times j} \)（p 为 patch 大小，j 为输出 token 维度）。
  - 给定输入图像 X 及其波长列表 \( b = [b_1, ..., b_n] \)，从字典 β 中根据波长动态查找对应权重，动态构建卷积层：
    \[
    W = g(b, \beta), \quad T = \text{Conv}_W(X)
    \]
  - 进一步分为 **关键通道分支**（β_k）和 **切片块分支**（β_c），两者输出求和得到最终 tokens：
    \[
    T = f(X_k | b_k, \beta_k) + f(X_c | b_c, \beta_c)
    \]

### 2.3 全频谱可提示训练
- 利用自建的 **Hyper-Seg 大规模分割数据集**（约 4.2 万张高光谱图像，150k 张含多光谱扩展）进行有监督训练。
- **训练方式**：每轮随机选择整个频谱的子集通道，并随机生成点提示，强制模型学习波长感知的嵌入。
- 损失函数：Focal loss + Dice loss，权重 20:1（同 SAM）。

### 2.4 提示-掩码-特征（PMF）交互推理
- **核心思想**：将提示和掩码都映射到特征空间，用余弦距离度量语义相似性，从而通过单个点提示筛选出所有语义一致的掩码。
- **两种基础模式**：
  - 模式1：给定点 (x,y)，利用特征立方 D 和生成的最小掩码 M，提取该点的特征向量 \( d_{(x,y)} \)。
  - 模式2：对于特征向量 \( d_{(x,y)} \)，计算所有掩码的平均特征，选择余弦相似度超过阈值 τ 的掩码作为最终输出。
- **任务适配**：
  - 分类（HC）：每类一个点提示，用模式1+模式2，最小距离决定类别。
  - 单类分类（HOCC）：仅目标类别点提示，τ 为类先验比率。
  - 目标检测（HTD）：输入目标光谱，选择最近像素作为点，τ 为距离阈值。
  - 异常检测（HAD）：无提示，仅利用模式2，过滤大尺寸掩码。
  - 变化检测（HCD）：双时相图像，模式1提取第一时相特征，模式2比较第二时相特征，超过 τ 判定为变化。

## 3. 实验设计

### 3.1 数据集与 Benchmark
- **训练数据**：Hyper-Seg 数据引擎生成（41,946 张 AVIRIS 机载高光谱图像 + fMoW、SpaceNet 多光谱图像），共约 150k 张图像，1550 万个掩码。
- **评估数据**：11 个高光谱数据集，覆盖 5 类任务：
  - **HC**：LongKou（270通道）、HanChuan（274通道）
  - **HOCC**：HongHu（270通道）、XiongAn（256通道）
  - **HTD**：Airport（205通道）、Cri（46通道）
  - **HAD**：Beach1（188通道）、Beach2（193通道）
  - **HCD**：River（154通道）、Hermiston（198通道）
- **对比方法**：每个任务 6 个专门 SOTA 模型（如 SVM、HybridSN、FCN、MambaHSI、OCSVM、ACE、RXD、FC-EF、BIT 等）。

### 3.2 实验设置
- 所有对比方法使用 **每类 5 个样本（5-shot）** 训练（HTD 和 HAD 使用 1-shot 或零样本无条件）。
- HyperFree **完全冻结参数**，使用：
  - HC、HOCC、HTD：每类 **1 个点提示**
  - HAD、HCD：零样本（无提示）
- 评估指标：各任务标准指标（OA、AA、KA、F1、AUC、IoU 等）。

## 4. 资源与算力

- **GPU**：8 块 NVIDIA A100（80GB）。
- **训练时长**：约 **10 小时**（使用 Hyper-Seg 数据集，ViT-base 主干）。
- **优化器**：AdamW，初始学习率 8e-5，batch size 16。
- **每次随机采样**：每张图随机选 16 个掩码，每个掩码 1–2 个点。

## 5. 实验数量与充分性

- **主实验**：11 个数据集 × 5 任务，全部免调参对比，每个任务 6 个强基线。
- **扩展实验**：额外 14 个数据集 × 8 任务（增加去噪、目标跟踪、解混）进行微调性能测试。
- **消融实验**：
  - 权重字典波长顺序打乱 vs 正确波长 → 验证波长感知性。
  - 关键通道分支与切片块分支单独 vs 联合 → 验证双分支有效性。
  - 与 SAM + 相同 PMF 策略对比 → 验证预训练对高光谱的重要性。
  - t-SNE 可视化与 HyperSigma 对比特征分布。
- **敏感性分析**（补充材料）：提示数量、提示位置、超参数 τ 的影响。

**结论**：实验充分、客观、公平。对比方法均按标准协议训练（5-shot），HyperFree 为零样本或 1 提示，且结果普遍优于或持平于 SOTA。

## 6. 主要结论与发现

1. **免调参高光谱基础模型首次验证可行**：HyperFree 无需微调即可在 5 类任务上取得与 5-shot 训练模型相当甚至更好的结果。
2. **全频谱权重字典有效**：正确波长顺序相比随机顺序带来 5–40 个点的提升，说明模型学会了波长特异性表示。
3. **双分支嵌入设计有益**：关键通道与切片块分支联合优于任一分支单独使用。
4. **PMF 交互策略通用性好**：通过特征空间语义度量，单一提示可生成多掩码，适配多种任务。
5. **与现有高光谱基础模型 HyperSigma 对比**：HyperFree 特征更具类间分离性，支持免调参推理。

## 7. 优点（亮点）

- **创新性**：首个面向高光谱遥感图像的免调参基础模型，填补了该领域空白。
- **实用性强**：用户只需一个点提示即可完成分类、检测、变化检测等多种任务，极大降低部署成本。
- **数据构建**：提出 Hyper-Seg 数据引擎，自动生成大规模高分辨率高光谱分割数据集（15.5M 掩码），为后续研究提供资源。
- **通用性**：模型可直接处理任意通道数（42–274）的高光谱图像，跨传感器迁移能力强。
- **高效性**：训练仅需 10 小时（8 A100），推理速度快。
- **实验全面**：涵盖 5+8 类任务、25 数据集，对比 30+ 方法，结果可信。

## 8. 不足与局限

- **依赖 SAM 架构**：基于 SAM 的 backbone 和 promptable 设计，权重复用可能限制对极窄或异源光谱的适应能力（如超光谱成像）。
- **对提示敏感**：虽然 1 点提示即可，但提示位置和数量仍影响性能，实际使用需一定经验。
- **某些任务表现欠佳**：在 River 数据集（HCD）上 IoU 排名第 6，低于部分专用模型；在 HTD 的 Cri 数据集上 AUC 排名第 5，说明对复杂场景的零样本泛化仍有提升空间。
- **未覆盖完全无监督场景**：异常检测虽零样本，但需手动设定面积阈值（τ），引入人为偏差。
- **训练数据局限**：Hyper-Seg 主要基于 AVIRIS 传感器（0.6–5 m 分辨率），对于其他机载/星载传感器（如 PRISMA、EnMAP）的泛化性未验证。
- **仅测试 ViT-base**：更轻量或更重量的 backbone 未做消融，最优规模未知。

（完）

---
title: Deep Rank-One Tensor Functional Factorization for Multi-Dimensional Data Recovery
title_zh: 深度秩一张量函数分解用于多维数据恢复
authors: "Yanyi Li, Xi Zhang, Yisi Luo, Deyu Meng"
date: 2025-04-11
pdf: "https://ojs.aaai.org/index.php/AAAI/article/download/34040/36195"
tags: ["query:hsi"]
score: 6.0
evidence: 提出张量分解方法可用于高光谱数据特征提取
tldr: 针对多维数据表示中的冗余参数问题，提出深度秩一张量函数分解方法，通过紧凑的秩一分解和功能网络集成，有效利用数据先验。该方法在彩色图像、视频和高光谱图像的数据恢复任务上验证了其高效性和低参数优势，为高光谱图像的谱-空特征提取提供了新思路。
source: AAAI-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-34040/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 802, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-34040/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-34040/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1524, \"height\": 848, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-34040/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1711, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-34040/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 322, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-34040/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 876, \"height\": 1100, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-34040/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-34040/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 855, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-34040/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 813, \"height\": 333, \"label\": \"Table\"}]"
motivation: 现有方法未充分利用多维数据的内在结构，导致参数冗余。
method: 提出深度秩一张量函数分解，包含紧凑秩一因子分解和功能网络集成。
result: 在多种多维数据恢复任务中实现了高效表示，参数更少。
conclusion: 该方法为高光谱图像等数据的紧凑表示和特征提取提供了新框架。
---

## Abstract
Many real-world data are inherently multi-dimensional, e.g., color images, videos, and hyperspectral images. How to effectively and compactly represent these multi-dimensional data within a unified framework is an important pursuit. Previous methods focus on tensor factorizations, convolutional networks, or diffusion models for multi-dimensional data representation, which may not fully utilize inherent data structures and may lead to redundant parameters. In this work, we propose a Deep Rank-One Tensor Functional Factorization (DRO-TFF), which internally utilizes more comprehensive data priors facilitated by much fewer parameters. Concretely, our DRO-TFF consists of three organically integrated blocks: compact rank-one factorizations in the spatial domain, a deep transform to capture underlying low-dimensional structures, and smooth factors parameterized by implicit neural representations. Through a series of theoretical analysis, we show the rich data priors encoded in the DRO-TFF structure, e.g., Lipschitz smoothness and low-rankness. Extensive experiments on multi-dimensional data recovery problems, such as image and video inpainting, image denoising, and hyperspectral mixed noise removal, showcase the effectiveness of the proposed method.

---

## 论文详细总结（自动生成）

# 论文总结：Deep Rank-One Tensor Functional Factorization for Multi-Dimensional Data Recovery

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现实世界中的多维数据（如彩色图像、视频、高光谱图像）需要高效且紧凑的表示方法。现有方法（张量分解、卷积网络、扩散模型）要么未能充分利用数据内在结构导致参数冗余，要么表示能力受限于浅层或线性结构。
- **研究动机**：寻找一种能够综合多种数据先验（低秩性、光滑性）、参数更少、表示能力更强的统一框架，用于多维数据恢复任务（如图像/视频修补、去噪、高光谱混合噪声去除）。
- **整体意义**：提出一种深度秩一张量函数分解（DRO-TFF），将紧凑的秩一分解、深度变换和隐式神经表示有机集成，在参数效率、表示能力、理论保证和实验性能上均优于现有方法。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
DRO‑TFF 将三维张量 **X** ∈ ℝ^{n₁×n₂×n₃} 表示为三个模块的嵌套组合：
1. **空间域上的紧凑秩一因子分解**：利用多个秩一矩阵（通过前额面片乘积和模式‑3乘积加权求和）捕获低秩空间结构。
2. **模式‑3深度变换**：将线性变换矩阵扩展为多层非线性变换（含激活函数 LeakyReLU），增强表达能力。
3. **因子隐式神经表示（INR）**：用三个坐标‑基 MLP（正弦激活）分别参数化秩一因子 **A**、**B** 和最后一层变换矩阵 **Hₖ**，编码空间‑光谱光滑性。

### 2.2 关键技术细节

- **基本因子分解形式**（无深度变换时）：  
  **X** = ( **A** △ **B** ) ×₃ **H**  
  其中 **A**∈ℝ^{n₁×1×r}，**B**∈ℝ^{1×n₂×r} 的每个前额面片是秩一的，△ 表示面片乘积，×₃ 表示模式‑3张量‑矩阵乘积，**H**∈ℝ^{n₃×r} 为变换矩阵。

- **深度变换扩展**（加入 k 层）：  
  **X** = ψ(…ψ(( **A** △ **B** ) ×₃ **H₁**) ×₃ … ×₃ **Hₖ₋₁**) ×₃ **Hₖ**  
  其中 ψ(·) = LeakyReLU，前 k−1 层权重 **Hᵢ**∈ℝ^{r×r} 为可学习参数，最后一层 **Hₖ**∈ℝ^{n₃×r} 由 INR 参数化。

- **因子 INR**：  
  三个独立 MLP（深度=3、正弦激活 sin(ω₀·)）分别映射坐标向量 **v₁**=[1,…,n₁] 等至输出矩阵，经 unsqueeze 后得到因子张量。

- **理论性质**：
  - **低秩性**（定理1）：每个前额面片 X⁽ⁱ⁾ 的秩 ≤ r，源于秩一分解的加和性质。
  - **光滑性**（定理2）：在 INR Lipschitz 连续假设下，X 在空间和光谱方向满足局部光滑不等式（Lipschitz 常数与网络深度、权重范数等相关）。

- **应用模型**：
  - 图像/视频修补：min ∥P_Ω(O−X)∥²_F + γ₁∥X∥_TV
  - 图像去噪：min ∥O−X∥²_F + γ₁∥X∥_TV + γ₂∥X∥_SSTV
  - 高光谱混合噪声去除：min ∥P_Ω(O−X−S)∥²_F + γ∥S∥₁ + γ₁∥X∥_TV + γ₂∥X∥_SSTV  
  采用 ADMM 算法交替求解，其中 **X** 子问题用 Adam 优化 DRO‑TFF 参数。

## 3. 实验设计

### 3.1 数据集与场景
- **图像/视频修补**：彩色图像（House, Tree, Jelly Beans, 256×256×3）、自然高光谱（Feathers, Flowers, Thread Spools, 512×512×31）、视频（News, Carphone, Hall Monitor, 144×176×100）；采样率 SR=0.1, 0.2, 0.3 随机缺失。
- **图像去噪**：高光谱图像（Face, Fake and Real Peppers, Egyptian Statue, 512×512×31）；高斯噪声标准差 SD=0.1, 0.2, 0.3。
- **高光谱混合噪声去除**：自然高光谱（Cloth, Toy, Food, 512×512×31）和遥感高光谱（WDC Mall, 256×256×191；Pavia University, 256×256×93）；三种噪声情况（Case 1: 高斯+死线；Case 2: 高斯+稀疏噪声；Case 3: 高斯+稀疏噪声+死线）。

### 3.2 Benchmark 与对比方法
- **图像/视频修补**：FTNN, FCTN, HLRTF, DDS2M, LRTFR
- **图像去噪**：S2DIP, DS2DP, HLRTF, DDS2M, LRTFR, HIR-Diff
- **混合噪声去除**：同上六种方法
- 评价指标：PSNR 和 SSIM。

### 3.3 超参数设置
- 秩参数 r = int(β·min(n₁,n₂))，β 按任务分别设为 0.7/0.3/0.3。
- 深度变换层数 k=3，INR 深度=3，激活 sin(ω₀·)，ω₀ 彩色图=1 否则=2。
- 损失系数 γ₁=4×10⁻⁵, γ₂=4×10⁻⁴；混合噪声模型中 γ=0.01, μ=0.04。

## 4. 资源与算力

文中**未明确说明**所使用的 GPU 型号、数量、训练时长等硬件信息。仅报告了各方法的**运行时间**（秒），如 DRO‑TFF 在图像修补任务约 22~126 秒（依数据大小），在去噪任务约 74 秒。参数数量也给出（通常 0.1M~0.6M）。但缺乏关于训练平台、GPU 型号、分布式设置等的描述。

## 5. 实验数量与充分性

- **实验数量**：三大任务共约 9 种数据集 × 多种噪声/缺失情况 = 超过 20 组独立实验（每组取平均值）。此外，还包含消融实验（3 种变体 × 3 个任务 × 3 个数据集 × 3 种缺失/噪声场景？实际报告了平均结果）。视觉对比图展示了 3 个代表性示例。
- **充分性**：
  - **公平性**：对比方法涵盖了张量分解、卷积网络、扩散模型等主流范式，超参数固定或来源可信。
  - **客观性**：所有结果取平均值，使用公认指标 PSNR/SSIM。
  - **消融充分**：设计了三个变体（去除秩一因子、去除深度变换、去除 INR），验证各组件必要性。
  - **不足**：未进行统计显著性检验（如 t 检验），未报告多次运行的标准差；未在更大批量的数据集（如高光谱基准数据集 HSI2018）上验证泛化性。

## 6. 论文的主要结论与发现

1. DRO‑TFF 在所有三项任务上均取得优于或持平 SOTA 的性能，且参数数量最少（通常 0.1M~0.6M，最接近的对比方法 LRTFR 需 0.5M~1.7M，扩散模型需 20M+）。
2. 理论分析证明该结构天然编码低秩性和 Lipschitz 光滑性，有助于稳定恢复。
3. 消融实验表明：秩一因子、深度变换、INR 三个组件缺一不可，尤其深度变换对捕获细节、INR 对抑制伪影起关键作用。
4. 在实验覆盖的任务中，DRO‑TFF 对高光谱等谱维较多的数据优势更明显（如混合噪声去除中平均 PSNR 高出次优方法 1~3 dB）。

## 7. 优点

- **参数效率极高**：秩一分解使参数数与空间分辨率亚线性相关，INR 进一步压缩可学习参数。
- **综合先验利用**：同时编码低秩性（空间）和光滑性（空间+光谱），理论扎实。
- **方法通用性**：同一框架解决修补、去噪、混合噪声去除等多种逆问题，无需外部训练数据。
- **可扩展性**：通过调整秩 r 或深度 k 可轻易平衡表示能力与模型大小。
- **实验验证充分**：覆盖彩色、高光谱、视频；对比多种经典与最新方法。

## 8. 不足与局限

- **计算资源未披露**：缺少 GPU 型号、训练时长等，影响可复现性评估。
- **实验波动性未知**：未报告运行多次的标准差或置信区间，难以判断结果稳健性。
- **任务覆盖有限**：未测试超分辨率、压缩感知等常见应用；未在更大的数据集（如高光谱卫星图像“Chikusei”）上验证。
- **优化复杂度**：ADMM 内嵌 Adam 优化，整体迭代可能较慢（尽管总时间尚可），且调参（γ₁, γ₂, μ, β）依赖经验。
- **理论分析较初步**：光滑性导出的是 Lipschitz 上界，但未给出具体紧界；低秩性仅对基础形式证明，深度变换后秩不一定受限。
- **消融中 rank-one v.s. rank‑p**：仅比较了 p=5 一种情况，未讨论更优的 p 选择，对 rank‑5 的劣势解释不够充分（可能是过拟合或参数冗余）。

（完）

---
title: Self-Learning Hyperspectral and Multispectral Image Fusion via Adaptive Residual Guided Subspace Diffusion Model
title_zh: 基于自适应残差引导子空间扩散模型的自学习高光谱与多光谱图像融合
authors: "Zhu, Jian, Wang, He, Xu, Yang, Wu, Zebin, Wei, Zhihui"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Zhu_Self-Learning_Hyperspectral_and_Multispectral_Image_Fusion_via_Adaptive_Residual_Guided_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 7.0
evidence: 高光谱融合方法涉及空间-光谱信息处理，与光谱-空间特征提取相关
tldr: 该文针对高光谱与多光谱图像融合问题，提出自适应残差引导子空间扩散模型，仅利用观测图像自学习融合，无需额外训练数据。方法通过轻量级光谱和空间网络提取特征，在多个数据集上达到SOTA效果，显著提升了空间-光谱分辨率，为无监督高光谱融合提供了新范式。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1755, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1811, \"height\": 1244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1813, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 803, \"height\": 313, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 844, \"height\": 882, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 820, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 822, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 821, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 655, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 866, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-zhu-self-learning-hyperspectral-and-multispectral-image-fusion-via-adaptive-residual-guided-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 784, \"height\": 204, \"label\": \"Table\"}]"
motivation: 现有HSI-MSI融合依赖大量训练数据，实际难以获取。
method: 提出自适应残差引导子空间扩散模型，仅用观测图像自学习融合。
result: 在多个数据集上达到SOTA效果。
conclusion: 为无监督高光谱融合提供了新范式。
---

## Abstract
Hyperspectral and multispectral image (HSI-MSI) fusion involves combining a low-resolution hyperspectral image (LR-HSI) with a high-resolution multispectral image (HR-MSI) to generate a high-resolution hyperspectral image (HR-HSI). Most deep learning-based methods for HSI-MSI fusion rely on large amounts of hyperspectral data for supervised training, which is often scarce in practical applications. In this paper, we propose a self-learning Adaptive Residual Guided Subspace Diffusion Model (ARGS-Diff), which only utilizes the observed images without any extra training data. Specifically, as the LR-HSI contains spectral information and the HR-MSI contains spatial information, we design two lightweight spectral and spatial diffusion models to separately learn the spectral and spatial distributions from them. Then, we use these two models to reconstruct HR-HSI from two low-dimensional components, i.e, the spectral basis and the reduced coefficient, during the reverse diffusion process. Furthermore, we introduce an Adaptive Residual Guided Module (ARGM), which refines the two components through a residual guided function at each sampling step, thereby stabilizing the sampling process. Extensive experimental results demonstrate that ARGS-Diff outperforms existing state-of-the-art methods in terms of both performance and computational efficiency in the field of HSI-MSI fusion.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

高光谱图像（HSI）包含丰富的连续光谱信息，但受硬件限制，空间分辨率通常较低。高光谱与多光谱图像融合（HSI-MSI Fusion）通过融合低分辨率高光谱图像（LR-HSI）与高分辨率多光谱图像（HR-MSI），生成高分辨率高光谱图像（HR-HSI），是提升空间分辨率的主流方法。

现有方法分为两类：基于模型的方法（如CNMF、HySure）依赖手工设计特征，难以处理高维非线性数据；深度学习方法（如CuCaNet、MIAE）性能更优，但严重依赖大量成对训练数据，实际中难以获取。近年来扩散模型在图像生成中表现优异，但现有扩散模型（如PLRDiff、S²CycleDiff）推理速度慢、计算资源消耗大（数千次迭代），难以部署于边缘设备（如无人机）。

**本文动机**：设计一种**无需额外训练数据**、**低资源消耗**且**推理快速**的HSI-MSI融合方法。

## 2. 提出的方法论

### 核心思想
利用HSI可分解为两个低维分量（光谱基 \(E\) 和约化系数 \(A\)）的特性，分别设计轻量级光谱网络和空间网络，仅从观测的LR-HSI和HR-MSI中自学习光谱和空间分布，然后在扩散反向过程中分别重建这两个分量，最终合成HR-HSI（\(Z = A \times_3 E\)）。同时引入自适应残差引导模块（ARGM）稳定采样过程。

### 关键技术细节
- **自学习子空间网络**：
  - 光谱网络：5层全连接网络，输入输出特征维度均为光谱波段数 \(C\)。训练样本从LR-HSI中随机选取 \(d\) 个像素光谱。
  - 空间网络：类UNet结构，9个卷积层（4下采样+1中间+4上采样），每层含2个残差块，输入输出通道数为子空间维度 \(d\)。训练样本从HR-MSI中提取补丁，随机选取一个波段并重复 \(d\) 次。
- **子空间反向扩散过程**：
  - 利用后验采样理论，在噪声估计中引入梯度项，将LR-HSI和HR-MSI作为条件。
  - 梯度项来自引导函数 \(L(\hat{A}_0, \hat{E}_0, X, Y)\)，包含数据保真项（LR-HSI空间降质和HR-MSI光谱降质）。
  - 使用Adam优化器加速收敛（更新动量项）。
- **自适应残差引导模块（ARGM）**：
  - 在每个采样步获取 \(A_{t-1}, E_{t-1}\) 后，计算残差损失 \(L(A_{t-1}, E_{t-1}, X, Y)\)（与引导函数形式相同）。
  - 通过梯度下降更新两个分量：\(A_{t-1} := A_{t-1} - \rho_1 r \nabla_{A_{t-1}} L\)，\(E_{t-1} := E_{t-1} - \rho_2 r \nabla_{E_{t-1}} L\)。
  - 目的：对齐光谱与空间分量，补偿模型预测误差，增强稳定性。

### 算法流程（文字描述）
1. 初始化：从标准正态分布采样 \(A_T, E_T\)，初始化Adam动量。
2. 对于 \(t = T\) 到 \(1\)：
   - 由当前 \(A_t, E_t\) 估计 \(\hat{A}_0, \hat{E}_0\)。
   - 计算引导损失 \(L(\hat{A}_0, \hat{E}_0, X, Y)\)。
   - 更新Adam动量，得到修正后的梯度项。
   - 计算修正后的噪声估计 \(\hat{s}_\theta, \hat{c}_\zeta\)。
   - 采样 \(A_{t-1}, E_{t-1}\) 由式(12)。
   - 应用ARGM：计算残差损失并更新 \(A_{t-1}, E_{t-1}\)。
3. 返回 \(Z_0 = A_0 \times_3 E_0\)。

## 3. 实验设计

### 使用数据集
- **模拟实验**：
  - Pavia University：256×256×103（中心裁剪后）
  - Chikusei：256×256×128
  - KSC：256×256×176
  - 生成方式：LR-HSI通过双三次插值下采样（尺度因子4），HR-MSI通过模式-3张量乘法与模拟光谱响应函数得到。
- **真实数据实验**：
  - DFC2018 Houston 数据集（真实高光谱数据）。

### 评价指标
PSNR↑、SAM↓、ERGAS↓、SSIM↑。

### 对比方法
- 传统方法：CNMF、HySure
- 深度学习方法：CuCaNet、MIAE
- 扩散模型方法：PLRDiff、S²CycleDiff

## 4. 资源与算力

文中明确说明：所有实验在**单块 NVIDIA GeForce RTX 4090 GPU**上进行。未说明训练时长，仅给出了推理时间（参见实验表格）。模型参数量21.85M，内存占用2.11GB，推理时间12秒（Pavia数据集，500步）。

## 5. 实验数量与充分性

### 实验组数
1. **三个模拟数据集**（Pavia、Chikusei、KSC）的定量对比（各表1-3）。
2. **一个真实数据集**（Houston）的定性对比（图3）。
3. **消融实验**（表4）：ARGM模块的有效性，在三个数据集上分别对比“w/o ARGM”与“w/ ARGM”。
4. **参数敏感性分析**（图5、表5）：子空间维度 \(d\)、采样步数 \(T\)、步长 \(\rho_1, \rho_2\)。
5. **模型规模与计算消耗对比**（表6）：与PLRDiff、S²CycleDiff对比参数量、内存、时间。

### 充分性评价
- 实验覆盖了多个典型数据集、多种类型对比方法、完整指标，消融和参数分析齐全，**充分且客观**。
- 所有结果均以表格和可视化形式呈现，误差图也提供了（图2）。
- 对比方法均为该领域SOTA，公平性有保障。

## 6. 主要结论与发现

- 提出的ARGS-Diff在**所有模拟数据集**上，PSNR、SAM、ERGAS、SSIM均优于所有对比方法，PSNR提升约1.3dB。
- 在**真实数据集**上，ARGS-Diff生成图像颜色自然、伪影少，优于其他方法。
- **ARGM模块**显著提升性能（PSNR增加约0.5-0.6dB，SAM改善），时间开销仅增加1-2秒。
- 模型参数仅为21.85M，是PLRDiff的1/20、S²CycleDiff的1/30；内存2.11GB；推理时间12秒（远快于PLRDiff的79秒和S²CycleDiff的297秒）。
- 子空间维度 \(d=8\)、采样步数 \(T=500\) 为最佳设置。

## 7. 优点

1. **无监督自学习**：仅利用观测的LR-HSI和HR-MSI即可训练，无需任何额外成对数据，适合实际场景。
2. **轻量化设计**：光谱网络（5层FC）和空间网络（9层卷积）参数量极少，推理速度快，内存占用低，适合边缘部署。
3. **ARGM模块创新性**：通过残差引导同时更新光谱和空间分量，有效稳定双分量联合采样过程，提升鲁棒性。
4. **性能与效率兼顾**：在PSNR等指标上达到SOTA，同时计算开销远小于其他扩散模型方法。
5. **实验充分**：多数据集、多指标、消融、参数分析、真实数据验证一应俱全，对比方法全面。

## 8. 不足与局限

1. **实验覆盖**：模拟数据仅测试了3个数据集（均为裁剪后256×256大小），更大尺寸或更复杂场景（如航拍大图）未验证。
2. **噪声鲁棒性**：论文仅测试了SNR=35的加噪情况，未探讨不同噪声水平或非高斯噪声的影响。
3. **应用限制**：子空间维度 \(d\) 需手动设定，且对性能敏感（当 \(d>8\) 后性能下降），在实际中需调参。
4. **与其他扩散模型对比公平性**：文中指出PLRDiff和S²CycleDiff需要更多迭代，但ARGS-Diff采用500步，其他方法可能采用不同步数（未明确说明），存在一定差异。
5. **真实数据评价**：真实实验仅提供定性结果，缺乏定量指标（如无参考指标），难以严格比较。
6. **训练过程细节缺失**：未说明网络训练的具体epoch数、学习率等超参数，可复现性略受影响。

（完）

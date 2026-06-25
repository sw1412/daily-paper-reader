---
title: Hyperspectral Pansharpening via Diffusion Models with Iteratively Zero-Shot Guidance
title_zh: 基于扩散模型与迭代零样本引导的高光谱全色锐化
authors: "Xiao, Jin-Liang, Huang, Ting-Zhu, Deng, Liang-Jian, Lin, Guang, Cao, Zihan, Li, Chao, Zhao, Qibin"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Xiao_Hyperspectral_Pansharpening_via_Diffusion_Models_with_Iteratively_Zero-Shot_Guidance_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 6.0
evidence: 提出神经空间-光谱分解用于高光谱特征提取
tldr: 该文针对高光谱全色锐化任务，提出了一种基于扩散模型的迭代零样本引导方法，并引入神经空间-光谱分解（NSSD）来逐步生成RGB细节图像并映射到高光谱图像，从而在避免复杂训练的同时获得高质量的高分辨率高光谱图像。该方法展示了在高光谱图像空间-光谱特征提取方面的潜力。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 700, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1261, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 445, \"height\": 349, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 886, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 885, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 885, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 869, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 713, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-xiao-hyperspectral-pansharpening-via-diffusion-models-with-iteratively-zero-shot-guidance-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 97, \"label\": \"Table\"}]"
motivation: 高光谱全色锐化需要融合全色和高光谱图像，现有扩散模型难以适应高光谱数据。
method: 提出迭代零样本引导扩散方案，结合神经空间-光谱分解，从RGB细节逐步恢复高光谱细节。
result: 在多个数据集上取得了高质量的高光谱全色锐化结果。
conclusion: 为零样本高光谱图像融合提供了新思路，其分解方法对空间-光谱特征提取有启发意义。
---

## Abstract
Hyperspectral pansharpening refers to fusing a panchromatic image (PAN) and a low-resolution hyperspectral image (LR-HSI) to obtain a high-resolution hyperspectral image (HR-HSI). Recently, guiding pre-trained diffusion models (DMs) has demonstrated significant potential in this area, leveraging their powerful representational abilities while avoiding complex training processes. However, these DMs are often trained on RGB images, not well-suited for pansharpening tasks, limited in adapting to the hyperspectral images. In this work, we propose a novel guided diffusion scheme with zero-shot guidance and neural spatial-spectral decomposition (NSSD) to iteratively generate the RGB detail image and map the RGB detail image to target HR-HSI. Specifically, zero-shot guidance employs an auxiliary neural network that trained only with a PAN and LR-HSI to guide pre-trained DMs in generating the RGB detail image, informed by specific prior knowledge. Then, NSSD establishes a spectral mapping from the generated RGB detail image to the final HR-HSI. Extensive experiments are conducted on Pavia, Washington DC, Chukusei, and FR1 datasets to demonstrate that the proposed method significantly enhances the performance of DMs for hyperspectral pansharpening tasks, outperforming existing methods across multiple metrics and achieving improvements in visualization results. The code is available at \href https://github.com/Jin-liangXiao/DM-zs https://github.com/Jin-liangXiao/DM-zs .

---

## 论文详细总结（自动生成）

# 基于扩散模型与迭代零样本引导的高光谱全色锐化 — 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究问题**：高光谱全色锐化（Hyperspectral Pansharpening）旨在融合一幅高空间分辨率的全色图像（PAN）和一幅低空间分辨率的高光谱图像（LR-HSI），生成一幅高空间分辨率的高光谱图像（HR-HSI）。该任务面临两大挑战：一是如何有效利用仅适用于RGB图像的预训练扩散模型（DM）来处理高光谱数据（光谱维数多、数据分布差异大）；二是如何将生成的RGB细节图像准确映射到目标高光谱图像。
- **现有方法不足**：现有基于预训练DM的方法（如PLRDiff、HIR-Diff）虽避免复杂训练，但缺乏针对高光谱数据的特定先验知识，且其固定变换矩阵导致最终结果严重依赖初始估计。传统深度学习方法需要大量训练数据和计算资源，且泛化性差。
- **研究动机**：提出一种新的引导扩散方案，利用零样本引导和神经空间-光谱分解（NSSD），使预训练DM能有效适应高光谱全色锐化任务，同时保持单样本训练能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 采用预训练扩散模型作为生成主干（参数冻结），通过一个可训练的零样本网络将测试数据的特定先验知识注入到扩散引导中，以生成RGB细节图像；再通过神经空间-光谱分解（NSSD）将该细节图像迭代映射为目标HR-HSI。

### 关键技术细节

1. **扩散过程与零样本引导**：
   - 定义反向SDE，在其中加入零样本引导项 \(\nabla_{\mathbf{A}_t} \log p_\psi(\tilde{\mathbf{Y}} \mid \mathbf{A}_t)\)。
   - 条件 \(\tilde{\mathbf{Y}} = (\mathbf{Y}, \mathbf{P}, \mathcal{M}, f_\psi(\mathbf{Y}, \mathbf{P}))\)，其中 \(\mathcal{M}\) 为NSSD映射，\(f_\psi\) 为轻量级零样本网络。
   - 引导损失函数（式10）包含三项：LR-HSI保真项、PAN保真项、以及零样本网络提供的先验项（\(\lambda_1 \|\mathcal{M}(\hat{\mathbf{A}}_0) - f_\psi(\mathbf{Y}, \mathbf{P})\|_F^2\)）。
   - 零样本网络训练：在降尺度尺度上，利用单一测试图像对（PAN、LR-HSI）模拟退化数据，训练网络以学习映射。网络结构为卷积级联结构（CONet）。

2. **神经空间-光谱分解（NSSD）**：
   - 将经典的低秩分解形式 \(\mathbf{X} = \mathbf{A} \times_3 \mathbf{E}\) 扩展为 \(\mathbf{X} = \mathcal{C}_{\theta_1}(\mathbf{A}) \times_3 \mathcal{D}_{\theta_2}(\mathbf{Y})\)。
   - \(\mathcal{C}_{\theta_1}\) 为U-Net型空间因子网络（从RGB细节图像提取空间信息），\(\mathcal{D}_{\theta_2}\) 为全连接层+激活函数的谱因子网络（从LR-HSI提取谱信息）。
   - 通过最小化损失（式14）迭代优化NSSD参数，该损失包含LR-HSI和PAN的重建误差。

3. **整体迭代算法**：
   - 外层循环：交替执行扩散采样（从 \(t=T\) 到 \(t=1\)，并利用当前NSSD计算引导）和NSSD更新（最小化式14）。
   - 最终输出：\(\mathbf{X} = \mathcal{C}_{\theta_1}(\mathbf{A}) \times_3 \mathcal{D}_{\theta_2}(\mathbf{Y})\)。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - Pavia（610×340×115 → 裁剪至256×256×93）
  - Washington DC（WDC，256×256×191）
  - Chikusei（256×256×128）
  - FR1（真实世界数据集，PAN大小240×240，降采样因子6）
- **模拟退化**：LR-HSI由高斯模糊（5×5核）和4倍下采样得到；PAN由真值乘光谱响应函数得到。
- **对比方法**：
  - 传统方法：GSA（2007）、CNMF（2011）、HySure（2014）
  - 零样本方法：ZSL（2023）
  - 扩散方法：PLRDiff（2024）、HIR-Diff（2024）
- **评价指标**：PSNR、SSIM、ERGAS、SAM、RMSE；真实数据使用QNR。

## 4. 资源与算力

- 论文中明确说明：
  - 硬件：64GB RAM、Intel Core i9-10900KF CPU @3.70GHz、NVIDIA GeForce RTX 4070 GPU。
  - 软件：PyTorch 2.0、MATLAB R2022a。
- 未明确给出训练总时长或采样步数的时间开销，但提到NSSD需要更多迭代时间（NSSD更新需20000次外循环？实际为20000次迭代），扩散反向过程步数为100步。整体计算成本与先前DM方法（如PLRDiff）相当，但NSSD带来了额外时间消耗。

## 5. 实验数量与充分性

- **实验数量**：共在4个数据集上进行了实验（3个模拟+1个真实），每个数据集分别与6种现有方法对比。
- **消融实验**：
  - 零样本引导和NSSD的贡献消融（4种组合，表4）。
  - 零样本引导与传统正则化（TV、仅保真）对比（表5）。
  - 不同零样本网络结构（U-Net、DSNet、CONet）对比（表6）。
  - 奇异值分布分析（图8）以证明NSSD的低秩逼近能力。
  - 对引导网络不同结构的影响进行了分析。
  - 还做了运行时间、不同降采样因子和核大小的讨论（见补充材料）。
- **充分性与公平性**：实验覆盖多个数据集和多种类型的方法；指标全面；参数按推荐调整；结果评价客观。但真实数据仅一个（FR1）且指标仅为QNR，未提供更多视觉结果。消融实验充分，有力证明了各组件的有效性。

## 6. 论文的主要结论与发现

- 提出的零样本引导方法能够有效将特定先验知识注入预训练扩散模型，生成更准确的RGB细节图像，且收敛更快（图3）。
- NSSD相比固定变换矩阵能更灵活地捕捉空间-光谱相关性，使最终HR-HSI的奇异值分布更接近真实（图8）。
- 在所有模拟数据集上，所提方法在PSNR、SSIM、SAM、RMSE等指标上均优于所有对比方法；在真实数据集FR1上QNR达到0.832，远超其他方法（第二名为ZSL，0.802）。
- 零样本网络结构采用CONet（卷积级联结构）效果最佳。
- 该方法显著提升了预训练DM在高光谱全色锐化任务上的性能。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  1. 首次将零样本网络引入扩散模型引导，仅需单对测试数据即可训练，无需大量标注数据。
  2. 提出NSSD，用两个神经网络分别建模空间和谱因子，替代固定的低秩分解，增强表示能力。
  3. 交替更新机制使扩散引导与NSSD相互适应，提升了整体性能。
- **实验设计亮点**：
  - 消融实验设计清晰，分别验证了零样本引导和NSSD的贡献。
  - 网络结构对比实验（U-Net、DSNet、CONet）为后续研究提供了参考。
  - 对引导与传统正则化（TV）的比较证明了零样本引导的优势。
  - 分析了奇异值分布，直观展示了NSSD的低秩逼近效果。

## 8. 不足与局限

- **计算开销**：NSSD需要迭代更新，导致总运行时间增加（论文承认NSSD需要更多时间，但未给出量化数据）。
- **参数敏感性**：方法涉及多个超参数（\(\lambda_1, \lambda_2\), rank \(r\)等），在不同数据集上需要调整，泛化参数设置未充分讨论。
- **真实数据集实验有限**：仅FR1一个真实数据集，且仅用QNR一个指标，可能不足以全面评估真实场景下的效果。
- **零样本网络依赖“尺度不变”假设**：该假设在某些场景下可能不成立（如传感器响应变化大），影响引导效果。
- **局限性讨论**：作者承认未来需探索使用预训练网络以减少NSSD时间开销，表明当前方法仍有优化空间。

（完）

---
title: "FRN: Fractal-Based Recursive Spectral Reconstruction Network"
title_zh: FRN：基于分形的递归光谱重建网络
authors: "Ge Meng, Zhongnan Cai, Ruizhe Chen, Jingyan Tu, Yingying Wang, Yue Huang, Xinghao Ding"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=812rmogRgf"
tags: ["query:hsi"]
score: 7.0
evidence: 光谱重建网络从RGB生成高光谱图像，支撑分类任务
tldr: 本文针对高光谱图像获取成本高的问题，提出基于分形的递归光谱重建网络FRN。该方法通过递归调用原子重建模块，由粗到细地预测光谱波段，从RGB图像逐步生成高光谱图像。实验表明该方法能有效重建光谱信息，降低高光谱数据获取门槛，为后续高光谱图像分类、检测等任务提供高质量输入。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 669, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 606, \"height\": 614, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 724, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 713, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1451, \"height\": 1064, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-812rmogrgf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1373, \"height\": 544, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-812rmogrgf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 384, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-812rmogrgf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 741, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-812rmogrgf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 711, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-812rmogrgf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 712, \"height\": 288, \"label\": \"Table\"}]"
motivation: 高光谱图像获取成本高昂，现有光谱重建方法一次性整合全谱信息效果有限。
method: 提出基于分形的递归光谱重建网络，通过递归调用原子模块逐波段由粗到细预测光谱。
result: 在多个数据集上重建精度优于现有方法，有效降低高光谱获取成本。
conclusion: 为低成本高光谱数据获取提供新途径，助力高光谱图像分类等下游应用。
---

## Abstract
Generating hyperspectral images (HSIs) from RGB images through spectral reconstruction can significantly reduce the cost of HSI acquisition. In this paper, we propose a Fractal-Based Recursive Spectral Reconstruction Network (FRN), which differs from existing paradigms that attempt to directly integrate the full-spectrum information from the R, G, and B channels in a one-shot manner. Instead, it treats spectral reconstruction as a progressive process, predicting from broad to narrow bands or employing a coarse-to-fine approach for predicting the next wavelength. Inspired by fractals in mathematics, FRN establishes a novel spectral reconstruction paradigm by recursively invoking an atomic reconstruction module. In each invocation, only the spectral information from neighboring bands is used to provide clues for the generation of the image at the next wavelength, which follows the low-rank property of spectral data. Moreover, we design a band-aware state space model that employs a pixel-differentiated scanning strategy at different stages of the generation process, further suppressing interference from low-correlation regions caused by reflectance differences. Through extensive experimentation across different datasets, FRN achieves superior reconstruction performance compared to state-of-the-art methods. Code is available at https://github.com/mongko007/frn.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：高光谱图像（HSI）获取成本高昂（如CASSI系统），而RGB相机广泛可用。从RGB图像光谱重建HSI可大幅降低成本，但该任务本质上是病态的（一个RGB可能对应多个HSI）。
- **动机**：现有方法（CNN/Transformer）倾向于一次性从RGB通道整合全谱信息，计算开销大且难以充分利用光谱的低秩特性。受数学中分形结构自相似性的启发，作者尝试将光谱重建分解为从宽波段到窄波段的渐进过程，从而降低病态问题的复杂度。

## 2. 论文提出的方法论
- **核心思想**：提出分形递归光谱重建网络（FRN），将HSI重建视为一个递归过程：通过递归调用原子重建模块，每次只利用相邻波段信息预测下一波长图像，符合HSI的低秩性质。
- **关键技术**：
  - **分形生成器**：定义原子生成器 \(g_i\)，从输入 \(x_i\) 生成下一级 \(x_{i+1}\)。给定递归层数 \(m\)，每个原子生成器产生长度为 \(n\) 的子序列，总波段数 \(K = n^m\)。通过分治策略递归分解联合分布 \(p(y_1, ..., y_K)\)。
  - **BAMamba（带波段感知掩码的状态空间模型）**：作为原子生成器，基于VMamba（线性复杂度）设计。关键创新是引入波段感知掩码 \(M\)，根据 \(\Delta A\) 系数阈值 \(\epsilon\) 过滤低空间相关像素，抑制隐藏状态中的干扰信息。公式：\(y_t = (C \odot M) h_t\)，其中 \(M\) 由 \(\Delta A \ge \epsilon\) 决定。整体流程为 \(feat_{k+1} = CS(LN(feat_k)) \odot SiLU(LN(feat_k)) + feat_k\)，其中CS包含DW Conv → SiLU → SSM → LN。
- **损失函数**：像素级L1损失。

## 3. 实验设计
- **数据集**：CAVE数据集（32个HSI，31波段，400-700nm）和Harvard数据集（50个HSI，31波段，420-720nm）。均按训练/验证/测试划分（CAVE: 20/6/6；Harvard: 30/10/10）。
- **Benchmark**：对比7种SOTA方法：HSACS、SSRNet、HSRNet、AWAN、MST++、LTRN、MSFN。
- **评价指标**：PSNR、SSIM、RMSE、UIQI。

## 4. 资源与算力
- 文中明确说明：实验在单张NVIDIA RTX 4090 GPU上完成，使用PyTorch框架。未提供训练时长或总计算量等详细信息。

## 5. 实验数量与充分性
- **主要对比实验**：在两个数据集上均与7种SOTA方法比较，报告了四项指标及参数量。
- **消融实验**：共3组：
  - 抑制阈值 \(\alpha\) 的消融（6个配置 + w/o）。
  - 递归层数 \(M\) 的消融（4个配置）。
  - 参考光谱数 \(S\) 的消融（5个配置）。
- **视觉结果**：展示了CAVE和Harvard数据集上的重建图像、残差图及光谱曲线。
- **充分性评估**：实验覆盖了核心参数的影响，对比方法全面，数据划分合理，结果客观公平。但未在更多样化数据集（如噪声或低光照场景）上验证泛化性。

## 6. 论文的主要结论与发现
- FRN在CAVE和Harvard数据集上均取得最优性能：CAVE上PSNR 41.05 dB（比第二名高1.2 dB），SSIM 0.99；Harvard上PSNR 42.87 dB（高0.23 dB）。同时参数量仅0.30M，远小于其他方法。
- 递归策略（从粗到细）有效降低病态问题难度，分形结构契合HSI的低秩性。
- BAMamba通过波段感知掩码过滤低相关像素，提升重建质量且保持线性复杂度。

## 7. 优点
- **方法论**：首次将分形概念引入光谱重建，建立渐进递归新范式，参数效率极高。
- **算法设计**：BAMamba利用状态空间模型的线性复杂度和波段自适应掩码，兼顾效率与性能；分形递归使网络结构自相似，易于扩展。
- **实验验证**：在多个数据集上超越SOTA，消融实验完整揭示了关键参数的影响。

## 8. 不足与局限
- **计算开销**：递归调用机制本身引入较大计算量（文中明确承认“significant computational overhead”），是未来优化方向。
- **实验范围**：仅在CAVE和Harvard两个实验室/受限场景数据集上评估，未在真实遥感或动态场景下测试，泛化性有待验证。
- **超参数敏感**：阈值 \(\alpha\) 需凭经验设定（文中设为0.5），对性能影响较大，可能需针对不同数据调整。
- **应用限制**：假设相邻波段间关联性强，若光谱采样间隔大或存在剧烈非线性变化，递归方式可能效果下降。

（完）

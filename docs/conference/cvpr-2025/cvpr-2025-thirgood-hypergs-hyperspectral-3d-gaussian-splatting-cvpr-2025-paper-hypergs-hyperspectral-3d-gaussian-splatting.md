---
title: "HyperGS: Hyperspectral 3D Gaussian Splatting"
title_zh: HyperGS：高光谱3D高斯溅射
authors: "Thirgood, Christopher, Mendez, Oscar, Ling, Erin, Storey, Jon, Hadfield, Simon"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Thirgood_HyperGS_Hyperspectral_3D_Gaussian_Splatting_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 6.0
evidence: 提出潜在3D高斯溅射用于高光谱特征提取
tldr: 该文提出HyperGS，一种基于潜在3D高斯溅射的高光谱新视角合成框架，能够同时对空间和光谱进行渲染，通过编码材料属性实现高光谱数据的高效表示。该方法在多个基准上优于现有方法，其潜在空间学习为高光谱空间-光谱特征提取提供了新工具。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1787, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1788, \"height\": 823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 846, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1818, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1809, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1793, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1794, \"height\": 399, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 523, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-thirgood-hypergs-hyperspectral-3d-gaussian-splatting-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 333, \"label\": \"Table\"}]"
motivation: 高光谱数据维度高，传统新视角合成方法效率低。
method: 采用潜在3D高斯溅射，结合自适应密度函数和剪枝技术，在高维潜在空间中进行视图合成。
result: 在多个高光谱基准上优于现有新视角合成方法。
conclusion: 为高光谱数据的三维空间-光谱建模提供了有效方法，可迁移至分类与检测任务。
---

## Abstract
We introduce HyperGS, a novel framework for Hyperspectral Novel View Synthesis (HNVS), based on a new latent 3D Gaussian Splatting (3DGS) technique. Our approach enables simultaneous spatial and spectral renderings by encoding material properties from multi-view 3D hyperspectral datasets. HyperGS reconstructs high-fidelity views from arbitrary perspectives with improved accuracy and speed, outperforming currently existing methods. To address the challenges of high-dimensional data, we perform view synthesis in a learned latent space, incorporating a pixel-wise adaptive density function and a pruning technique for increased training stability and efficiency. Additionally, we introduce the first HNVS benchmark, implementing a number of new baselines based on recent SOTA RGB-NVS techniques, alongside the small number of prior works on HNVS. We demonstrate HyperGS's robustness through extensive evaluation of real and simulated hyperspectral scenes with a 14dB accuracy improvement upon previously published models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：高光谱成像（HSI）能捕捉连续光谱信息，对遥感、医疗、环境监测等至关重要。然而，现有新视角合成（NVS）方法主要针对RGB图像，无法直接处理高光谱数据的高维特性（数百个通道）。传统的RGB 3DGS和NeRF方法在高光谱数据上表现不佳：NeRF训练慢、渲染慢、参数多；3DGS直接扩展则出现训练不稳定、伪影、细节丢失等问题。已有方法HS-NeRF性能有限。
- **动机**：需要一种高效、准确的高光谱新视角合成（HNVS）框架，能够同时建模空间和光谱信息，实现实时或近实时的渲染。
- **整体含义**：HyperGS首次将3D高斯溅射（3DGS）成功扩展到高光谱领域，通过潜在空间学习、自适应密度控制和全局剪枝等技术，解决了高维数据带来的挑战，显著提升了HNVS的精度和速度。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- 在高维潜在空间中进行3DGS优化，而非直接在原始高光谱通道上操作。利用预训练的自编码器（AE）压缩光谱维度，降低计算负担并约束重建误差。
- 每个3D高斯体附带一个潜在光谱特征向量，并通过视图依赖的MLP预测视角相关的光谱和透明度。
- 引入针对高光谱的初始化、自适应密度化（深度缩放梯度）和全局剪枝策略，提升训练稳定性和场景质量。

### 关键技术细节
1. **高光谱压缩**：
   - 使用轻量1D卷积自编码器（含Squeeze-Excitation模块）对每个像素的光谱进行压缩，得到潜在表示（LHSI）。编码器输出维度为m（远小于原始通道数），解码器在训练和推理时固定（frozen）。
   - 损失函数：Huber损失，处理噪声。

2. **潜在高光谱3DGS**：
   - 每个3D高斯体参数包括：位置、缩放、旋转、不透明度、以及潜在光谱特征f_i（维度m）。
   - 新增视图依赖MLP：输入高斯中心坐标和视图方向，通过哈希编码，输出视图相关的光谱修正f̃_i,d和不透明度修正σ̃_i,d。
   - 混合渲染方程（修改后的公式8-10）：
     - 透射率 T_i,d = ∏_{j<i} (1 - α_j σ_j σ̃_j,d)
     - 潜在像素光谱 Ĉ(p,d) = Σ T_i,d α_i f_i f̃_i,d
     - 最终光谱 C(p,d) = Decoder(Ĉ(p,d))
   - 损失函数：加权组合Charbonnier损失（空间）和余弦相似度（光谱），并结合SSIM保持空间一致性（公式11-12）。

3. **初始化**：
   - 将高光谱图像转换为单通道灰度图（选择前景方差最大的通道），运行COLMAP获得稀疏点云和相机位姿。
   - 将每个3D点投影到所有训练视图的潜在图像上，取平均作为该高斯的初始光谱特征（公式14）。

4. **潜在高光谱密度化**：
   - 针对高光谱数据稀疏、梯度不稳定的问题，引入深度缩放函数：梯度除以 (|E_d X_i| / (β_field × R))²，降低近相机高斯的影响。
   - 分裂/克隆条件：当深度缩放后的梯度幅值超过阈值θ_q时触发。

5. **全局高光谱高斯剪枝**：
   - 对每个高斯、每个像素、每个视图计算重要性得分：I = (1 - |真实光谱 - 解码后光谱|) × α_i × T_i。
   - 保留在所有视角-像素组合中排名前K的高斯（即至少在一个像素-视角对中重要性排名前τ_p）。
   - 避免跨视图平均导致的过剪枝。

## 3. 实验设计

- **数据集**：
  - **真实数据集**：HS-NeRF发布的两个数据集：
    - BaySpec数据集：141通道，每场景约360张图像，噪声较高（快拍导致）。
    - SOC710-VP (SOP) 数据集：128通道，每场景约40张图像，空间分辨率高，噪声低。
  - **合成数据集**：从ScanNetv200中选择场景，用语义标签替换为不同高光谱特征（见补充材料）。
- **基准**：首次为HNVS建立全面基准，包括：
  - 传统NeRF变体：NeRF、MipNeRF、MipNeRF-360、Nerfacto、TensoRF（即Spec-NeRF）。
  - 已有高光谱方法：HS-NeRF。
  - 3DGS基础版本：3DGS（使用本文的初始化方案，移除球谐系数）。
- **指标**：PSNR（↑）、SSIM（↑）、光谱角度映射SAM（↓）、RMSE（↓）。
- **划分**：90%训练，10%测试。
- **主要对比**：HyperGS在所有场景和数据集上均优于所有基线，尤其在BaySpec上PSNR达27.11，优于第二的MipNeRF360（26.53）；在SOP上PSNR达30.51，远超3DGS（28.58）和HS-NeRF（14.44）。SAM和RMSE也全面领先。

## 4. 资源与算力

- 论文明确指出：所有实验在 **NVIDIA A100 80GB GPU** 上进行，因为MipNeRF-360需要较大显存。其他方法可在NVIDIA 3090上运行。
- 训练周期：HyperGS训练 **60k迭代**，NeRF方法使用标准1024条光线每批次。
- 没有给出每个方法具体的训练时间（小时数），但指出HyperGS比NeRF方法更快。具体速度瓶颈分析在补充材料中。

## 5. 实验数量与充分性

- **实验组数**：
  - 真实数据集两个（BaySpec 3场景，SOP 4场景），合成数据集（ScanNetv200子集），覆盖不同噪声、通道数、视角密度。
  - 消融实验（表3）：逐步添加各组件（光谱SfM初始化、潜在空间AE、密度化、剪枝、视图依赖MLP、自定义损失函数），共6个消融步骤，验证每部分贡献。
  - 补充材料中还有更多消融：剪枝策略评分函数、AE性能（不同数据和潜在尺寸）、全局剪枝策略、系统速度瓶颈等。
- **充分性**：实验设计较为全面，覆盖真实和合成数据，对比多个强基线（包括RGB NVS的最佳方法），消融实验系统。但未包含真实的室外大场景或动态场景。
- **客观性与公平性**：所有方法在相同硬件、相同训练/测试划分下比较。HS-NeRF和3DGS的适应性实现经过调整。但论文未说明超参数搜索过程，存在一定调优偏差风险。

## 6. 主要结论与发现

- HyperGS在高光谱新视角合成任务上显著优于所有现有的NeRF和3DGS方法，PSNR提升高达14dB（对比HS-NeRF）。
- 潜在空间学习是核心：压缩维度、约束误差、提高噪声鲁棒性。
- 自适应密度化（深度缩放）和像素级全局剪枝有效稳定训练、提升质量、控制高斯数量。
- 在BaySpec（多视角、高噪声）和SOP（少视角、低噪声）两种场景下均表现最佳，证明泛化能力。
- 消融实验证实每个组件都有正向贡献，其中潜在空间AE和视图依赖MLP贡献最大。

## 7. 优点

- **方法创新**：首次将3D高斯溅射成功应用于高光谱数据，提出潜在空间3DGS框架，解决了高维优化困难。
- **技术支持**：精心设计的密度化和剪枝策略（深度缩放、像素级重要性）针对高光谱特性优化，而非通用方法。
- **实验全面**：建立首个HNVS基准，包含多类NeRF变体和3DGS基线，数据集覆盖不同特性。
- **性能突出**：在精度（PSNR最高30.51，SAM最低0.00415）和渲染速度上明显优于NeRF方法，且高斯数量可控（~310k）。
- **损失函数设计**：结合Charbonnier、余弦相似度和SSIM，兼顾空间和光谱质量。

## 8. 不足与局限

- **实验覆盖**：真实数据集仅两个相机（BaySpec和SOP），场景数量有限（7个），且均为室内小物体或植物场景，缺乏室外大场景、复杂光照、动态场景验证。
- **部署限制**：依赖COLMAP进行SfM初始化，对于纹理稀疏或高噪声场景可能不稳定；虽用灰度图优化，但仍需先验3D点云。
- **潜在空间依赖**：自编码器固定后无法在推理时调整，可能无法适应训练场景外的新光谱分布。
- **算力开销**：虽然比NeRF快，但未与极快方法（如Instant-NGP）直接对比；潜在空间MLP和AE解码增加计算，未给出详细帧率。
- **剪枝策略**：像素级重要性计算需要遍历所有高斯-像素对，可能带来额外内存开销，论文未详细分析。
- **复现难度**：未开源代码，补充材料虽有细节但部分超参数（如β_field、阈值θ_q、K值）未完全公开。

（完）

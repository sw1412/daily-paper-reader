---
title: Spectral Compressive Imaging via Chromaticity-Intensity Decomposition
title_zh: 基于色度-强度分解的光谱压缩成像
authors: "Xiaodong Wang, Zijun He, Ping Wang, Lishun Wang, Yanan Hu, Xin Yuan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xQfZprbSWL"
tags: ["query:hsi"]
score: 8.0
evidence: 高光谱图像的色度-强度分解，提取光谱-空间特征
tldr: 针对编码孔径快照光谱成像中高光谱图像重建的严重病态和光照依赖问题，本文提出色度-强度分解框架，将HSI分解为空间平滑的强度图和光谱可变的色度立方体。色度编码了光照不变的反射率，并富含高频空间细节和局部光谱稀疏性。该方法有效重建HSI，为后续高光谱图像分类和目标检测等任务提供了更好的输入表示和数据增强基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 540, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1409, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1419, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1287, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 427, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 713, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1268, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 567, \"height\": 192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1286, \"height\": 787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xqfzprbswl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1243, \"height\": 741, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xqfzprbswl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 728, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xqfzprbswl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 877, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xqfzprbswl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xqfzprbswl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 934, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xqfzprbswl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1125, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xqfzprbswl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1075, \"height\": 156, \"label\": \"Table\"}]"
motivation: CASSI中HSI重建病态且受光照影响，难以恢复光照不变的光谱反射率。
method: 提出色度-强度分解框架，将HSI分解为空间平滑强度图和光谱可变色度立方体，色度编码光照不变反射率。
result: 实验表明该方法能有效重建HSI，提取光照不变特征，提升后续应用性能。
conclusion: 该分解为HSI重建与特征提取提供了新思路，有利于高光谱图像的分析与理解。
---

## Abstract
In coded aperture snapshot spectral imaging (CASSI), the captured measurement entangles spatial and spectral information, posing a severely ill-posed inverse problem for hyperspectral images (HSIs) reconstruction. Moreover, the captured radiance inherently depends on scene illumination, making it difficult to recover the intrinsic spectral reflectance that remains invariant to lighting conditions. To address these challenges, we propose a chromaticity-intensity decomposition framework, which disentangles an HSI into a spatially smooth intensity map and a spectrally variant chromaticity cube. The chromaticity encodes lighting-invariant reflectance, enriched with high-frequency spatial details and local spectral sparsity. Building on this decomposition, we develop CIDNet—a Chromaticity-Intensity Decomposition unfolding network within a dual-camera CASSI system. CIDNet integrates a hybrid spatial-spectral Transformer tailored to reconstruct fine-grained and sparse spectral chromaticity and a degradation-aware, spatially-adaptive noise estimation module that captures anisotropic noise across iterative stages. Extensive experiments on both synthetic and real-world CASSI datasets demonstrate that our method achieves superior performance in both spectral and chromaticity fidelity. Code is released at: \url{https://github.com/xiaodongwo/CIDNet}.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在编码孔径快照光谱成像（CASSI）系统中，传感器获取的二维压缩测量值将空间和光谱信息高度混叠，导致从测量值中重建三维高光谱图像（HSI）是一个严重病态的逆问题。此外，测量值是辐射度信号，天然依赖于场景照明，难以恢复光照不变的固有光谱反射率。
- **研究背景**：现有方法（如优化方法、Plug-and-Play、深度展开、端到端网络、扩散模型等）大多隐式学习空间-光谱特征，缺乏显式的物理可解释分解；且普遍忽视照明变化对重建精度的影响。RGB图像中的内在图像分解（Retinex）和遥感中的反射率-照明分离方法尚未被引入CASSI重建。
- **整体含义**：本文首次提出将HSI分解为光照不变的**色度（Chromaticity）** 和空间平滑的**强度（Intensity）**，从而将病态逆问题转化为更易于求解的色度恢复问题，并实现对抗照明变化的鲁棒重建。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将高光谱图像立方体 \(\mathbf{X} \in \mathbb{R}^{H \times W \times N_\lambda}\) 分解为强度图 \(\mathbf{I} \in \mathbb{R}^{H \times W}\) 和色度立方体 \(\mathbf{C} \in \mathbb{R}^{H \times W \times N_\lambda}\)，满足 \(\mathbf{X}(u,v,\lambda) = \mathbf{C}(u,v,\lambda) \odot \mathbf{I}(u,v)\)。强度定义为每个像素的平均光谱能量；色度为归一化光谱签名 \(\mathbf{C} = \mathbf{X} / (\mathbf{I} + \epsilon)\)。色度具有光照不变性、光谱稀疏性和高频细节丰富等优点。在双相机CASSI系统中，强度可由另一路灰度（或RGB）相机获取（PAN-Intensity等价性）。
- **关键技术细节**：
  - **降质模型**：引入强度引导掩码 \(\mathbf{M}'(u,v) = \mathbf{I}(u,v) \odot \mathbf{M}(u,v)\)，将测量方程改写为 \(\mathbf{y} = \mathbf{H}\mathbf{c} + \mathbf{n}\)，其中 \(\mathbf{H}\) 为有效感测矩阵，\(\mathbf{n} \sim \mathcal{N}(0,\Sigma)\) 为各向异性高斯噪声。
  - **优化框架**：基于半二次分裂（HQS），推导出带各向异性噪声的梯度投影更新公式 \(\mathbf{c}^{(k+1)} = \mathbf{z}^{(k)} + \mathbf{H}^\top(\mathbf{H}\mathbf{H}^\top + \mu\boldsymbol{\Sigma})^{-1}(\mathbf{y} - \mathbf{H}\mathbf{z}^{(k)})\)，以及噪声估计模块（DNEM），可动态估计每阶段的空间自适应噪声方差 \(\boldsymbol{\Sigma}^{(k)}\) 和去噪强度 \(\omega^{(k)}\)。
  - **网络架构（CIDNet）**：采用K阶段展开结构。每阶段包含DNEM、解析重建层和可学习去噪器。去噪器采用非对称U-Net骨干，编码器使用基于窗口的自注意力（Spa-LWSA，即Swin Transformer），解码器使用稀疏TopK光谱注意力（Spec-TKSA）。Spec-TKSA在每个局部空间窗口内对光谱通道执行TopK自注意力，融合多个稀疏率，捕捉光谱的局部稀疏结构。
  - **损失函数**：\(\ell_2\) 损失，监督重建色度与真实色度之间的差异。

## 3. 实验设计：使用数据集、Benchmark、对比方法

- **数据集**：
  - 训练：CAVE数据集（32张高光谱图像，空间分辨率512×512）。
  - 测试：KAIST数据集（选取10个场景，分辨率2704×3376）。
  - 真实数据：来自双相机CASSI系统的真实测量数据（Ninja场景）。
- **Benchmark**：重建质量评估使用PSNR和SSIM，同时分别评估HSI整体重建、色度重建和强度重建效果。对真实数据仅作定性比较。
- **对比方法**：
  - 单相机方法：DeSCI、GAP-Net、MST-L、DAUHST-9stg、SSR-9stg。
  - 双相机方法：PIDS（RGB指导）、In2SET-9stg。
  - 同时将CIDNet与CID-TV（传统迭代版）在真实数据上对比。

## 4. 资源与算力

- 文中明确说明：所有实验在 **Nvidia A40 GPU** 上完成。训练使用 **Adam优化器**，初始学习率 \(4\times10^{-4}\)，余弦退火调度，训练 **300个epoch**。
- 未说明具体GPU数量、批次大小或总训练时长（大约几天等）。可认为算力资源中等（单卡A40可满足需求）。

## 5. 实验数量与充分性

- **数量**：
  - 模拟数据集10个场景×7种对比方法+多个CIDNet变体（3、5、7、9阶段），定量对比（表2、表3）。
  - 真实数据1个场景定性对比（图6）。
  - 消融实验：表4（强度、HSST、DNEM逐项消融）、表5（不同注意力机制对比）、表6（强度引导掩码在不同算法中的有效性）。
  - 传统优化对比（附录A.5，图7）。
  - 噪声图可视化（附录A.7，图10）。
  - 附加色度vs. HSI视觉比较（附录A.6，图9）。
- **充分性与公平性**：
  - 对比方法涵盖主流优化、展开、端到端、双相机等方法，且与CIDNet在同一设置下比较（模拟数据使用相同forward模型）。
  - 消融实验全面，验证了核心组件（分解、注意、噪声估计）的贡献。
  - 在HSI和色度两个层面分别对比（表2和表3），公平性较好。
  - 未见统计显著性误差棒报告，但网络结果复现性由代码保证。

## 6. 论文的主要结论与发现

- 色度-强度分解能有效分离光照影响，使重建更关注光照不变的光谱反射率。
- CIDNet在KAIST模拟数据集上以 **44.12 dB PSNR**、**0.991 SSIM** 的平均HSI重建性能超越所有对比方法（包括单相机和双相机SOTA），色度重建也显著领先（平均35.81 dB PSNR）。
- 消融实验表明，每个组件（强度掩码、混合空间-光谱Transformer、双噪声估计模块）均对性能有显著贡献。
- 真实数据实验也证明CIDNet在双相机硬件设置中的有效性。
- 稀疏TopK光谱注意力能有效利用色度的局部光谱稀疏性，比全连接光谱注意力更高效且更准确。

## 7. 优点

- **物理可解释性**：首次将内在图像分解思想引入CASSI重建，明确分离光照与反射率，理论清晰。
- **创新性设计**：提出强度引导掩码、各向异性噪声建模、稀疏TopK光谱注意力、双噪声估计模块等，具有原创性。
- **性能领先**：在KAIST模拟数据集上PSNR/SSIM全面超越SOTA，且参数量和FLOPs控制在合理范围（9阶段4.19M参数，74.16G FLOPs）。
- **双相机兼容**：可无缝融入双相机CASSI系统，利用额外灰度/RGB相机提供强度先验。
- **开源代码**：提供GitHub仓库，可复现实验。

## 8. 不足与局限

- **依赖双相机**：目前方法假设强度已知（由双相机中的灰度/RGB相机提供），在单相机CASSI系统中不能直接应用。作者在附录中提及可先训练一个强度网络再冻结，再训练CIDNet，但未在论文中实验验证。
- **训练数据规模有限**：仅使用CAVE 32张图像训练（虽然常用），可能泛化性受限于小样本。未在大规模高光谱数据集（如 Houston、Chikusei）上测试。
- **真实实验仅定性**：真实数据只展示了4个波段的视觉效果，无定量指标（因为GT未知），说服力稍弱。
- **未报告误差棒**：没有多次运行的标准差，难以判断性能的统计显著性。
- **计算开销**：9阶段CIDNet的FLOPs（74.16G）略高于某些对比方法（如MST-L仅28.15G），可能影响实时性。
- **应用局限**：分解假设光照均匀空间变化（全局光照），对于局部阴影或复杂光照场景的适用性有待验证。

（完）

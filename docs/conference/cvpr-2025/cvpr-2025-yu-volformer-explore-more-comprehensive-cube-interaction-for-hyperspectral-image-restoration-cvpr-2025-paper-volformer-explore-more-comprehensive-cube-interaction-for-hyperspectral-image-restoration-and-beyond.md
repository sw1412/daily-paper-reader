---
title: "VolFormer: Explore More Comprehensive Cube Interaction for Hyperspectral Image Restoration and Beyond"
title_zh: VolFormer：探索更全面的高光谱图像立方体交互用于图像恢复及更多
authors: "Yu, Dabing, Gao, Zheng"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Yu_VolFormer_Explore_More_Comprehensive_Cube_Interaction_for_Hyperspectral_Image_Restoration_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 8.0
evidence: 体素自注意力机制用于高光谱图像的谱空特征提取
tldr: 现有Transformer在高光谱图像恢复中仅关注单维度自注意力，缺乏谱空维度间全面交互。该工作提出VolFormer，通过体素自注意力机制实现跨空间和光谱维度的立方体交互，首次将三维卷积与Transformer结合。在多个恢复任务上取得领先性能，其核心的谱空特征提取能力可迁移至分类与检测任务。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1314, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1657, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1665, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 826, \"height\": 235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1189, \"height\": 246, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1736, \"height\": 891, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1720, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1637, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1503, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 903, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-yu-volformer-explore-more-comprehensive-cube-interaction-for-hyperspectral-image-restoration-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1792, \"height\": 806, \"label\": \"Table\"}]"
motivation: 现有方法缺乏跨谱空维度的全面交互，限制了高光谱图像恢复性能。
method: 提出体素自注意力嵌入Transformer网络，实现谱空立方体的三维交互特征提取。
result: 在公开高光谱恢复数据集上取得最优结果，证明了方法的有效性。
conclusion: VolFormer不仅提升了图像恢复质量，其谱空特征提取方法也可推广至分类及检测任务。
---

## Abstract
Capitalizing on the talent of self-attention in capturing non-local features, Transformer architectures have exhibited remarkable performance in single hyperspectral image restoration. For hyperspectral images, each pixel is located in the hyperspectral image cubes with a large spectral dimension and two spatial dimensions. Although uni-dimensional self-attention, like channel self-attention or spatial self-attention, builds long-range dependencies in spectral or spatial dimensions, they lack more comprehensive interactions across dimensions. To tackle the above drawback, we propose a VolFormer, a volumetric self-attention embedded Transformer network for single hyperspectral image restoration. Specifically, we propose volumetric self-attention (VolSA), which extends the interaction from 2D flat to 3D cube. VolSA can simultaneously model token interaction in the 3D cube, mining the potential correlations between the hyperspectral image cube. An attention decomposition form is proposed to reduce the computational burden of modeling volumetric information. In practical terms, VolSA adapts double similarity matrixes in spatial and channel dimensions to implicitly model 3D context information while transforming the complexity from cubic to quadratic. Additionally, we introduce the explicit spectral location prior to enhance the proposed self-attention. This property allows the target token to perceive global spectral information while simultaneously assigning different levels of attention to tokens at varying wavelength bands. Extensive experiments demonstrate that VolFormer achieves record-high performance on hyperspectral image super-resolution, denoise and classification benchmarks. Particularly, VolSA is portable and achieves inspiring results in hyperspectral classification. The source code is available at https://github.com/yudadabing/VolFormer.

---

## 论文详细总结（自动生成）

# VolFormer 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：高光谱图像（HSI）具有大光谱维度和两个空间维度，每个像素位于三维立方体中。现有基于Transformer的方法（如空间自注意力SSA、通道自注意力CSA）仅在单一维度（空间或光谱）上建立长程依赖，缺乏跨维度的全面交互，导致无法充分利用高光谱立方体中的潜在相关性。
- **研究动机**：为了更全面地建模高光谱图像立方体中像素间的三维上下文关系，同时避免立方级计算复杂度，提出一种新的体素自注意力（VolSA）机制，并嵌入Transformer网络形成VolFormer。
- **整体含义**：VolFormer将交互从2D平面扩展到3D立方体，通过双相似性矩阵隐式建模三维信息，并引入显式光谱位置先验，在超分辨率、去噪和分类任务上均达到最优性能。

## 2. 论文提出的方法论

### 核心思想
- **VolSA（Volumetric Self-Attention）**：通过双分支投影——**光谱维投影**和**空间维投影**——分别生成两个二维相似性矩阵，再以“接力通信”方式隐式构建三维立方体中的长程依赖，将注意力复杂度从立方级 O(H²W²C²) 降低到平方级 O(H²W² + C²)。
- **光谱位置先验（Spectrum Location Prior）**：利用高光谱连续窄带特性，设计双向指数衰减矩阵 D，描述光谱通道间相关性随波长距离衰减，增强自注意力对光谱位置信息的感知。

### 关键技术细节
1. **光谱维投影**：
   - 输入 X_in ∈ R^{H×W×C}，经1×1卷积和3×3深度可分离卷积生成 Q_spe, K_spe, V_spe ∈ R^{C×HW}。
   - 计算光谱维投影矩阵 A_spe ∈ R^{C×C}：A_spe = Softmax( (Q_spe·K_spe)/ε + D + B )，其中ε是可学习缩放参数，D是双向衰减矩阵，B是相对位置编码。
   - 分多头处理，拼接得到隐层特征 Y_spe。

2. **空间维投影**：
   - 线性投影生成 Q_spa, K_spa ∈ R^{HW×C}。
   - 计算空间维投影矩阵 A_spa ∈ R^{HW×HW}：A_spa = Softmax( Q_spa·K_spa / √C + B )。
   - 最终输出：Y_vol = W_out · (Y_spe · A_spa + Y_spe)。

3. **网络架构**：
   - 整体采用残差中残差设计，包含浅层特征提取（3×3卷积）、深层特征提取（堆叠多个Transformer块，每块包含若干Transformer层）、图像重建（卷积+上采样）。
   - 使用混合数据集训练（HSI数据集+辅助RGBI数据集），损失函数为L1损失和空间光谱总变分（SSTV）损失。

## 3. 实验设计

### 数据集和场景
- **超分辨率任务**：
  - 自然HSI：CAVE数据集（31个波段）
  - 遥感HSI：Pavia数据集、Chikusei数据集
  - 辅助RGBI：DIV2K
  - 尺度因子：×4、×8
- **去噪任务**：
  - 合成噪声：ICVL数据集，添加高斯噪声（σ=30,50,70，随机[30,70]）及混合噪声（高斯+脉冲+条纹）
  - 真实噪声：HSIDwRD数据集
  - 辅助RGB去噪：RENOIR
- **分类任务**：
  - HU2013数据集

### 对比方法
- **超分辨率**：GDRRN、MCNet、ERCSR、SSPSR、HSISR、DSTrans、ESSA
- **去噪**：BM4D、KBR、WLRTR、NGmeet、HSID-CNN、QRNN3D、DPPR、SST
- **分类**：SVM、DBMA、DBDA、SSRN、SSFTT、BS2T、CS2DT、HybridFormer

### 评价指标
- 超分辨率：SAM、CC、ERGAS、RMSE、MPSNR、MSSIM
- 去噪：MPSNR、MSSIM（合成噪声）；MPSNR、MSSIM、SAM（真实噪声）
- 分类：每类精度、OA、AA、Kappa

## 4. 资源与算力
- **文中提及**：所有实验在 NVIDIA GeForce RTX 3090 GPU 上进行。
- **未明确说明**：GPU数量、训练总时长、具体显存占用等细节未给出。

## 5. 实验数量与充分性

### 实验数量
- **超分辨率**：3个数据集（CAVE、Pavia、Chikusei）×2个尺度（×4、×8） → 6组定量对比，附有可视化结果。
- **去噪**：5个噪声水平（σ=30,50,70,随机[30,70],混合噪声）+ 1个真实噪声数据集 → 6组定量对比。
- **分类**：1个数据集（HU2013）与8个方法对比。
- **消融实验**：
  - 不同自注意力机制：SSA、CSA、SSA+CSA、VolSA w/o SLP、VolSA → 对比MPSNR/MSSIM/SAM。
  - 使用LAM和DI分析交互距离。
  - 文中还提到其他消融（附录11和12）未在正文详细展开。

### 充分性与客观性
- 对比方法覆盖传统和深度学习SOTA，且均为近年工作。
- 实验场景多样（自然/遥感、合成/真实噪声、不同尺度），指标全面。
- 消融实验设计合理，验证了VolSA各组件贡献。
- 结果报告了多次实验的平均值（分类任务有标准差），保证了统计可靠性。
- **总体评价**：实验充分、客观、公平。

## 6. 论文的主要结论与发现
- **VolFormer在超分辨率、去噪、分类三个任务上均达到SOTA**，在CAVE数据集×4超分中MPSNR达40.205 dB，优于之前最优0.13 dB。
- **VolSA有效建模三维立方体交互**，相比SSA、CSA及其线性组合，性能显著提升且计算量增量可控。
- **显式光谱位置先验带来稳定收益**，且几乎不增加计算成本。
- **VolSA具有良好的可迁移性**，在分类任务中替换HybridFormer的注意力后，OA提升至97.35%。
- LAM可视化表明VolSA具有最远的交互距离，能利用立方体中更广泛的像素进行重建。

## 7. 优点（方法或实验设计上的亮点）
1. **创新性自注意力设计**：首次将3D立方体交互引入Transformer，通过双二维相似性矩阵隐式建模三维上下文，复杂度从立方降至平方。
2. **光谱位置先验**：针对高光谱连续光谱特性，设计双向衰减矩阵，有效利用波长相关性，且实现简洁。
3. **统一框架**：同一网络架构同时用于超分辨率和去噪，训练时利用辅助RGB数据，增强泛化性。
4. **广泛验证**：在三个不同类型的任务（恢复+分类）上均表现优异，体现了方法的通用性。
5. **低计算开销**：对比SSA+CSA组合，VolSA FLOPs更低（90.15G vs 93.60G），参数更少（5.10M vs 5.24M），性能更优。

## 8. 不足与局限

### 实验覆盖方面
- **算力细节缺失**：未报告GPU数量、训练时间、显存占用，不利于复现和资源评估。
- **分类任务仅验证一个数据集**：HU2013规模中等，未在更大或更复杂的场景（如Indian Pines、Salinas）上测试，通用性证据略显不足。
- **消融实验不够全面**：仅消融了注意力机制和位置先验，未对网络深度、头数、窗口大小等超参数进行系统性研究。
- **未见与其他3D Transformer的对比**：如Spectral-wise Transformer (Cai et al. 2022) 等未在对比列表中。

### 偏差风险方面
- **混合训练策略**：使用RGBI辅助任务，可能引入领域偏差，且未分析辅助数据量大小的影响。
- **光谱位置先验**：假设光谱相关性严格服从双向指数衰减，实际可能更复杂（如非单调或局部高频波动），该先验的鲁棒性未探讨。

### 应用限制方面
- **仅针对高光谱图像**：方法依赖光谱维度，对一般3D数据（如视频、医学图像）的直接迁移性未验证。
- **实时性**：尽管复杂度优化，但VolSA仍涉及两个矩阵乘法，在边缘设备或实时场景下的效率未经评估。
- **超分辨率尺度有限**：仅测试×4和×8，更大尺度（如×16）的性能未知。

（完）

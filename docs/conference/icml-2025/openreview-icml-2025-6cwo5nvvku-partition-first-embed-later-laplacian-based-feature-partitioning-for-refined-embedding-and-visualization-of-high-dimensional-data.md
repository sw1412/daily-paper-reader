---
title: "Partition First, Embed Later: Laplacian-Based Feature Partitioning for Refined Embedding and Visualization of High-Dimensional Data"
title_zh: 先划分后嵌入：基于拉普拉斯的特征划分用于高维数据的精细化嵌入与可视化
authors: "Erez Peterfreund, Ofir Lindenbaum, Yuval Kluger, Boris Landa"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6CwO5nVvku"
tags: ["query:hsi"]
score: 4.0
evidence: 高维数据特征划分方法用于嵌入和可视化
tldr: 该论文针对高维数据存在多个潜在变量导致嵌入失真的问题，提出一种基于图拉普拉斯平滑度的特征划分方法。通过优化将特征划分为互斥子集，每个子集捕捉不同的平滑子结构，从而改进数据可视化和解释性。该方法可应用于高光谱数据的特征提取与降维，但未直接针对遥感任务设计。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1745, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 638, \"height\": 1046, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1605, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 1083, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 721, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 794, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 1251, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1757, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1615, \"height\": 1160, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1712, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1767, \"height\": 1322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1251, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1232, \"height\": 1706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1667, \"height\": 1368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 872, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6cwo5nvvku/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1224, \"height\": 2120, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6cwo5nvvku/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6cwo5nvvku/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1506, \"height\": 652, \"label\": \"Table\"}]"
motivation: 高维数据受多个潜在变量影响，现有嵌入方法可能扭曲关键结构。
method: 提出基于图拉普拉斯平滑度的优化问题，将特征划分为互斥子集各捕捉不同子结构。
result: 在合成和真实数据集上提升了嵌入质量和解释性。
conclusion: 特征划分方法有助于揭示高维数据中的多源结构。
---

## Abstract
Embedding and visualization techniques are essential for analyzing high-dimensional data, but they often struggle with complex data governed by multiple latent variables, potentially distorting key structural characteristics. This paper considers scenarios where the observed features can be partitioned into mutually exclusive subsets, each capturing a different smooth substructure. In such cases, visualizing the data based on each feature partition can better characterize the underlying processes and structures in the data, leading to improved interpretability. To partition the features, we propose solving an optimization problem that promotes graph Laplacian-based smoothness in each partition, thereby prioritizing partitions with simpler geometric structures. Our approach generalizes traditional embedding and visualization techniques, allowing them to learn multiple embeddings simultaneously. We establish that if several independent or partially dependent manifolds are embedded in distinct feature subsets in high-dimensional space, then our framework can reliably identify the correct subsets with theoretical guarantees. Finally, we demonstrate the effectiveness of our approach in extracting multiple low-dimensional structures and partially independent processes from both simulated and real data.

---

## 论文详细总结（自动生成）

# 先划分后嵌入：基于拉普拉斯特征划分的高维数据精细化嵌入与可视化 —— 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：高维数据往往受多个潜在变量（latent variables）共同影响，传统降维/可视化方法（如 tSNE、UMAP、Laplacian Eigenmaps、Diffusion Maps）在构建全局相似图时，容易扭曲数据的复杂多子结构，无法分离不同潜变量的信号。
- **背景**：在许多实际应用中（如高光谱成像、基因组学、天体物理学），不同特征子集对应不同的物理或生物过程，且这些子结构可能部分独立或部分依赖。例如，高光谱图像中不同波长波段捕获不同的化学/物理现象；单细胞RNA-seq中不同基因群对应细胞类型发育和细胞周期进程。
- **目标**：提出一种框架，先将特征划分为互斥子集，每个子集只包含一个较简单的几何子结构，然后基于每个子集单独嵌入/可视化，从而提升解释性并避免全局嵌入的失真。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- **“先划分，后嵌入”**：将原始高维数据的 D 个特征划分为 K 个互斥子集，每个子集构建一个独立的 N×N 相似图，使得每个子图上的数据平滑度（graph smoothness）总和最小。平滑度通过图拉普拉斯得分（Laplacian score）度量，即特征值在图上变化的加权平方和。

### 关键技术细节
- **图平滑度得分**：
  - 定义 `J(W, {yi}) = Σ_{i,j} W_{i,j} ‖y_i - y_j‖²`，其中 W 是高斯核相似矩阵（行归一化，对角为零）。
  - 当数据来自低维流形时，该得分近似等于 `(ϵ/2)·dim(M)` （Proposition 3.2），即得分越小表示几何结构越简单。
- **特征划分优化问题**（Problem 3.3）：
  - 优化变量：K 个二值特征指示向量 `ω^(k) ∈ {0,1}^D`（每个特征只属于一个分区）和 K 个相似矩阵 `W^(k)`。
  - 目标：最小化所有分区上的平滑度之和 `G = Σ_k Σ_{i,j} W^(k)_{i,j} ‖y_i - y_j‖²_{ω^(k)}`。
  - 约束：每个特征总和为1；每行 `W^(k)` 和为1；对角线为0；行熵约束（类似 tSNE 的 perplexity）。
- **解的性质**（Proposition 3.4）：
  - 最优 `W^(k)` 为基于对应特征子集的高斯核（带宽由熵约束确定）；
  - 最优特征分配：每个特征被分配到使该特征在图上的拉普拉斯得分最小的分区。
- **求解算法**（Algorithm 1）：
  - 引入软正则化（熵正则项）避免陷入局部最优；通过逐步降低正则化参数 δ，从均匀软划分逐步收敛到硬划分。
  - 交替更新：固定分区更新图（高斯核）；固定图更新分区（软分配公式，类似 softmax）。

### 理论分析（Section 4）
- 针对一种简化变体（目标函数增加了归一化和正则项），在高维渐近（D, N → ∞，D/log N → ∞）下，推导了损失函数的渐近形式（Theorem 4.3）。
- 证明当 K=2 时，损失函数的最小值对应正确的特征划分（即两个分区完全分离不同的潜流形）（Theorem 4.4），即使在部分依赖（共享潜变量）的情况下也成立。

## 3. 实验设计

### 使用的数据集/场景
1. **合成数据 – 二维椭球体乘积**（Section 5.1）：
   - 独立六个维度：前三个来自一个椭球，后三个来自另一个椭球（独立或共享一个极角）。
   - 目标：将前三个和后三个特征正确分开。
2. **真实生物数据 – 小鼠皮肤 scRNA-seq**（Section 5.2）：
   - N=5572 个细胞，D=5000 个高变基因；两个交织过程：细胞类型发育（LD→UD→DC）和细胞周期（G1/G2M/S）。
   - 目标：将基因划分为两个子集，分别对应这两个过程。
3. **肝小叶 scRNA-seq 数据**（Section 5.3）：
   - N=6889 个细胞，D=2000 个基因，受空间分区（1-8层）和昼夜节律（ZT0，6，12，18）两个潜变量控制。
   - 由于基因同时受两个变量影响，先进行 PCA 变换后再划分子特征。
4. **旋转雕像视频数据**（Appendix D）：
   - 两个摄像头同步拍摄三个不同转速的雕像，水平拼接图像形成 D=9600 像素的样本，N=5000。
   - 隐含三个旋转角度潜变量。目标：将像素划分为三个分区，每个分区对应一个雕像。
5. **COIL-20 子集**（Appendix H）：
   - 三个不同车型的汽车图像，N=216，D=16384 像素，检验特征可分离假设不严格成立时的效果。

### Benchmark 与对比方法
- 特征划分类：k-means（对特征聚类）、谱聚类（对特征）、双聚类（Spectral Co-clustering/Bi-clustering）。
- 嵌入方法：tSNE（全局特征）、UMAP、Diffusion Maps。
- 多嵌入方法：IC-PML（独立坐标选择乘积流形学习）、Multi-tSNE、LDLE（低失真局部特征图）。
- 所有方法均采用定量评估：基于 k-近邻标签一致性误差（k-NN error），衡量嵌入与潜变量的对齐程度。

## 4. 资源与算力

- **文中未明确说明使用了何种 GPU、数量或训练时长。** 只提到了算法复杂度为 O(K N² D)，以及使用低秩 SVD 近似可降至 O(K S² N² + K S² D)（S ≪ N,D）。作者未提供具体硬件信息或运行时间数据。

## 5. 实验数量与充分性

- **实验数量**：共涉及 5 个不同场景（合成椭球、皮肤 scRNA-seq、肝 scRNA-seq、旋转雕像、COIL-20），每个场景均包含多个子实验（如独立/部分依赖、不同特征数、不同可视化方法）。
- **定量对比**：在椭球和雕像实验中，报告了100次随机实验的平均划分误差及标准差；在 scRNA-seq 和雕像实验中，使用 k-NN 误差对多种方法进行了系统性对比，并针对 IC-PML、Multi-tSNE、LDLE 等搜索了超参数（如数十至数百种配置）以选取最优结果，保证了比较的公平性。
- **消融/验证**：包括选择分区数 K 的“肘部法”讨论、使用随机正交变换的排列检验以验证划分必要性（Appendix G）。
- **总体评价**：实验设计较充分，覆盖了独立、部分依赖、非严格分离等多种情况，定量评估客观（使用相同的数据预处理和评价指标）。但未在超大规模数据（如 >10⁶ 样本）上进行测试，计算效率的可扩展性有待验证。

## 6. 主要结论与发现

- 提出的“先划分后嵌入”框架能够有效分解高维数据中的多源子结构，使每个分区的嵌入更清晰、更解释。
- 在合成数据上，该方法准确恢复真实特征划分（误差为0），而传统聚类/双聚类方法误差较大。
- 在 scRNA-seq 数据上，分区1捕获细胞类型发育信号（含已知标记基因 Sox2、Foxd1等），分区2捕获所有86个细胞周期基因，分区嵌入分别展示了两个生物学过程，而全特征嵌入仅显示细胞类型。
- 在肝数据上，经 PCA 变换后，分区1揭示空间分区，分区2揭示昼夜节律循环，比全特征嵌入更清晰。
- 理论分析支持在渐近条件下损失函数的最小与真实特征划分一致。

## 7. 优点

- **理论保证**：提供了在高维渐近和部分依赖情况下的恢复性证明（Theorem 4.3/4.4），这在同类特征划分/多视图学习中较为少见。
- **泛化性**：框架可结合任意基于图的嵌入方法（tSNE、UMAP、扩散映射等），不仅限于特定可视化算法。
- **处理部分依赖**：比乘积流形解耦方法（IC-PML）更灵活，能处理潜变量之间存在部分共享的情况。
- **鲁棒性**：通过熵正则化的逐步退火算法（Algorithm 1）避免硬划分局部最优，实验显示收敛到全局最优。
- **可解释性**：分区结果可直接对应已知语义领域知识（如基因本体、旋转雕像对应关系）。

## 8. 不足与局限

- **K 的选择尚未自动化**：用户需手动指定分区数 K，论文仅提供启发式“肘部法”和经验验证（如 permutation test），缺乏自动确定 K 的方法。
- **计算复杂度高**：直接实现为 O(K N² D)，虽然可利用低秩 SVD 加速，但 N 很大时仍可能昂贵。未报告实际运行时间或可扩展性实验。
- **实验覆盖面有限**：仅在相对较小的数据集（N 数千至数万，D 数千至近万）上测试；未在图像/视频大数据集（如 ImageNet、视频流）或百万级样本上验证。
- **假设局限性**：要求不同子结构对应不同特征子集，且每个子结构内部平滑（低流形维数）。如果特征不可分离（如所有特征均受所有潜变量混合影响），则需要预处理（如 PCA）转换，但转换后可能丢失物理/语义可解释性。
- **缺乏与深度学习方法的对比**：未与基于自编码器或变分推断的分离表示学习方法（如 β-VAE、FactorVAE）进行比较，虽然那些方法通常不直接输出可解释的特征划分。

（完）

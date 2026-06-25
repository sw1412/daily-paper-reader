---
title: A Selective Re-learning Mechanism for Hyperspectral Fusion Imaging
title_zh: 面向高光谱融合成像的选择性再学习机制
authors: "Liu, Yuanye, Liu, Jinyang, Dian, Renwei, Li, Shutao"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Liu_A_Selective_Re-learning_Mechanism_for_Hyperspectral_Fusion_Imaging_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 8.0
evidence: 针对高光谱空间-光谱结构的选择性再学习机制，与光谱-空间特征提取紧密相关
tldr: 该文针对高光谱融合成像计算成本高的问题，发现平滑区域可用浅层网络重建而复杂区域需深层网络，提出选择性再学习融合网络。方法先初步融合，再选择性细化失真特征点，在保持性能的同时显著降低计算量，为高光谱融合提供了自适应计算的有效方案。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1784, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1707, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1706, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1708, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1790, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1792, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1785, \"height\": 255, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 822, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1700, \"height\": 610, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1810, \"height\": 477, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1809, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 876, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-liu-a-selective-re-learning-mechanism-for-hyperspectral-fusion-imaging-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 880, \"height\": 235, \"label\": \"Table\"}]"
motivation: 现有方法对所有像素统一处理，忽视空间-光谱结构差异导致冗余。
method: 初步融合后检测失真特征点并选择性深度再学习。
result: 在保持性能的同时显著降低计算量。
conclusion: 为高光谱融合提供了自适应计算的有效方案。
---

## Abstract
Hyperspectral fusion imaging is challenged by high computational cost due to the abundant spectral information. We find that pixels in regions with smooth spatial-spectral structure can be reconstructed well using a shallow network, while only those in regions with complex spatial-spectral structure require a deeper network. However, existing methods process all pixels uniformly, which ignores this property. To leverage this property, we propose a Selective Re-learning Fusion Network (SRLF) that initially extracts features from all pixels uniformly and then selectively refines distorted feature points. Specifically, SRLF first employs a Preliminary Fusion Module with robust global modeling capability to generate a preliminary fusion feature. Afterward, it applies a Selective Re-learning Module to focus on improving distorted feature points in the preliminary fusion feature. To achieve targeted learning, we present a novel Spatial-Spectral Structure-Guided Selective Re-learning Mechanism (SSG-SRL) that integrates the observation model to identify the feature points with spatial or spectral distortions. Only these distorted points are sent to the corresponding re-learning blocks, reducing both computational cost and the risk of overfitting. Finally, we develop an SRLF-Net, composed of multiple cascaded SRLFs, which surpasses multiple state-of-the-art methods on several datasets with minimal computational cost.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：高光谱融合成像（融合低分辨率高光谱图像LRHSI与多光谱图像MSI得到高分辨率高光谱图像HRHSI）因丰富的谱段信息导致计算成本极高。现有深度学习方法（CNN、Transformer）对所有像素统一处理，忽视了一个重要特性：**空间-光谱结构平滑的区域可用浅层网络充分重建，而只有结构复杂的区域才需要深层网络**。
- **背景**：传统方法（矩阵分解、张量分解）非线性能力有限；深度学习虽然性能优越，但存在计算量与融合精度的权衡——CNN计算量低但精度有限，Transformer精度高但计算量巨大。近期轻量级框架尝试对图像区域分类后差异化处理，但应用于高光谱图像时会破坏空间位置关系且计算开销大。
- **整体含义**：本文旨在利用空间-光谱结构的差异性，设计一种**自适应计算分配**的融合网络，在保证高精度的同时最小化计算量，为卫星或紧凑相机等边缘设备部署提供可能。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：先对所有像素进行**初步融合**（用较浅的网络提取全局特征），再**选择性**地只对初步融合特征中发生**畸变的特征点**（空间畸变或光谱畸变）进行**深度再学习**，从而避免对已良好重建区域的冗余计算，降低过拟合风险。
- **网络框架（SRLF-Net）**：
  - **嵌入层**：拼接输入的MSI和LRHSI，调整通道数得到\(F_0\)。
  - **N个级联的SRLF模块**：每个SRLF包含：
    - **初步融合模块**：基于多尺度Mamba（SS2D块）提取全局信息。采用下采样-上采样结构，形成多尺度感受野，增强全局感知能力（图3(c)有效感受野显著增大）。输出初步融合特征\(Z'\)。
    - **选择性再学习模块**：
      - **空间再学习块（Spa-RL）**：利用观测模型中的**光谱响应函数**\(R\)将\(Z'\)降质为伪MSI \(Y'\)，计算\(Y'\)与真实MSI \(Y\)之间的**SSIM图**，据此选出SSIM得分最低的\(r\)比例像素（空间畸变点），输入Spectral Transformer进行再学习。
      - **光谱再学习块（Spe-RL）**：将Spa-RL输出再通过**空间退化模型**（高斯模糊+下采样）降质为伪LRHSI \(X'\)，计算\(X'\)与真实LRHSI \(X\)之间的**SAM图**，选出SAM得分最高的\(r\)比例像素（光谱畸变点），同样用Spectral Transformer再学习。
      - **再融合块（RF）**：一个SS2D块，融合空间与光谱再学习的结果。
    - **畸变点比例自适应计算**：\(r = \lambda (1 - \text{Avg}(M_{\text{spa}}))\)，\(\lambda\)为超参数（实验中设置为0.1～0.3最优）。
  - **精炼层**：将所有级联SRLF的输出与\(F_0\)拼接后通过卷积得到最终HRHSI。
- **关键技术细节**：
  - **SSG-SRL机制**：无需直接对比特征与真实HRHSI（未知），而是利用已知的观测模型生成伪图像，通过SSIM和SAM从**空间和光谱两个维度**自动识别畸变点。
  - **Mamba与Transformer混合**：初步融合使用线性复杂度的Mamba（全局感知），再学习使用Spectral Transformer（局部精细修复），兼顾效率与精度。
  - **公式示例**（文字说明）：式(3)-(6)描述空间畸变点识别与再学习流程；式(7)-(9)描述光谱畸变点识别与再学习流程。

### 3. 实验设计
- **数据集**：
  - **模拟数据**：CAVE（31波段，512×512）和Harvard（31波段，原始图像经空间/光谱降质得到LRHSI和MSI作为输入，原始图像作为GT）。
  - **真实数据**：Gaofen5卫星数据（无GT，使用无参考指标QNR评价）。
- **Benchmark**：模拟数据采用PSNR、SAM、UIQI、SSIM；真实数据采用QNR。
- **对比方法**：
  - 传统方法：Hysure、NSSR。
  - 深度学习方法：DAEM、FusionMamba、DHIF-Net、DSPNet、MIMO-SST、Mog-DCN、LRTN。
- **实验设置**：按照常规高光谱融合设置进行空间/光谱降质，训练/测试划分，代码公开（GitHub）。

### 4. 资源与算力
- **论文明确提及的信息**：
  - 计算量：SRLF-Net的FLOPs仅81.22G（表1），参数量1.33M；SSG-SRL机制每次仅需<0.11 GFLOPs。
  - 但**未明确说明**训练所用的**GPU型号、数量、训练时长**。仅在附录或正文中未提及，这是本文的一个信息缺口。

### 5. 实验数量与充分性
- **实验数量**：
  - 2个模拟数据集（CAVE、Harvard）+ 1个真实数据集（Gaofen5）。
  - 消融实验：网络深度N（1~5）、初步融合模块的多尺度结构、SSG-SRL机制（有无选择）、先验\(R\)和\(C\)已知/未知、比例系数\(\lambda\)（0~1调参）。
  - 可视化分析：伪彩色图、光谱角度误差图、畸变点位置热力图。
- **充分性与公平性**：
  - 对比方法覆盖了传统和各类最新深度方法，评价指标全面（4个指标+无参考）。
  - 消融实验逐一验证各模块有效性，且报告了对应FLOPs变化，论证充分。
  - 在真实数据上使用无参考指标QNR，避免人为GT偏差。
  - 交换响应函数未知时的实验显示仍接近最优，鲁棒性较好。

### 6. 主要结论与发现
- 提出SRLF-Net，通过**选择性再学习**机制，在CAVE上PSNR达49.39 dB（比Mog-DCN高0.8 dB），Harvard上47.90 dB（与最优持平），而FLOPs仅81.22 G（约为Mog-DCN的1/54），参数量1.33 M。
- **空间畸变点主要位于纹理复杂区域**（如边缘、细节），光谱畸变点则随阶段变化（初期关注整体光谱漂移，后期关注局部异常）。
- 比例系数\(\lambda\)在0.1~0.3时性能稳定，FLOPs线性增长；\(\lambda>0.3\)后SAM开始波动。
- 当观测模型先验未知时（用可学习参数替代），仍能达到PSNR 49.34 dB，说明网络具有较强的适应能力。

### 7. 优点
- **高效性**：通过自适应计算分配，大幅降低计算量与参数量（比同类SOTA方法降低1~2个数量级），适合资源受限场景。
- **创新性**：首次将“选择性再学习”思想引入高光谱融合，利用观测模型自动区分畸变区域，避免手工设计或分类器。
- **结构设计合理**：Mamba负责全局初步融合，Transformer负责局部精确修复，优势互补；多尺度Mamba有效增强感受野。
- **可解释性强**：通过可视化畸变点位置，可直观理解网络关注的重点区域，便于调试和部署。
- **代码开源**：提升可复现性。

### 8. 不足与局限
- **超参数依赖**：畸变比例\(r\)依赖于\(\lambda\)，虽然\(\lambda\)在0.1~0.3范围稳定，但在复杂真实场景下是否需要额外调优未深入讨论。
- **泛化性验证有限**：仅测试了固定退化模型（光谱响应函数和空间模糊核已知），对于未知或动态退化模型（如真实传感器差异）的鲁棒性仅做了一组“先验未知”实验，但未在更多真实退化场景中评估。
- **训练细节缺失**：未报告GPU型号、训练时长、批量大小等，降低复现便利性，也影响对计算效率的全面评估。
- **对比方法计算量统计**：表1中部分方法的FLOPs未统一（如DHIF-Net标为3.616T但指明“per fine-tuning”），造成公平性略带模糊。
- **实时性未讨论**：虽然FLOPs低，但实际推理速度（FPS）未给出，无法直接判断是否满足实时需求。

（完）

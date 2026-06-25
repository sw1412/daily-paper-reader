---
title: "SSIF: Physics-Inspired Implicit Representations for Spatial-Spectral Image Super-Resolution"
title_zh: "SSIF: 物理启发的空间-光谱图像超分辨率隐式表示"
authors: "Gengchen Mai, Zeping Liu, Ni Lao, Weiwei Sun, Yuchi Ma, Jiaming Song, Chenlin Meng, Hongxu Ma, Jinmeng Rao, Qian Cao, Nemin Wu, Zhangyu Wang, Stefano Ermon"
date: 2024-09-16
pdf: "https://openreview.net/pdf?id=zrNbsV87Os"
tags: ["query:hsi"]
score: 6.0
evidence: 空间-光谱隐式函数用于超分辨率，与光谱-空间特征提取相关
tldr: 针对现有空间隐式函数无法处理连续光谱分辨率的问题，本文提出空间-光谱隐式函数（SSIF），将图像表示为空间坐标和光谱波长的连续函数，可实现任意空间和光谱分辨率的超分辨率重建。该方法为光谱-空间特征提取提供了新的连续表示范式。
source: ICLR-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1462, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1460, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1110, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1404, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 950, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1467, \"height\": 830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1464, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 1038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1382, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1385, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1139, \"height\": 1136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1296, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1010, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1172, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1173, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1452, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1170, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1161, \"height\": 943, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1173, \"height\": 981, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1161, \"height\": 1060, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-zrnbsv87os/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1150, \"height\": 981, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-iclr-2025-zrnbsv87os/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 865, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-zrnbsv87os/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 871, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-zrnbsv87os/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1459, \"height\": 608, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-zrnbsv87os/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 811, \"height\": 118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-zrnbsv87os/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1306, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-zrnbsv87os/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-zrnbsv87os/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1307, \"height\": 453, \"label\": \"Table\"}]"
motivation: 现有传感器固定空间和光谱分辨率，超分辨率模型需针对不同设置单独训练。
method: 提出空间-光谱隐式函数，将图像表示为连续空间坐标和光谱波长的函数。
result: 实现了任意空间和光谱分辨率的超分辨率重建。
conclusion: 为光谱-空间特征提取提供了连续表示方法，具有通用性。
---

## Abstract
Existing digital sensors capture images at fixed spatial and spectral resolutions (e.g., RGB, multispectral, and hyperspectral images), and generating super-resolution images with different resolution settings requires bespoke machine learning models. Spatial Implicit Functions (SIFs) partially overcome the spatial resolution challenge by representing an image in a spatial-resolution-independent way. However, they
still operate at fixed, pre-defined spectral resolutions. To address this challenge, we propose Spatial-Spectral Implicit Function (SSIF), a neural implicit model that represents an image as a function of both continuous pixel coordinates in the spatial domain and continuous wavelengths in the spectral domain. This continuous representation across spatial and spectral domains enables a single model to learn from a diverse set of resolution settings, which leads to better generalizability. This representation also allows the physical principle of spectral imaging and the spectral response functions of sensors to be easily incorporated during training and inference. Moreover, SSIF does not have the equal spectral wavelength interval requirement for both input and output images which leads to much better applicability. We empirically demonstrate the effectiveness of SSIF on two challenging spatial-spectral super-resolution benchmarks. We observe that SSIF consistently outperforms state-of-the-art baselines even when the baselines are allowed to train separate models at each spatial or spectral resolution. We show that SSIF generalizes well to both unseen spatial and spectral resolutions. Moreover, due to its physics-inspired design, SSIF performs significantly better at low data regime and converges faster during training compared with other strong neural implicit function-based baselines.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有数字传感器（如RGB、多光谱、高光谱相机）固定空间和光谱分辨率，导致超分辨率（SR）模型需要为每对输入-输出分辨率单独训练，缺乏泛化能力。空间隐式函数（SIF）解决了空间分辨率任意缩放问题，但光谱分辨率仍然固定，且现有方法（如LISSF）要求输入波段等间隔，不适用于多数RGB/多光谱图像。
- **研究动机**：设计一个单一模型，能同时处理任意空间和光谱分辨率的超分辨率任务（空间SR、光谱SR、空间-光谱SR），并整合传感器物理成像原理以提高泛化性、数据效率和训练效率。

## 2. 论文提出的方法论
### 2.1 核心思想
- **SSIF（Spatial-Spectral Implicit Function）**：将图像表示为关于连续像素坐标 \(x\) 和连续波长 \(\lambda\) 的连续函数 \(\gamma_I(x, \lambda)\)。通过积分传感器响应函数 \(\rho_i(\lambda)\) 与辐射函数 \(\gamma_I\) 来预测每个波段的值，从而统一处理任意空间和光谱分辨率。

### 2.2 关键技术细节
- **物理原理**：
  - **传感器侧**：像素值 \(s_{x,i} = \int_{\Lambda_i} \rho_i(\lambda) \gamma_I(x, \lambda) d\lambda\)，近似为加权和：\(s_{x,i} = \sum_{k=1}^K \rho_i(\lambda_{i,k}) \gamma_I(x, \lambda_{i,k})\)。
  - **光源侧**：辐射函数可分解为预训练光谱签名函数的加权和（光谱签名先验）。
- **模型架构**（图2b）：
  - 图像编码器 \(E_I\)（如SwinIR）提取2D特征图。
  - 像素特征解码器 \(F_x\)（如CiaoSR）根据坐标 \(x\) 输出像素隐特征 \(h_x\)。
  - 光谱编码器 \(E_\lambda\)（带傅里叶特征映射的MLP）将波长 \(\lambda\) 编码为光谱嵌入 \(b\)。
  - 光谱解码器 \(D_{x,\lambda}\)（采用点积操作）融合 \(h_x\) 和 \(b\) 得到辐射值。
  - 响应函数 \(\rho_i(\lambda)\) 预定义为高斯或均匀分布，采样 \(K\) 个波长进行积分近似。
- **训练过程**：在空间域随机采样尺度 \(p \sim U(p_{\min}, p_{\max})\)，在光谱域随机采样波段数 \(C \sim U(C_{\min}, C_{\max})\)，使模型同时学习多种分辨率。

## 3. 实验设计
### 3.1 数据集
- **CAVE**：32张室内高光谱图像，512×512像素，31个波段（400–700 nm）。训练/测试划分：22/10。
- **Pavia Centre**：遥感高光谱图像，1095×715像素，102个波段（430–860 nm）。训练/测试划分：除左上1024×128区域外为训练集。

### 3.2 Baseline 方法
- **10个对比方法**：RCAN+AWAN、AWAN+RCAN、AWAN+SSPSR、RC/AW+MoG-DCN、SSJSR、US3RN、SSFIN、LIIF、CiaoSR、LISSF（修改为SwinIR编码器以处理不等间隔波段）。其中前7个需为每种分辨率单独训练模型。
- **额外光谱SR对比**：HDNet、MST++、SSRNet。

### 3.3 评估指标
- PSNR、SSIM、SAM（光谱角映射）。

## 4. 资源与算力
- 文中提及：Linux服务器，4块24GB显存的CUDA GPU。未说明具体GPU型号（如V100/RTX 3090），也未给出总训练时长。消融实验和最终模型基于该配置完成。

## 5. 实验数量与充分性
- **实验数量充足**：覆盖空间SR（p=2,4,8,10,12,14,16等）、光谱SR（不同C值）、空间-光谱SR（联合变化），以及在分布内/外（unseen）分辨率上的测试。
- **消融实验充分**：
  - 图像编码器（EDSR、RDN、SwinIR）和像素解码器（LIIF、CiaoSR）的组合。
  - 光谱解码器（点积、MLP拼接、自注意力）。
  - 采样波长数 \(K\) 的影响。
  - 数据效率（25%/50%/75%训练数据）和训练效率（损失收敛曲线）。
  - 不同 \(C_{\min}\) 设置、截断波段泛化实验。
- **公平性**：
  - 所有基线使用官方代码，SSIF与CiaoSR使用相同骨干网（SwinIR+CiaoSR）进行公平对比。
  - 基线允许单独训练（更容易的任务），SSIF仍全面胜出。
- 不足之处：CAVE数据集仅32张图像，规模较小；Pavia Centre仅一个场景切片。

## 6. 论文的主要结论与发现
- **SSIF在所有空间/光谱尺度上一致优于所有基线**，甚至当基线为每种分辨率单独训练时。
- **SSIF对未见过的空间和光谱分辨率展现强泛化能力**（如p=10~14、C>31或C>102）。
- **物理启发的设计带来三大优势**：
  - 数据效率：在25%训练数据下PSNR提升≥3.14 dB。
  - 训练效率：前50个epoch损失下降更快。
  - 参数效率：仅比CiaoSR多0.3M参数，但一个模型替代多个。
- **光谱编码器学到类似分段线性或连续基函数的表示**，可解释性强。

## 7. 优点（方法或实验设计亮点）
- **统一框架**：单一模型解决空间SR、光谱SR、空间-光谱SR三类任务，无需重新训练。
- **无等间隔假设**：输入/输出光谱可任意间隔，适用于真实RGB/多光谱传感器。
- **物理先验嵌入**：利用传感器响应函数和光谱签名分解，提升泛化与低数据性能。
- **实验设计严谨**：全面对比、消融、分布内外测试、统计显著性（3次随机种子误差条）。
- **定性可视化丰富**：提供误差图、光谱曲线重建对比，直观证明优势。

## 8. 不足与局限
- **数据规模限制**：CAVE仅32张图像，Pavia Centre仅一个场景；依赖小数据集，模型规模受约束。
- **光谱响应函数假设**：假设为高斯/均匀分布，对于复杂传感器（如大气吸收）可能不够精确（作者承认可通过学习方式扩展）。
- **未验证多光谱输入非等间隔情况**：论文主要在高光谱数据集上实验，未直接在真实非等间隔多光谱图像上测试。
- **潜在Deepfake风险**：作者提及需在下游任务（语义分割等）进行整体评估，但目前未开展。
- **计算复杂度**：尽管参数量与CiaoSR相当，但FLOPS略高（717G vs 636.5G）。
- **未报告训练时长**：GPU型号和训练耗时缺失，影响可复现性评估。

（完）

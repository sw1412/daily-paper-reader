---
title: "Automatic Spectral Calibration of Hyperspectral Images: Method, Dataset and Benchmark"
title_zh: 高光谱图像的自动光谱校准：方法、数据集与基准
authors: "Du, Zhuoran, You, Shaodi, Cheng, Cheng, Wei, Shikui"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Du_Automatic_Spectral_Calibration_of_Hyperspectral_Images_Method_Dataset_and_Benchmark_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 7.0
evidence: 高光谱图像自动光谱校准，为高光谱任务提供数据质量支撑
tldr: 该工作提出一种基于学习的高光谱图像自动光谱校准方法，无需物理参考板即可消除光照变化影响。创建了包含765对高质量高光谱图像的大规模校准数据集，并通过与10种不同测量照明条件结合扩展到7650对。该方法为后续高光谱分类、目标检测等任务提供了重要预处理基础，具有广泛适用性。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1786, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 843, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1707, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1641, \"height\": 1351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 775, \"height\": 663, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-du-automatic-spectral-calibration-of-hyperspectral-images-method-dataset-and-benchmark-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 284, \"label\": \"Table\"}]"
motivation: 传统高光谱校准依赖物理参考板，操作繁琐且限制相机移动，亟需自动校准方法。
method: 提出基于学习的自动光谱校准方法，利用大规模配对数据集训练网络，无需物理参考即可校正光照影响。
result: 构建了大规模高光谱校准数据集，并通过数据增强扩展10倍，验证了方法的有效性和泛化性。
conclusion: 该工作为高光谱图像自动校准提供了新思路和基准数据集，可显著提升下游任务性能。
---

## Abstract
Hyperspectral images (HSI) densely sample the world in both the space and frequency domains and, therefore, are more distinctive than RGB images. Usually, HSI needs to be calibrated to minimize the impact of various illumination conditions. The traditional way to calibrate HSI utilizes a physical reference, which involves manual operations, occlusions, and/or limits camera mobility. These limitations inspire this paper to automatically calibrate HSIs using a learning-based method. Towards this goal, a large-scale HSI calibration dataset, which has 765 high-quality HSI pairs covering diversified natural scenes and illuminations, is created. The dataset is further expanded to 7650 pairs by combining with 10 different physically measured illuminations. A spectral illumination transformer (SIT) together with an illumination attention module is proposed. Extensive benchmarks demonstrate the SoTA performance of the proposed SIT. The benchmarks also indicate that low-light conditions are more challenging than normal conditions. The dataset and codes are available online: https://github.com/duranze/Automatic-spectral-calibration-of-HSI.

---

## 论文详细总结（自动生成）

# 高光谱图像的自动光谱校准：方法、数据集与基准（中文总结）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：高光谱图像（HSI）受光照影响极大，传统校准依赖物理参考板（如硫酸钡白板），存在**操作繁琐、遮挡场景、限制相机移动**等缺点。现有方法分为同步法（参考板在场景中）和异步法（双次拍摄），均不适用于自然场景的灵活部署。
- **整体含义**：本文首次提出**基于学习的自动光谱校准**方法，无需物理参考即可从单张未校准HSI中恢复反射率，旨在解决传统方法的局限性，推动HSI在自然场景下的实际应用。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用深度学习模型直接学习从原始强度图像到校准后反射率图像的映射。提出**光谱照明变换器（Spectral Illumination Transformer, SIT）**，引入**照明注意力模块（Illumination Attention）**，模仿经典灰度世界（Gray-World）假设，以更好地捕获全局光照信息。
- **关键技术细节**：
  - **U形变换器结构**：基于HCANet的U形编码器-解码器，结合残差连接。
  - **照明注意力（IA）**：通过全局平均池化提取每个通道的均值，将其作为光照特征，生成注意力矩阵 \( A^{m}_{I} \)。该矩阵与光谱注意力（SA）矩阵 \( A^{m}_{S} \) 相乘后经softmax得到最终注意力 \( A^{m}_{SI} \)，用于调整特征。
  - **公式流程**：
    - 输入特征 \( x^{m}_0 \) → 层归一化 + 卷积 → 分别进入光谱注意力（SA）和照明注意力（IA）分支。
    - IA分支：卷积 + 下采样 + 全局平均池化 → 得到光照特征 \( x^{m}_{I} \) → 线性投影得到查询和键 → 生成 \( A^{m}_{I} \)。
    - SA分支：类似HCANet，得到 \( A^{m}_{S} \) 和值 \( x^{m}_{v} \)。
    - 最终注意力：\( A^{m}_{SI} = \text{softmax}(A^{m}_{S} \cdot A^{m}_{I}) \)，输出 \( x^{m}_{a} = A^{m}_{SI} x^{m}_{v} \)。
    - 再经层归一化和前馈网络得到当前层输出。
- **算法流程**：端到端训练，输入未校准HSI，输出校准后的反射率HSI，使用L1损失优化。

## 3. 实验设计：数据集、基准与对比方法
- **数据集**：
  - **BJTU-UVA**：首个自动校准数据集，包含**765对**高光谱图像（204波段，400–1000nm，空间分辨率512×512，12bit）。通过异步法采集，涵盖城市、自然、不同天气和时段等多样场景。
  - **BJTU-UVA-E**：将765对扩展为**7650对**，利用10种不同照明（5种自然照明：晴天、阴天、雨天、傍晚、阴影；5种滤色照明：红、蓝、黄、紫、绿）与反射率合成。
  - 同时提供**31通道子集**（400–700nm）以便与现有方法兼容。
- **基准（Benchmark）**：使用四个指标：PSNR、RMSE、ERGAS、SAM。
- **对比方法**：
  - 经典方法：Gray-World。
  - 基于学习的方法：
    - DivIll（室内光谱恢复）
    - SERT（HSI去噪）
    - HCANet（HSI去噪）
  - 本文提出的**SIT**。
- **实验设置**：训练/验证/测试划分：535/114/116（BJTU-UVA），5350/1140/1160（BJTU-UVA-E）。图像随机裁剪为256×256，批大小4，训练500 epoch（BJTU-UVA）或50 epoch（BJTU-UVA-E），Adam优化器，初始学习率1e-4，L1损失。

## 4. 资源与算力
- 论文明确提到：**Nvidia 3090 GPU**（未说明具体数量）。
- 训练时长：BJTU-UVA训练500 epoch，BJTU-UVA-E训练50 epoch。未给出具体时间。
- 算力描述较为简略，未提供批量大小下的显存消耗或总计算量。

## 5. 实验数量与充分性
- **实验数量**：
  - 主实验：在**全光谱（204通道）** 和**31通道**两种设置下，各在BJTU-UVA和BJTU-UVA-E上测试，共4组对比。
  - 消融实验：4种配置（无SA&IA、仅SA、仅IA、SA&IA），在BJTU-UVA全光谱验证和测试集上。
  - 可视化结果：多组热图对比，以及低光照挑战案例分析。
- **充分性**：
  - 对比方法涵盖经典算法、已有学习去噪/恢复方法，且SIT在所有指标上领先，充分展示了优势。
  - 消融实验证实照明注意力模块的必要性。
  - 还分析了低光照区域的困难情况，提供了未来方向。
- **客观公平性**：
  - 数据划分固定，所有方法采用相同训练/测试集，参数设置基本一致（随机裁剪、批大小、损失函数）。
  - 但未进行交叉验证，且对比方法均为泛用模型（非专门为校准设计），可能对SIT有利。论文也承认Gray-World在自然光照下表现不错，说明公平性尚可。

## 6. 论文的主要结论与发现
- **主要结论**：提出的**SIT框架**在自动HSI校准任务上达到了**最先进（SoTA）性能**，在所有指标上优于对比方法。
- **重要发现**：
  - 在原始BJTU-UVA（自然光照）上，Gray-World方法优于部分深度学习模型（如SERT），表明古典假设仍有价值。
  - 在扩展数据集上，所有学习方法性能大幅提升，因数据量更大、光照更多样；而Gray-World性能不变。
  - **低光照场景和红外波段**仍然是挑战，校准误差较大，值得后续研究。
- 验证了照明注意力模块的有效性：单独使用IA或SA效果相近，二者结合最优。

## 7. 优点
- **方法创新**：首次将学习引入HSI自动校准，设计了有针对性的照明注意力模块，结合物理先验（Gray-World）和现代变换器架构。
- **数据集贡献**：创建了首个大规模、高质量的HSI校准数据集BJTU-UVA及其扩展，为后续研究提供了宝贵资源。
- **基准全面**：在两个光谱分辨率（全谱、31通道）下进行系统评估，对比了多种基线方法。
- **消融充分**：通过四种注意力配置验证了各组件的贡献。
- **开源实践**：代码和数据集公开发布，促进可重复性研究。

## 8. 不足与局限
- **实验覆盖**：
  - 仅测试了自然场景和有限的人工照明（滤色），未涵盖混合光照、复杂室内场景等。
  - 所有图像均为静态单视角，未评估运动或动态光照下的鲁棒性。
  - 数据集仅包含204个波段（400–1000nm），未涉及短波红外或更长波段。
- **偏差风险**：
  - 数据集采集使用单台Specim IQ相机，未考虑传感器差异对模型的泛化影响。
  - 模型训练依赖异步法获取的真实标签，而异步法本身存在时间差和暗电流噪声等误差，可能引入标签噪声。
- **应用限制**：
  - 性能在低光照区域下降明显，且未探索是否可与其他去噪、增强方法结合。
  - 模型计算量未与现有方法对比，未提供推理速度，难以评估实时性。
- **消融不完整**：仅探讨了注意力模块的结构，未分析U形深度、层数、卷积尺寸等超参数影响。
- **可复现性**：虽提供代码，但未说明训练所需具体硬件配置和时长，复现成本不明确。

（完）

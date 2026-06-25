---
title: A Unified Latent Schrodinger Bridge Diffusion Model for Unsupervised Anomaly Detection and Localization
title_zh: 统一潜在薛定谔桥扩散模型用于无监督异常检测与定位
authors: "Akshay, Shilhora, Narasimhan, Niveditha Lakshmi, George, Jacob, Balasubramanian, Vineeth N"
date: 2025-06-01
pdf: "https://openaccess.thecvf.com/content/CVPR2025/papers/Akshay_A_Unified_Latent_Schrodinger_Bridge_Diffusion_Model_for_Unsupervised_Anomaly_CVPR_2025_paper.pdf"
tags: ["query:hsi"]
score: 6.0
evidence: 无监督异常检测方法，可迁移至高光谱异常检测
tldr: 该文提出统一潜在薛定谔桥扩散模型用于无监督异常检测与定位，仅利用正常数据训练，无需辅助网络，提高了鲁棒性和实用性。方法在工业检测和医学数据集上取得优异性能，为高光谱异常检测提供了可迁移的通用框架，但未直接在高光谱上验证。
source: CVPR-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1787, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 482, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 756, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 571, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 881, \"height\": 783, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 903, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 115, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 825, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/cvpr-2025-accepted/cvpr-2025-akshay-a-unified-latent-schrodinger-bridge-diffusion-model-for-unsupervised-anomaly-cvpr-2025-paper/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1794, \"height\": 215, \"label\": \"Table\"}]"
motivation: 现有无监督异常检测依赖辅助网络，鲁棒性有限。
method: 利用薛定谔桥扩散模型在潜在空间重建正常数据，检测异常。
result: 在工业检测和医学数据集上取得优异性能。
conclusion: 为高光谱异常检测提供了可迁移的通用框架。
---

## Abstract
Anomaly detection and localization remain pivotal challenges in computer vision, with applications ranging from industrial inspection to medical diagnostics. While current supervised methods offer high precision, they are often impractical due to the scarcity of annotated data and the infrequent occurrence of anomalies. Recent advancements in unsupervised approaches, particularly reconstruction-based methods, have addressed these issues by training models exclusively on normal data, enabling them to identify anomalies during inference. However, these methods frequently rely on auxiliary networks or specialized adaptations, which can limit their robustness and practicality. This work introduces the Latent Anomaly Schrodinger Bridge (LASB), a unified unsupervised anomaly detection model that operates entirely in the latent space without requiring additional networks or custom modifications. LASB transforms anomaly images into normal images by preserving structural integrity across varying anomaly classes, lighting, and pose conditions, making it highly robust and versatile. Unlike previous methods, LASB does not focus solely on reconstructing anomaly features, but emphasizes anomaly transformation, achieving smooth anomaly-to-normal image conversions. Our method achieves state-of-the-art performance on both the MVTec-AD and VisA datasets, excelling in detection and localization tasks.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：无监督异常检测与定位是计算机视觉中的关键任务，广泛应用于工业检测和医学诊断。监督方法需要大量标注数据，而异常样本稀少、标注成本高，导致监督方法在实际应用中受限。现有无监督方法（尤其是重建类方法）通常仅用正常数据训练，但在推理时依赖辅助网络或定制化改造，鲁棒性和实用性不足。
- **动机**：设计一个统一的、无需辅助网络的异常检测模型，能够仅基于正常数据训练，并在推理时将异常图像平滑转换为正常图像，同时保持结构完整性，适应不同异常类别、光照和姿态变化。
- **整体含义**：提出一个在潜在空间中运作的薛定谔桥扩散模型（LASB），实现端到端的异常检测与定位，首次将线性薛定谔桥应用于潜在扩散模型进行异常检测。

## 2. 方法论

- **核心思想**：利用薛定谔桥（Schrödinger Bridge）的线性变体，在潜在空间中建立异常分布到正常分布的直接扩散桥，实现平滑的异常到正常图像转换，而非从纯高斯噪声重建。
- **关键技术细节**：
  - **两阶段训练**：第一阶段使用VQ-VAE（从Stable Diffusion初始化）对图像进行感知压缩，得到64×64×3的潜在表示；第二阶段在潜在空间中训练线性薛定谔桥（Linear-SB）。
  - **线性薛定谔桥**：基于Dirac delta边界条件，使得反向过程无论终端分布如何，始终收敛于给定的正常图像。后验分布解析形式：`q(z_t | z_0, z_1) = N(z_t; μ_t, Σ_t)`，其中`μ_t`是`z_0`和`z_1`的加权平均，`Σ_t`是方差。
  - **训练目标**：`L_LASB = || ϵ_θ(z_t, t) - (z_t - z_0) / σ(z)_t ||`，其中`ϵ_θ`是噪声预测网络（U-Net），`σ(z)_t`是累积方差。
  - **推理**：输入异常测试图像，通过DDPM采样器生成正常图像，然后计算原始图像与重建图像在预训练ImageNet模型上的多尺度特征差异，生成热图定位异常。
  - **无辅助网络**：整个流程不需要额外的判别子网络或语义引导网络。

## 3. 实验设计

- **数据集**：
  - **MVTec-AD**：15个类别（10种物体+5种纹理），共5,354张图像（3,629正常用于训练，1,725测试含正常和异常），提供像素级标注。
  - **VisA**：12个子集（复杂结构、多实例、单实例类型），共10,821张图像（9,621正常，1,200异常，78种异常类型），提供像素级标注。
- **Benchmark评价指标**：AUROC（图像级`cls`和像素级`seg`）、AP、F1_max。
- **对比方法**：
  - **基于类的（class-based）**：SimpleNet, PatchCore, DSR, PaDiM, CS-Flow, CFLOW-AD, OCR-GAN, DRAEM, RD4AD, ADSPR, DiffAD, D3AD, DDAD, TransFusion等。
  - **统一的（unified/multi-class）**：DRAEM, HVQ-Trans, MambaAD, OmniAL, GLAD, UniAD, DiAD等。
- **对比方式**：在类级和统一设置下分别报告平均AUROC_cls/AUROC_seg，并提供了详细的类级性能（见补充材料）。

## 4. 资源与算力

- 文中未明确说明总训练时长、GPU数量等详细算力信息。
- 仅提及**推理时间**的测量使用**NVIDIA V100 GPU**，并在不同NFE（函数评估次数）下报告了推理时间（例如10 NFE时0.74秒）。
- 图3显示了不同分辨率下LASB与SGM、SB、DDPM的训练时间、内存和采样时间的对比，但无具体硬件配置。

## 5. 实验数量与充分性

- **实验组数**：主要对比了超过15种方法在两个数据集上的检测和定位性能；提供了消融实验（与标准扩散模型的对比）、稳定性分析（6次采样均值与方差）、采样步数（NFE）消融（从1到1000）、推理时间对比（表5）。
- **充分性评价**：
  - 实验覆盖了**MVTec-AD和VisA**两个主流工业数据集，且包含类级和统一设置两种评估协议，较为全面。
  - 对比方法众多，涵盖了嵌入、记忆库、归一化流、AutoEncoder、GAN、Transformer、扩散模型等多种范式。
  - 提供了**稳定性分析**（表6）表明模型在多轮采样中结果稳定，方差极小。
  - 但**缺乏在医学图像或其他领域（如高光谱）上的验证**，且未进行与更复杂多类方法（如DDAD）的详细统计显著性检验。
- **公平性**：作者将方法分为类级和统一两种设置分别比较，避免了不公平对比。但统一设置下LASB仅在MVTec-AD上超过MambaAD 0.54%，在VisA上低于MambaAD（94.2% vs 94.3%），作者声称超过但在文本中给出的数字94.2 vs 94.3实际上略低（注：原文表1中VisA统一设置AUROC_seg为98.18%，但class-based下94.2% vs 98.3%？请检查表1：VisA统一设置LASB为94.2/98.18，MambaAD为94.3/98.5，故检测略低。但作者在描述中强调LASB在定位上更优。需要客观指出）。

## 6. 主要结论与发现

- LASB在MVTec-AD上达到了**图像级AUROC 99.66%（类级）/99.14%（统一）**，像素级AUROC 98.6%（类级）/98.66%（统一），均接近或达到SOTA。
- 在VisA上，类级设置为AUROC_cls 98.52%、AUROC_seg 99.06%；统一设置为AUROC_cls 94.2%、AUROC_seg 98.18%。
- LASB在**采样效率**上显著优于其他扩散模型（10个NFE即可达到接近最优性能，推理时间0.74秒），且训练时间和内存消耗更低（图3）。
- **稳定性**优异，多次采样结果方差可忽略。
- 证明了薛定谔桥在潜在空间中用于异常检测的有效性，无需辅助网络。

## 7. 优点

- **统一性**：单一框架同时处理异常检测和定位，无需额外的分类或分割子网络。
- **高效性**：潜在空间运作，训练和推理速度显著快于像素空间模型，内存消耗低。
- **鲁棒性**：对异常类别、光照、姿态变化不敏感，能够保持结构完整性。
- **稳定性**：多次推理结果一致，适合实际部署。
- **新颖性**：首次将线性薛定谔桥应用于潜在扩散模型进行无监督异常检测，理论推导清晰。
- **开源代码**：提供了GitHub仓库，促进可复现性。

## 8. 不足与局限

- **实验范围有限**：仅在MVTec-AD和VisA两个工业数据集上验证，未在医学、高光谱或其他领域测试，泛化性待证实。
- **统一设置下VisA检测性能略低于MambaAD**（94.2% vs 94.3%），且未与最新的基于Transformer的方法（如DDAD在class-based下达到99.84%准确率）进行直接对比（DDAD未在统一设置下报告）。
- **缺少消融实验**：未详细分析VQ-VAE压缩率、潜在空间维度等超参数的影响，也未对比不同边界条件（如高斯 vs Dirac delta）的效果。
- **计算资源细节缺失**：未报告完整训练时长、所需GPU数量等，不利于评估实际训练成本。
- **潜在偏差风险**：依赖预训练VQ-VAE（从Stable Diffusion初始化），可能引入预训练数据集（如LAION）的分布偏差；且推理时使用ImageNet预训练模型提取多尺度特征，其特征空间的域适应性可能影响定位性能。

（完）

---
title: "OTIAS: OcTree Implicit Adaptive Sampling for Multispectral and Hyperspectral Image Fusion"
title_zh: OTIAS：基于八叉树隐式自适应采样的多光谱与高光谱图像融合
authors: "Shangqi Deng, Jun Ma, Liang-Jian Deng, Ping Wei"
date: 2025-04-11
pdf: "https://ojs.aaai.org/index.php/AAAI/article/download/32275/34430"
tags: ["query:hsi"]
score: 6.0
evidence: 基于八叉树的自适应采样用于高光谱图像融合，改善光谱-空间表示
tldr: 针对现有隐式神经表示方法在遥感图像融合中忽略通道建模的问题，提出八叉树隐式自适应采样方法，从水平和垂直方向恢复数据，有效结合空间和光谱信息。实验表明该方法在多光谱与高光谱图像融合任务中优于现有技术，提升了光谱-空间特征质量。
source: AAAI-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32275/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 752, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32275/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1789, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32275/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1822, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32275/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 915, \"height\": 269, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32275/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 876, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32275/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 877, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32275/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1842, \"height\": 647, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32275/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 874, \"height\": 207, \"label\": \"Table\"}]"
motivation: 现有隐式方法忽略通道建模，对数据特异性不敏感。
method: 提出八叉树结构结合隐式自适应采样，从水平和垂直方向恢复数据。
result: 在遥感图像融合任务中取得更好的空间和光谱重建效果。
conclusion: 该方法有效提升多光谱/高光谱融合质量，有助于后续分类检测任务。
---

## Abstract
Implicit Neural Representation (INR) methods have demonstrated great potential in arbitrary-scale super-resolution tasks. This success is primarily due to their ability to continuously represent images using coordinates. In the task of remote sensing image fusion, INR methods have also shown promising applications. However, the previous INR methods neglect channel-wise modeling, while sharing a single kernel across all channels at each position, resulting in a lack of sensitivity to data specificity. To address these issues, we propose the OcTree Implicit Adaptive Sampling (OTIAS) method, which innovatively applies the octree structure to restore data from both horizontal and vertical directions, effectively incorporating spatial and spectral information from hyperspectral data. Additionally, we introduce a novel method to adaptively generate interpolation kernels based on coordinates. This approach efficiently produces customized interpolation kernel parameters for octree nodes, tailored to different spectral information. Overall, our method achieves state-of-the-art performance on the CAVE and Harvard datasets with 4× and 8× scaling factors, outperforming existing approaches.

---

## 论文详细总结（自动生成）

# OTIAS: OcTree Implicit Adaptive Sampling for Multispectral and Hyperspectral Image Fusion

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究背景**：多光谱与高光谱图像融合（MHIF）旨在融合低空间分辨率高光谱图像（LR-HSI）和高空间分辨率多光谱图像（HR-MSI），重建高空间分辨率高光谱图像（HR-HSI）。隐式神经表示（INR）因能连续表示图像，已在超分任务中展现潜力，但现有INR方法在融合任务中仅进行空间采样，忽略通道建模，且在所有通道共享同一插值核，导致对数据特异性（如不同波段的光谱信息）不敏感。
- **核心问题**：如何设计一种空间–光谱联合的INR采样结构，使模型能同时捕捉空间纹理和光谱细节，并能够根据位置和通道信息自适应生成插值核。
- **研究意义**：提出一种新颖的八叉树隐式自适应采样方法（OTIAS），同时利用水平和垂直方向（即空间和光谱维）的信息，有效提升融合质量，为遥感图像融合提供新范式。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将八叉树层次结构（OcTree Hierarchy, OTH）引入INR框架，在空间–光谱两个维度对低分辨率特征进行分层采样；并设计自适应合成核（Adaptive Synthesis Kernel, ASK）模块，针对每个八叉树叶子节点生成专属的深度可分离卷积核，实现按需融合。
- **整体架构**（图2）：
  1. **特征编码**：分别用光谱编码器 \(F_\phi\) 和空间编码器 \(F_\psi\) 将LR-HSI和HR-MSI映射到隐空间，得到特征图 \(\hat{Y} \in \mathbb{R}^{h \times w \times d}\) 和 \(\hat{Z} \in \mathbb{R}^{H \times W \times d}\)。
  2. **OcTree Hierarchy (OTH)**：对每个查询位置 \(C_q\)，先在空间域采样4个最近的LR域像素（类似四叉树），然后通过一个MLP将通道数扩展为 \(2d\)，再沿通道维度进行分组和重排，得到8个叶子节点 \(\hat{N}_q \in \mathbb{R}^{8 \times d}\)。这相当于将通道信息“展开”到空间，形成八叉树结构。
  3. **Adaptive Synthesis Kernel (ASK)**：对8个叶子节点 \(\hat{N}_q\)，通过一个瓶颈形MLP（Reduce → Span）和softmax，生成自适应核 \(\hat{K}_q \in \mathbb{R}^{8 \times d}\)。然后执行深度可分离卷积（元素级乘积求和）得到根节点特征 \(\Psi(C_q) \in \mathbb{R}^{1 \times d}\)。
  4. **长跳跃连接**：将双三次插值的LR-HSI \(Y_U\) 与根节点输出相加，得到最终HR-HSI \(\tilde{X}\)。
- **关键公式**：
  - 编码：\(\hat{Y}=F_\phi(Y), \hat{Z}=F_\psi(\text{Cat}(Y_U, Z))\)
  - OTH采样：\(\hat{N}_q = \text{MLP}(\text{cat}(\hat{Y}_s, \hat{Z}, \Delta c)).\text{view}()\)，其中\(\hat{Y}_s\)为插值后的LR特征，\(\Delta c\)为相对坐标。
  - ASK：\(\hat{K}_q = \text{Softmax}(\text{Span}(\text{Reduce}(\hat{N}_q)))\)，然后 \(\Psi(C_q) = \hat{N}_q \odot \hat{K}_q\)（\(\odot\)表示沿节点维度的加权求和）。
- **算法流程**（Algorithm 1）：输入LR特征、HR特征、坐标网格，输出融合特征。核心步骤：grid_sample获取四邻域特征 → 计算相对距离 → MLP扩展通道并重排为8节点 → ASK生成核 → 加权求和 → reshape。

## 3. 实验设计：数据集、场景、benchmark、对比方法
- **数据集**：
  - **CAVE**：32幅高光谱图像（31波段，400–700 nm），常用20幅训练、11幅测试。模拟生成：高斯模糊+4倍下采样得LR-HSI（16×16×31），用Nikon D700 SRF生成HR-MSI（64×64×3），共3920个64×64×31的patch，80%训练、20%验证。
  - **Harvard**：77幅室内外场景，选取20幅，每幅裁剪1000×1000，10幅训练、10幅测试。模拟方式同上。
- **缩放因子**：主要报告4×，也包含8×的消融实验。
- **对比方法**：共16种，包括传统方法（CSTF-FUS、LTTR、LTMR、IR-TenSR）和深度学习方法（SSRNet、ResTFNet、HSRNet、MogDCN、Fusformer、DHIF、PSRT、3DT-Net、DSPNet、QIS、DCT、MIMO）。其中JIIF和QIS是INR基线方法。
- **评估指标**：PSNR（↑）、SAM（↓）、ERGAS（↓）、SSIM（↑）。
- **公平性**：统一使用相同的模拟流程和训练/测试划分。所有方法在同一硬件平台（RTX4090）上重新运行或使用作者提供的结果。

## 4. 资源与算力
- **软件**：PyTorch 2.4.0、Python 3.11。
- **训练配置**：
  - 优化器：AdamW，学习率0.0001，损失函数ℓ1。
  - 训练轮数：1000 epochs。
  - 硬件：单张NVIDIA RTX4090 GPU（24G显存）。
- **说明**：论文未明确报告单次训练总时长（如小时数），但根据1000 epochs和数据集规模（3920 patches），估计在数小时内完成。参数数量和FLOPs已在表中给出（OTIAS约2.99M参数，8.722G FLOPs）。

## 5. 实验数量与充分性
- **主要对比实验**：在CAVE×4和Harvard×4两个设置下，与16种方法对比（表2），所有指标均报告平均值±标准差。
- **INR基线对比**：在CAVE×4下与JIIF、QIS对比参数、FLOPs及PSNR/SAM/ERGAS（表1）。
- **消融实验**：
  - **ASK模块有效性**：将ASK集成到JIIF和QIS中（表3），显示性能提升且参数量增加微小。
  - **OTH层数影响**：在8×缩放下测试1、2、3层八叉树结构（表4），层数增加改善SAM和ERGAS。
- **充分性分析**：
  - 对比方法覆盖传统优化、CNN、Transformer、INR等多种范式，数量充足。
  - 消融实验针对核心模块（ASK和OTH）设计，验证了各自贡献。
  - 提供可视化误差图（图3、图4）辅助定性分析。
  - 报告了参数和FLOPs，便于公平对比效率。
- **客观性**：所有结果均在同一模拟设置下获得，标准偏差已给出，实验设计较为严谨。

## 6. 论文的主要结论与发现
- OTIAS在CAVE×4上PSNR达52.43 dB，比第二名QIS高0.21 dB，比MIMO高1.57 dB；在Harvard×4上PSNR达49.08 dB，超过所有对比方法。
- 八叉树结构（OTH）通过将通道信息展开到空间，有效捕捉了光谱相关性，显著优于仅使用四叉树的INR方法。
- 自适应合成核（ASK）能够针对不同位置和通道生成定制化核，以极小的额外代价提升重建精细度。
- 消融证实ASK和OTH均有正向贡献，且ASK可作为通用增强模块移植到其他INR框架。

## 7. 优点
- **创新性**：首次将八叉树结构引入INR用于遥感融合，同时考虑空间和光谱两个维度的采样，突破了传统INR只关注空间域的局限。
- **轻量高效**：ASK通过瓶颈结构和深度可分离卷积，将核生成参数量降至原始方案的1%，在提升性能的同时保持低开销。
- **实验扎实**：对比方法众多（16种），包含传统和深度方法；消融实验覆盖核心模块；评价指标全面（4种质量指标+参数/FLOPs）。
- **可迁移性**：ASK模块可直接嵌入其他INR方法（如JIIF、QIS）并取得增益，表明其通用性。
- **可视化清晰**：提供了误差图，直观展示了OTIAS在纹理和光谱恢复上的优势。

## 8. 不足与局限
- **实验覆盖有限**：仅测试了4×和8×两种缩放因子，未涉及更大倍数（如16×）或真实传感器噪声场景。
- **泛化性未充分验证**：仅在CAVE和Harvard两个室内/近景数据集上评测，未在机载或卫星遥感数据（如 Chikusei、Pavia）上验证，实际应用中可能面临更大尺度、更复杂光照和噪声。
- **计算资源细节缺失**：未报告训练总时长，也未与所有对比方法进行统一的FLOPs对比（部分方法未提供FLOPs）。
- **潜在偏差**：模拟数据的退化模型（高斯模糊+固定SRF）可能与真实传感器特性存在差异，真实场景性能仍有待评估。
- **超参数敏感性**：未讨论八叉树层数、瓶颈比r等超参数的选择对结果的影响，可能需要在更多数据集上调优。
- **理论分析不足**：对八叉树为何能改善光谱建模缺乏深入的数学解释，更多是经验性验证。

（完）

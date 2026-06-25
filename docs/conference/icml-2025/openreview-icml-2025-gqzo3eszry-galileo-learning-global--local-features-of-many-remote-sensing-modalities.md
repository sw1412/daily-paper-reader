---
title: "Galileo: Learning Global & Local Features of Many Remote Sensing Modalities"
title_zh: Galileo：学习多种遥感模态的全局与局部特征
authors: "Gabriel Tseng, Anthony Fuller, Marlena Reil, Henry Herzog, Patrick Beukema, Favyen Bastani, James R Green, Evan Shelhamer, Hannah Kerner, David Rolnick"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gqZO3eSZRy"
tags: ["query:hsi-lidar"]
score: 8.0
evidence: 多模态遥感表示学习用于联合分类与融合
tldr: 该论文针对遥感数据多模态、多尺度的挑战，提出了Galileo，一个高度多模态的Transformer，可处理多光谱光学、合成孔径雷达、高程等多种遥测模态。通过新颖的自监督学习算法，利用掩码建模提取跨模态的全局与局部多尺度特征。实验表明其在作物制图和洪水检测等任务上表现优异，为高光谱与LiDAR等多模态遥感数据的联合分类与融合提供了强大的基础模型。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gqzo3eszry/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1051, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gqzo3eszry/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1672, \"height\": 992, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gqzo3eszry/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gqzo3eszry/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 815, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gqzo3eszry/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1729, \"height\": 748, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1754, \"height\": 725, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 620, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1046, \"height\": 1287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1160, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 853, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 854, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 857, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 725, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 989, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 744, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 726, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 816, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1771, \"height\": 694, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1772, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1776, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gqzo3eszry/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1387, \"height\": 981, \"label\": \"Table\"}]"
motivation: 遥感数据模态多样且目标尺度变化极大，现有方法难以学习共享表示。
method: 提出高度多模态Transformer和自监督掩码建模算法，提取跨模态多尺度特征。
result: 在作物制图、洪水检测等多个遥感任务上取得优异性能。
conclusion: Galileo有效融合了多种遥感模态，提升了多任务泛化能力。
---

## Abstract
We introduce a highly multimodal transformer to represent many remote sensing modalities - multispectral optical, synthetic aperture radar, elevation, weather, pseudo-labels, and more - across space and time. These inputs are useful for diverse remote sensing tasks, such as crop mapping and flood detection. However, learning shared representations of remote sensing data is challenging, given the diversity of relevant data modalities, and because objects of interest vary massively in scale, from small boats (1-2 pixels and fast) to glaciers (thousands of pixels and slow). We present a novel self-supervised learning algorithm that extracts multi-scale features across a flexible set of input modalities through masked modeling. Our dual global and local contrastive losses differ in their targets (deep representations vs. shallow input projections) and masking strategies (structured vs. not). Our Galileo is a single generalist model that outperforms SoTA specialist models for satellite images and pixel time series across eleven benchmarks and multiple tasks.

---

## 论文详细总结（自动生成）

# Galileo：学习多种遥感模态的全局与局部特征

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：遥感数据模态多样（多光谱光学、合成孔径雷达、高程、气象、伪标签等），且地物目标尺度差异极大（从1-2像素的小船到数千像素的冰川），现有自监督学习方法大多针对单一模态或特定输入形态（如像素时间序列 vs 图像时间序列），缺乏能够灵活处理多种模态和多种时空尺度（单时刻图像、多时刻图像、像素时间序列）的通用模型。
- **意义**：构建一个能同时处理多种遥感模态、多种输入形状的统一预训练模型，有助于在标注稀缺的情况下提升下游任务（作物制图、洪水检测、海洋碎片监测）的性能，降低应用门槛，促进遥感机器学习在食物安全、灾害响应等社会重要领域的落地。

## 2. 方法论：核心思想与关键技术细节
- **核心思想**：通过**双目标掩码数据建模**同时学习全局特征和局部特征。全局任务利用深度目标表征和结构化（时空）掩码，鼓励跨输入样本的判别性；局部任务利用浅层目标表征（线性投影）和随机掩码，鼓励输入内部不同令牌间的细粒度区分。
- **算法流程**（结合图2）：
  1. **令牌化**：将输入（空间×时间×通道组）通过线性投影、位置编码等转化为令牌序列。
  2. **掩码构造**：全局任务采用时空结构化掩码（空间掩码保持时间一致性，时间掩码保持空间一致性），局部任务采用无结构随机掩码。
  3. **编码**：
     - 在线编码器处理可见令牌，参数由梯度下降更新。
     - 目标编码器通过指数移动平均（EMA）更新，输出目标令牌表征。
  4. **目标层次选择**：
     - 全局任务：从目标编码器不同深度（按模态选择层数）提取表征作为深度目标。
     - 局部任务：仅使用目标编码器的线性投影（无Transformer层）作为浅层目标。
  5. **预测与损失**：预测器通过交叉注意力从可见编码预测目标令牌表征，使用**PatchDisc损失**（InfoNCE，令牌级对比学习）。全局任务使用跨批次负样本（PatchDisc_B），局部任务使用批次内负样本（PatchDisc）。
  6. **总损失**：全局损失和局部损失平均。
- **目标多样性验证**：表2显示全局任务提升**间输入**特征多样性，局部任务提升**内输入**特征多样性，两者结合达到平衡。

## 3. 实验设计
- **预训练数据**：全球采样，127,155个实例，每个实例包含24个月时间步、96×96像素、9种遥感模态（空间-时间变化：Sentinel-1/2; 空间变化：高程/坡向、Dynamic World、WorldCereal; 时间变化：ERA5、TerraClimate、VIIRS夜光; 静态：人口、经纬度、平均类别图）。
- **下游基准**：涵盖11个基准，包括：
  - **图像分类**（4个）：m-EuroSat, m-BigEarthNet, m-So2Sat, m-Brick-Kiln
  - **图像分割**（5个）：m-Cashew-Plant, m-SA-Crop-Type, MADOS（海洋碎片）, Sen1Floods11（洪水）, PASTIS（多时刻分割）
  - **像素时间序列分类**（3个）：Breizhcrops, CropHarvest（Togo, Brazil, Kenya）
- **对比方法**：包括SatMAE, SatMAE++, CROMA, SoftCon, DOFA-v1, Satlas, MMEarth, DeCUR, Prithvi 2.0, AnySat, Presto等。所有模型均重新运行并统一调整超参数（学习率、特征缩放等）。
- **评估设置**：对图像任务测试四种训练比例（100%, 20%, 5%, 1%），使用kNN、线性探测、微调三种方式。对时间序列任务使用线性探测。

## 4. 资源与算力
- **模型训练**：在单个H100 GPU上预训练。ViT-Nano约200 GPU小时，ViT-Tiny约259 GPU小时，ViT-Base约573 GPU小时（500个epoch）。
- **框架**：使用Mila计算集群、Ai2的Beaker计算平台。未明确说明使用的GPU数量（推测多卡并行，但论文写“single H100 GPU”可能是单卡训练，但有效批大小512通过重复4次32批次实现，实际可能需要多卡？论文未明确）。另外，下游评估也使用了计算资源，但未具体量化。

## 5. 实验数量与充分性
- **实验数量**：论文进行了大量消融实验：
  - 全局任务消融（表7）：6种掩码策略/目标深度/损失函数组合。
  - 局部任务消融（表8）：5种组合。
  - 组合目标消融（表9）：8种组合（共享/不共享预测器、不同损失等）。
  - 预训练数据模态消融（表11）：逐个移除9种模态。
  - 全局批大小影响（表10）：3种设置。
  - 下游性能完整表格（表3-6、表15-17）：包含所有模型在4个分类、5个分割、3个时间序列任务上的kNN、线性探测、微调结果，及不同训练比例。
  - 计算-精度权衡（图4、表14）：不同patch size下的性能和MACs。
- **充分性与公平性**：
  - 所有对比模型均重新运行，统一超参数扫描（学习率、特征缩放、临时聚合方法），避免因预处理差异导致的性能偏差。
  - 分割任务中，AnySat使用逐像素特征，为保证公平，线性探测时仅采样6.25%像素特征，但测试时用全部像素，且与作者确认。
  - 使用了多个随机种子（线性探测重复5次平均）。
  - 消融实验覆盖了方法各部分，论证了双目标、掩码策略、目标深度、loss选择等关键设计的必要性。
  - 不足：主要聚焦Sentinel-2/1等多光谱/雷达模态，对高光谱、LiDAR等模态未涉及；所有评估均基于开源数据集，实际部署场景可能有额外挑战。

## 6. 主要结论与发现
- Galileo-Base在所有图像任务和时间序列任务上平均排名第一（表1），超过了更大的专用模型（如CROMA Large, SatMAE Large）和通用模型（AnySat, Presto）。
- 在图像分类（kNN和微调）上，Galileo-Base在EuroSat（100%数据）达93.0%和97.7%，领先第二名3%+；在低数据场景（1%）下提升更显著（56.6% vs 51.3%）。
- 在图像分割上，Galileo-Base在MADOS（海洋碎片小目标）上mIoU达67.6%，超过CROMA的66.3%；在Sen1Floods11（SAR洪水）上达79.4%（仅CROMA和AnySat支持SAR）。
- 在像素时间序列上，Galileo-Base在Breizhcrops达73.0%，远高于AnySat的66.1%和Presto的63.0%。
- 消融实验证实：全局任务利于分类，局部任务利于分割；两者结合可同时提升两者，且训练更稳定（100%成功率达>80% EuroSat vs 单目标仅63%）。
- 多模态预训练数据中，移除TerraClimate、VIIRS、LandScan等显著影响性能，表明这些额外模态的重要性。

## 7. 优点
- **方法创新**：首次在遥感SSL中提出双目标（深/浅）对比学习，同时学习全局分类级和局部细粒度特征，避免了单一目标或loss的不足。
- **架构灵活性**：ViT基础架构支持任意通道组、空间大小、时间步数，可处理图像、多时刻图像、像素时间序列，无需修改模型。
- **数据多样性**：预训练数据集包含9种模态（SAR、光学、气象、人口、高程等），覆盖全球地理和语义多样性，且通过聚类保证多样性。
- **评估全面性**：覆盖11个基准、多种训练比例、三种特征提取方式（kNN/线性探测/微调），并重新运行所有基线，避免不公平比较。
- **实用性**：提供了多个模型尺寸（Nano/Tiny/Base），并支持可变patch size，用户可根据计算资源选择。开源模型、权重、数据和代码。

## 8. 不足与局限
- **模态覆盖**：未包含高光谱、LiDAR、航空影像等常见遥感模态，虽然方法可扩展但未验证。
- **预训练数据规模**：127k实例相对于ImageNet级别仍较小，且仅24个月时间窗口，可能无法捕获长周期现象。
- **下游任务局限**：所有评估均基于公开的光学/SAR数据集，未在实际大规模生产环境（如全球作物制图）中验证。
- **计算开销**：ViT-Base预训练需573 GPU小时，对于算力有限的组织可能较高；但小模型（Nano）仅200小时，性能依然不错。
- **消融仅验证集**：消融实验仅使用四个任务的验证集，未在测试集上报告，可能略微高估。
- **AnySat对比**：AnySat是并发工作，论文承认其共享精神，但在某些任务（如PASTIS）上AnySat略优（46.2% vs 39.2%），说明缺乏时间建模的图像模型仍可能不擅长多时刻任务。
- **社会影响**：方法可能被用于未得到社区知情同意的监测，作者虽呼吁与当地社区合作，但未提供具体缓解措施。

（完）

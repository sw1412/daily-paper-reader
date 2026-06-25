---
title: An Evidence-Based Post-Hoc Adjustment Framework for Anomaly Detection Under Data Contamination
title_zh: 基于证据的数据污染下异常检测事后调整框架
authors: "Sukanya Patra, Souhaib Ben Taieb"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NgLFQTBPRR"
tags: ["query:hsi"]
score: 6.0
evidence: 数据污染下的测试时自适应异常检测
tldr: 该论文提出EPHAD框架，针对训练数据污染问题，在测试时利用多模态基础模型收集证据来调整异常检测输出。该方法无需重训练或先验知识，简单有效。可应用于高光谱异常检测，但未在光谱数据上验证。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nglfqtbprr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1307, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nglfqtbprr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nglfqtbprr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nglfqtbprr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nglfqtbprr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1305, \"height\": 523, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 838, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 713, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 720, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 656, \"height\": 250, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 939, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nglfqtbprr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 579, \"height\": 300, \"label\": \"Table\"}]"
motivation: 真实异常检测数据常受污染，现有方法需访问训练流程或先验比例。
method: 测试时利用多模态基础模型证据调整模型输出。
result: 在多个基准上提升了污染数据下的检测性能。
conclusion: 为异常检测提供了鲁棒后处理方案，具有迁移潜力。
---

## Abstract
Unsupervised anomaly detection (AD) methods typically assume clean training data, yet real-world datasets often contain undetected or mislabeled anomalies, leading to significant performance degradation. Existing solutions require access to the training pipelines, data or prior knowledge of the proportions of anomalies in the data, limiting their real-world applicability. To address this challenge, we propose EPHAD, a simple yet effective test-time adaptation framework that updates the outputs of AD models trained on contaminated datasets using evidence gathered at test time. Our approach integrates the prior knowledge captured by the AD model trained on contaminated datasets with evidence derived from multimodal foundation models like Contrastive Language-Image Pre-training (CLIP), classical AD methods like the Local Outlier Factor or domain-specific knowledge. We illustrate the intuition behind EPHAD using a synthetic toy example and validate its effectiveness through comprehensive experiments across eight visual AD datasets, twenty-six tabular AD datasets, and a real-world industrial AD dataset. Additionally, we conduct an ablation study to analyse hyperparameter influence and robustness to varying contamination levels, demonstrating the versatility and robustness of EPHAD across diverse AD models and evidence pairs. To ensure reproducibility, our code is publicly available at https://github.com/sukanyapatra1997/EPHAD.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：无监督异常检测（AD）方法通常假设训练数据是“干净”的（仅含正常样本），但在实际应用中，数据集常含有未检测到的或误标的异常样本（数据污染），导致模型性能显著下降。
- **现有方法的局限**：现有的数据污染处理方法要么需要访问训练流程、训练数据，要么需要提前知道异常比例（污染率），这些条件在实际部署中往往无法满足，尤其当使用预训练的商业闭源模型时。
- **本文目标**：提出一种无需访问训练流程、无需重训练、无需先验污染率知识的**测试时自适应（Test-Time Adaptation, TTA）框架**，通过测试时收集的证据来事后调整已受污染异常检测模型的输出，从而提高检测性能。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：利用测试时收集的“证据函数”（evidence function）对已训练好的受污染AD模型的输出进行指数倾斜（exponential tilting），从而修正密度估计或分数排序，使之更接近真实的正常样本分布。
- **技术细节**：
  - **密度型AD的调整**：对于密度估计模型，受污染密度 \( f_{\pm} \) 通过指数倾斜调整得到新密度 \( \tilde{f}_{\pm}(x) \propto f_{\pm}(x) \exp(T(x)/\beta) \)，其中 \( T(x) \) 是证据函数（赋予正常样本更高值），\( \beta \) 是温度参数。
  - **分数型AD的扩展**：由于现代AD方法多输出异常分数而非密度，论文利用能量模型观点，定义 \( \tilde{f}_{\pm}(x) \propto \exp(s_{\pm}^{\text{in}}(x) + T(x)/\beta) \)，从而直接调整内点分数 \( s_{\pm}^{\text{in}} \)，异常检测阈值相应变更。
  - **理论保证**：证明当证据函数满足 \( \mathbb{E}_{x\sim P_+}[\log(\exp(T(x)/\beta)/Z_\beta)]>0 \) 时，调整后的密度与真实正常密度的KL散度更小。
  - **超参数自适应（EPHAD-Ada）**：提出无监督的β选择方法，基于测试样本上原始模型和证据函数的预测熵之比自适应确定β，避免依赖标注验证集。
  - **证据函数**：可以是多模态基础模型（如CLIP）、经典AD方法（如LOF、Isolation Forest）或领域特定规则（如工业热成像的温差规则）。

## 3. 实验设计

- **数据集**：
  - **视觉AD**：8个数据集。感官AD：MVTecAD、MPDD、ViSA、RealIAD；语义AD：CIFAR-10、Fashion-MNIST、MNIST、SVHN。采用one-vs-rest协议，污染率ε=0.1（默认），部分使用“重叠”或“非重叠”设置。
  - **表格AD**：ADBench中的26个经典数据集（覆盖医疗、航天、金融等），通过添加高斯噪声合成异常模拟污染。
  - **工业AD**：CSP植物热图像数据集（Patra et al., 2024），使用基于预测的ForecastAD方法。
- **基准方法**：
  - 视觉：CLIP（零样本）、CFLOW、DRÆM、FastFlow、PaDiM、PatchCore、Reverse Distillation (RD)、ULSAD。
  - 表格：IForest、LOF、DeepSVDD、ECOD、COPOD。
  - 污染处理对比：Refine (Yoon et al., 2022)、LOE (Qiu et al., 2022)、SoftPatch (Jiang et al., 2022)。
- **评估指标**：AUROC（曲线下面积），视觉实验按类别平均，表格实验重复3次取均值和标准误差。
- **消融实验**：污染率（0%,5%,10%,15%）、温度参数β变化、证据函数类型、测试集异常比例等。

## 4. 资源与算力

- 文中明确说明：**基础AD模型训练使用单个NVIDIA A100 GPU**；EPHAD推理在CPU上运行。
- **未提及**：具体训练时长、总计算量、GPU数量（各个实验是否复用同一GPU）、推理耗时等细节。仅说明用Anomalib和ADBench开源库。

## 5. 实验数量与充分性

- **实验总量**：
  - 8个视觉数据集 × 7种AD方法（含EPHAD两种变体）≈ 约150+组（含不同种子）。
  - 26个表格数据集 × 5种AD方法 × 2种证据函数 × 2种变体 ≈ 500+组（含3次重复）。
  - 1个工业数据集 × 1种AD方法 × 2种变体。
  - 3种现有污染处理方法对比（LOE、SoftPatch、Refine）在部分数据集上。
  - 消融实验：污染率（4个水平）× 7种AD方法、温度β扫描、证据函数对比。
- **充分性与客观性**：
  - 覆盖视觉、表格、工业三类场景，基准方法多样，代码公开，可复现。
  - 结果均报告均值和标准误差，采用标准AUROC指标。
  - 对比方法使用开源库，设置公平（部分对比需注意：LOE和SoftPatch需修改训练过程，与本文后处理设定不同，论文已说明此差异）。
  - 消融实验全面，验证了污染率、超参数β、证据函数的影响。
- **潜在偏差**：视觉证据函数仅用CLIP，表格证据仅用LOF/IForest，未探索其他基础模型（如DINOv2等）；自适应EPHAD-Ada并非总能优于固定β，说明仍存在局限性。

## 6. 主要结论与发现

- EPHAD能显著提升受污染数据训练的各种AD模型的性能，多数情况下超越单独使用AD模型或证据函数。
- 当证据函数优于原始AD模型时，改善最明显；若证据较弱，通过调整β可避免性能下降。
- EPHAD-Ada提供无监督β选择，在部分场景下优于固定β，但整体与固定β结果相近。
- 在不同污染率（0%~15%）下，EPHAD均能稳定提升性能，尤其当证据足够强时，性能几乎不受污染率影响。
- 在工业热成像数据上，基于领域规则的证据函数能有效恢复受污染模型的性能，甚至接近干净训练时的水平。
- 与LOE、SoftPatch等污染处理方法相比，EPHAD在证据函数较好时无需修改训练过程即可达到可比甚至更优性能。

## 7. 优点

- **简单实用**：纯后处理，无需访问训练数据、训练管道或污染率，可直接用于预训练模型（包括闭源模型）。
- **灵活通用**：可整合多种证据源：基础模型、经典AD方法、领域知识。
- **理论支撑**：提供KL散度减少的理论条件，并与生成模型中的测试时对齐方法建立联系。
- **自适应超参数**：提出基于熵的无监督β选择策略，降低调参需求。
- **实验全面**：涵盖视觉、表格、工业三大类数据，验证了框架的鲁棒性和可迁移性。

## 8. 不足与局限

- **证据函数依赖性**：性能很大程度上取决于证据函数的质量，当证据函数严重弱于原始模型时（如SVHN上ULSAD vs CLIP），需仔细调整β，自适应策略也未必总能解决。
- **自适应β有待改进**：EPHAD-Ada基于未校准的内点概率，有时导致性能下降，论文承认需要更可靠的推断方法。
- **实验覆盖有局限**：
  - 视觉证据函数仅使用CLIP，未测试如DINOv2、ImageBind等其他基础模型。
  - 表格证据仅用LOF/IForest，未探索基于自编码器或深度学习的证据。
  - 未在高光谱、视频、时间序列等场景验证，尤其是**高光谱异常检测**场景，虽然方法论具有迁移潜力，但论文未提供任何光谱数据实验。
- **计算开销**：虽然推理在CPU上运行，但基础模型训练仍需要GPU，且证据函数可能要求额外的特征提取（如CLIP需要图像编码器）。
- **理论基础**：KL散度减少的条件要求证据函数在正常样本上的期望为正，实际中难以保证，论文未给出如何检查该条件。
- **应用限制**：在闭环系统中如果测试数据分布与训练差异极大，证据可能不准确；此外，对隐私敏感场景，使用CLIP等模型可能存在数据泄露风险（论文已提及但未深入讨论）。

（完）

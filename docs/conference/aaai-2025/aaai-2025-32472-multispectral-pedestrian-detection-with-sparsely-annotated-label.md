---
title: Multispectral Pedestrian Detection with Sparsely Annotated Label
title_zh: 稀疏标注下的多光谱行人检测
authors: "Chan Lee, Seungho Shin, Gyeong-Moon Park, Jung Uk Kim"
date: 2025-04-11
pdf: "https://ojs.aaai.org/index.php/AAAI/article/download/32472/34627"
tags: ["query:hsi"]
score: 8.0
evidence: 多光谱行人目标检测，直接相关于高光谱目标检测
tldr: 针对多光谱行人检测中稀疏标注导致伪标签质量差、学习范围有限的问题，提出SAMPD框架，包括多光谱行人自适应权重和正伪标签增强模块，有效利用未标注区域的信息。在多个多光谱数据集上验证了该方法在减少标注成本的同时提升了检测精度，为高光谱目标检测中的标注稀疏问题提供了可借鉴的方法。
source: AAAI-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32472/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32472/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1693, \"height\": 966, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32472/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 848, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32472/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1840, \"height\": 869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/aaai-2025-accepted/aaai-2025-32472/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 802, \"height\": 506, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32472/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1726, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32472/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 875, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32472/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 873, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32472/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32472/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 874, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/aaai-2025-accepted/aaai-2025-32472/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 871, \"height\": 230, \"label\": \"Table\"}]"
motivation: 现有稀疏标注目标检测方法在多光谱领域忽略了伪标签质量提升，且过度依赖固定真值，限制了学习多样性。
method: 提出多光谱行人自适应权重（MPAW）和正伪标签增强（PPE）模块，动态调整伪标签质量。
result: 在多个多光谱行人检测基准上，该方法显著优于现有稀疏标注检测方法，尤其在低标注比例下。
conclusion: 该方法有效解决了多光谱稀疏标注检测中的标注不足问题，提升了检测鲁棒性。
---

## Abstract
Although existing Sparsely Annotated Object Detection (SAOD) approches have made progress in handling sparsely annotated environments in multispectral domain, where only some pedestrians are annotated, they still have the following limitations: (i) they lack considerations for improving the quality of pseudo-labels for missing annotations, and (ii) they rely on fixed ground truth annotations, which leads to learning only a limited range of pedestrian visual appearances in the multispectral domain. To address these issues, we propose a novel framework called Sparsely Annotated Multispectral Pedestrian Detection (SAMPD). For limitation (i), we introduce Multispectral Pedestrian-aware Adaptive Weight (MPAW) and Positive Pseudo-label Enhancement (PPE) module. Utilizing multispectral knowledge, these modules ensure the generation of high-quality pseudo-labels and enable effective learning by increasing weights for high-quality pseudo-labels based on modality characteristics. To address limitation (ii), we propose an Adaptive Pedestrian Retrieval Augmentation (APRA) module, which adaptively incorporates pedestrian patches from ground-truth and dynamically integrates high-quality pseudo-labels with the ground-truth, facilitating a more diverse learning pool of pedestrians. Extensive experimental results demonstrate that our SAMPD significantly enhances performance in sparsely annotated environments within the multispectral domain.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：多光谱行人检测结合可见光和热红外图像，能在低光照、恶劣天气等条件下稳健检测行人。然而，实际应用中常出现**稀疏标注**问题——由于人为疏忽（如小目标、遮挡行人漏标），训练集中仅部分行人被标注，导致检测器学习到的行人外观知识有限，性能显著下降。
- **现有方法的局限**：已有的稀疏标注目标检测（SAOD）方法主要面向通用物体检测，在多光谱领域存在两大不足：
  1. 缺乏对伪标签质量的提升机制，直接使用模型预测的高置信度框作为伪标签，易引入噪声；
  2. 依赖固定真值标注，无法动态纳入训练过程中识别出的缺失标注，限制了行人外观多样性的学习。
- **论文目标**：提出**SAMPD（Sparsely Annotated Multispectral Pedestrian Detection）** 框架，通过多模态知识增强伪标签质量，并动态丰富行人样本库，解决稀疏标注下的检测性能下降问题。

## 2. 方法论：核心思想、关键技术细节

- **整体框架**：采用教师-学生结构，教师模型生成伪标签，学生模型作为最终检测器。输入图像经APRA模块增强后分别送入教师和学生网络（均为3路编码：可见光V、热红外T、融合F）。
- **核心模块一：多光谱行人自适应权重（MPAW）**
  - 对学生模型每个模态（V/T/F）的伪标签特征与真值特征计算余弦相似度，得到该模态的权重 \( w_k \)（公式1）。权重越高表示该模态伪标签越可靠。
  - 最终检测损失为各模态损失加权和（公式3）：\( L_{\text{det}}^{\text{sum}} = w_V L_V^{\text{det}} + w_T L_T^{\text{det}} + w_F L_F^{\text{det}} \)。
  - 作用：自动降低低质量伪标签或不可靠模态的影响，稳定训练。
- **核心模块二：正伪标签增强（PPE）**
  - 将伪标签分为**正伪标签**（与学生模型真值特征相似度 > τ1=0.9）、**负伪标签**（相似度 < τ2=0.7）和**不确定伪标签**（介于两者之间）。
  - 设计**正伪标签引导损失** \( L_{PG} \)（公式7）：拉近正伪标签之间的距离，推开正伪标签与负伪标签的距离，同时保留不确定区域作为缓冲区，避免偏差。
  - 损失适用于三个模态，促进教师模型生成更高质量的伪标签。
- **核心模块三：自适应行人检索增强（APRA）**
  - **图像增强**：从真值样本库中检索与当前图像亮度最匹配的 m 个行人patch，根据原图标注的平均尺寸缩放后，粘贴到图像的**低显著性区域**（通过显著性图确定）——这些区域通常不是行人可能出现的位置（如天空、车辆前部），避免干扰。
  - **动态真值细化**：若某伪标签的模态权重和分类得分均超过阈值 τ1，则将其转换为真值，动态扩充训练标注。随着训练进行，真值数量逐步增加（KAIST上从40107增至47369，增长18%）。
- **总损失**：\( L_{\text{Total}} = \lambda_1 L_{\text{det}}^{\text{sum}} + \lambda_2 (L_{PG}^V + L_{PG}^T + L_{PG}^F) \)，其中 \(\lambda_1 = \lambda_2 = 1\)。

## 3. 实验设计

- **数据集**：
  - **KAIST**：95328对可见-热红外图像，103128个行人框。按稀疏标注模拟方式（按小目标概率删除标注），分别移除30%、50%、70%的标注。
  - **LLVIP**：15488对低光照可见-热红外图像。同样按30%、50%、70%移除标注。
- **评估指标**：
  - KAIST：**漏检率（MR）**，在FPPI区间[10⁻², 10⁰]上平均，越低越好。分为All、Day、Night三类。
  - LLVIP：同时报告**MR**和**AP₅₀**（IoU=0.5的平均精度）。
- **对比方法**：5种SAOD方法：
  - Pseudo label (CVPR'19)、BRL (ICASSP'20)、Co-mining (AAAI'21)、SparseDet (ICCV'23)、Calibrated Teacher (AAAI'23)
- **基线**：仅用稀疏标注训练的“Supervised”（无伪标签或增强）。
- **消融实验**：分别移除MPAW、PPE、APRA模块，验证各模块贡献；比较静态vs动态APRA；与Robust Teacher (CVIU'23) 等增强方法对比。
- **全标注场景测试**：在KAIST和LLVIP的0%移除场景下（全标注），也评估SAMPD性能。

## 4. 资源与算力

- 论文明确提及：使用 **2块GTX 3090 GPU**，每个mini-batch处理6张图像，训练80个epoch，学习率0.0001，优化器为SGD。
- 未给出具体训练时间（小时数），但提供了硬件和超参数细节。

## 5. 实验数量与充分性

- **实验数量**：共4大类实验：
  1. 在KAIST数据集上3种稀疏比例（30%/50%/70%）× 3种场景（All/Day/Night）的主对比实验（表1）。
  2. 在LLVIP数据集上3种稀疏比例（30%/50%/70%）的主对比实验（表2）。
  3. 消融实验（表3、表4）：分别验证MPAW、PPE、APRA模块，及APRA中动态vs静态效果。
  4. 额外实验：与Robust Teacher增强方法对比（表4）；在0%全标注场景下对比Calibrated Teacher与SAMPD（表6）；动态真值数量变化曲线（图4）。
- **充分性评估**：
  - 覆盖了多模态（可见光、热红外、融合）、多场景（白天、夜晚）、多稀疏程度（30%~70%）、多个基准数据集（KAIST、LLVIP）。
  - 消融实验设计完整，每个模块的贡献清晰。
  - 与5种主流SAOD方法对比，且所有方法采用相同backbone（SSD+VGG16），公平性良好。
- **潜在不足**：未在不同backbone（如ResNet、Transformer）或检测器上验证泛化性；未在更多领域（如遥感、自动驾驶）的稀疏标注场景测试。

## 6. 主要结论与发现

1. **SAMPD在所有稀疏标注比例下均显著优于现有SAOD方法**。例如在KAIST 30%移除下，MR降至8.56，而第二名Calibrated Teacher为10.47；在LLVIP 30%移除下，MR为7.65（Calibrated Teacher为9.41）。
2. **在70%移除的极端稀疏场景下优势更明显**：KAIST全天MR 23.52，比第二名（28.20）提升近5个百分点。
3. **动态真值细化有效提升标注完整性**：训练过程中真值数量增加18%（KAIST），且比静态APRA（无动态细化）降低MR约0.32（KAIST）和0.93（LLVIP）。
4. **在全标注场景（0%移除）中，SAMPD仍能进一步提升性能**（KAIST MR从7.58降到6.50），表明其能补全潜在漏标。
5. **APRA模块优于传统随机增强**，因为考虑了场景亮度匹配和显著性区域选择，避免了视觉失真。

## 7. 优点（方法与实验设计亮点）

- **方法创新性**：将多模态感知（V/T/F）引入伪标签质量评估，通过模态权重自适应调整，有效抑制噪声。
- **完整性**：三个模块（MPAW、PPE、APRA）环环相扣，分别解决伪标签质量、引导、及样本多样性，形成闭环。
- **实验严谨**：
  - 所有对比方法均在同一代码库和参数下复现。
  - 消融实验验证了每个组件贡献，并区分静态/动态APRA。
  - 不仅验证稀疏标注场景，也在全标注场景测试，证明方法通用性。
- **可视化充分**：图4展示了动态真值数量增长，图5展示了APRA增强示例，直观说明效果。

## 8. 不足与局限

- **APRA模块的局限**：目前仅基于图像亮度进行样本检索，且仅提供图像级指导。未来可探索同时考虑行人个体特征（如姿态、尺度）的检索与特征级引导。
- **实验覆盖**：仅在KAIST和LLVIP两个数据集上验证，均为公开行人检测数据集。未在更复杂的多光谱场景（如拥挤街道、远红外）或遥感高光谱图像上测试，影响对高光谱目标检测的泛化性判断。
- **baseline选择**：对比的SAOD方法均为通用物体检测方法，缺少专为多光谱设计的稀疏标注方法（目前无），但可理解。
- **消融实验只报告了30%移除情况**，未在50%、70%下详细展示各模块贡献，可能削弱消融结论的全面性。
- **计算开销**：APRA模块涉及检索、显著性图生成、patch粘贴等步骤，但未给出推理时的额外时间成本，实际部署效率有待评估。

（完）

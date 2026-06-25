---
title: Query Optimization Detection Transformer for Small Objects in Remote Sensing Images
title_zh: 面向遥感图像小目标的查询优化检测Transformer
authors: "Jinsheng Xiao, Mingyang Gu, Yuebin Zhou, Wenjuan Xie, Wei Yang, Jian Zhou"
date: 2024-09-23
pdf: "https://openreview.net/pdf?id=T6hhDEnAoo"
tags: ["query:hsi"]
score: 6.0
evidence: 遥感目标检测方法可迁移至高光谱目标检测
tldr: 本文针对遥感图像中小目标特征表示弱、背景噪声大的问题，提出QO-DETR检测Transformer。通过查询提议生成模块和注意力聚焦机制，增强小目标特征。实验表明该方法在遥感小目标检测上有效，其框架可迁移至高光谱图像目标检测任务。
source: ICLR-2025-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-iclr-2025-t6hhdenaoo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-t6hhdenaoo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1158, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-iclr-2025-t6hhdenaoo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1172, \"height\": 596, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-iclr-2025-t6hhdenaoo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-t6hhdenaoo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 743, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-t6hhdenaoo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-t6hhdenaoo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-iclr-2025-t6hhdenaoo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1463, \"height\": 343, \"label\": \"Table\"}]"
motivation: 遥感图像中小目标易受背景噪声干扰，特征表示困难。
method: 设计查询提议生成模块和注意力聚焦机制提升小目标特征。
result: 在遥感小目标检测数据集上表现出优越性能。
conclusion: 该方法为高光谱目标检测提供了可迁移的框架。
---

## Abstract
Object detection in remote sensing images is a challenging task. Remote sensing images contain substantial background noise and complex contextual information, which weakens the feature representation of small objects, making detection difficult. To solve these problems, a detection Transformer for small objects in remote sensing images is proposed, called QO-DETR. Specifically, to enhance the feature representation of small objects, a query proposal generation module is designed to select queries based on multi-class classification scores. These queries provide the initial position embeddings for object queries in the decoder, enabling the decoder's attention mechanism to focus on object regions.  To improve the model’s robustness to noise, a group denoising module is designed to add noise into decoder queries during training, enhancing the network's ability to reconstruct object features from noise. To accurately locate small objects, a query cascade refinement strategy is designed, and each decoder layer refines anchor parameters under the guidance of preceding layers to achieve spatial alignment between the anchor and the object. Experiments have been carried out on DIOR and AI-TOD. The AP and APs on DIOR reach 51.3% and 13.4%, respectively, while on AI-TOD, they reach 23.6% and 30.1%. QO-DETR shows superior performance in detecting small objects.

---

## 论文详细总结（自动生成）

# 面向遥感图像小目标的查询优化检测 Transformer（QO-DETR）—— 详细中文总结

## 1. 核心问题与研究动机
- **问题背景**：遥感图像具有大视场、复杂背景和大量噪声，小目标（面积小于 32×32 像素）仅占很少像素，其特征表示极弱，且容易受背景和其他实例的干扰。
- **现有不足**：
  - 传统 CNN 检测器（如 Faster R-CNN、SSD）及通用 DETR 在遥感小目标上性能不佳，原因是小目标特征信息少、下采样导致进一步丢失、区域特征被背景淹没。
  - Transformer 检测器虽有上下文捕获优势，但 DETR 训练收敛慢，对小目标检测效果相对较差；两阶段 Deformable DETR 改进了收敛，但其区域提议基于二分类（前景/背景），不能区分具体实例，导致提议锚框包含多对象或仅部分对象，影响后续检测。
- **核心挑战**：如何增强小目标特征表示、抑制背景噪声、实现精确空间定位，从而提升遥感图像小目标检测性能。

## 2. 方法论：QO-DETR 的核心思想与关键技术
### 整体架构
- 以 ResNet 为骨干提取多尺度特征，经 Transformer 编码器增强后，由 **查询提议生成模块（QPG）** 产生初始位置嵌入，输入解码器；解码器采用 **查询级联优化策略（QCR）** 逐层细化锚框；训练时加入 **组去噪模块（GD）** 提高抗噪性；最终检测头输出分类和回归结果。
- 查询表示为 4D 动态锚框 `(x, y, w, h)` 与内容特征的组合，使用多尺度可变形注意力。

### 关键技术细节
1. **查询提议生成模块（QPG）**：
   - 对编码器输出的锚框查询，计算**多类分类分数**，选取分数最高的 Top-K 查询作为提议。
   - 仅用提议的锚框坐标初始化解码器对象查询的**位置嵌入**，而内容特征保持为可学习静态查询（与 DETR 一致），避免内容特征含混问题。
   - 优势：提供明确的位置先验，使解码器交叉注意力更快聚焦于对象区域，增强特征表示。

2. **组去噪模块（GD）**（仅训练阶段使用）：
   - 对每个真实框生成**正查询**（噪声尺度 ≤ λ₁）和**负查询**（λ₁ < 噪声尺度 ≤ λ₂）。
   - 正查询用于重建对应真实框；负查询预测“无对象”类别。
   - 使用多个去噪查询组（论文设为 100 组），通过**注意力掩码**防止不同组及匹配部分之间的信息泄露。
   - 损失：L1 和 GIOU 回归损失 + Focal Loss 分类损失。
   - 作用：迫使模型从含噪声的查询中恢复真实特征，减少匈牙利匹配的二义性，提升鲁棒性。

3. **查询级联优化策略（QCR）**：
   - 解码器第 i 层预测的偏移量 `Δb_i` 会更新两次：第一次得到当前层精炼框 `b'_i`，第二次与上一层的精炼框 `b'_{i-1}` 结合得到下一层的预测框 `b_{pred}^{i+1}`。
   - 具体更新公式（使用 sigmoid/反 sigmoid 函数），实现逐层空间对齐。
   - 优势：通过级联细化逐步纠正锚框偏移，提高小目标定位精度。

## 3. 实验设计
### 数据集与评价指标
| 数据集 | 图像数/实例数 | 对象类别数 | 图像大小 | 特点 |
|--------|--------------|-----------|---------|------|
| DIOR   | 23,463 张 / 192,472 实例 | 20 类 | 800×800 | >50% 实例为小目标 |
| AI-TOD | 28,036 张 / 700,621 实例 | 8 类 | 800×800 | 平均对象大小仅 12.8 像素，约 86% 实例 <16×16 像素 |

- 评价指标：AP（IoU=0.50:0.95）、AP₅₀、AP₇₅，以及按尺寸分级的 AP_S/AP_M/AP_L（AI-TOD 还细分 AP_VT、AP_T、AP_S、AP_M）。
- 对比方法：Faster R-CNN、SSD、RetinaNet、Cascade R-CNN、ATSS、M-CenterNet、DetectoRS+NWD、两阶段 Deformable DETR 等（涵盖主流 CNN 和 Transformer 检测器）。

### 实验设置
- 骨干网络：ResNet-50 / ResNet-101（预训练于 ImageNet）。
- Transformer 编码器 6 层，解码器 6 层，隐层维度 256，解码器查询数 900。
- 噪声尺度 λ₁=1.0, λ₂=2.0，去噪查询组 100 组（正/负各 100）。
- 优化器：AdamW，初始学习率 1×10⁻⁴，权重衰减 1×10⁻⁴，学习率在第 11 和 30 个 epoch 衰减。
- 损失权重：分类 1.0，L1 5.0，GIOU 2.0；Focal Loss 超参数 α=0.25, γ=2.0。

## 4. 资源与算力
- 文中明确说明：训练和推理均使用**单张 GeForce RTX 3090 GPU**，batch size 为 16。
- 训练 epoch 数：12 或 36（视具体实验配置）。
- **未明确提供**：总训练耗时、模型参数量、推理速度等细节。

## 5. 实验数量与充分性
### 主要实验组
1. **DIOR 数据集全量对比**（表 1、表 2）：与 6 种方法对比，报告 AP、AP₅₀、AP₇₅ 及按尺度和按类别的结果。
2. **AI-TOD 数据集全量对比**（表 3、表 4）：与 7 种方法对比，报告按尺度和按类别的详细 AP。
3. **消融实验**（表 5）：在 DIOR 上逐步替换/添加 QPG、GD、QCR，验证每个模块的贡献（12 epoch 训练）。
4. **不同骨干网络**：均使用 ResNet-50（消融和主要对比），且 AI-TOD 上也用了 ResNet-50，骨干对比较单一。
- **充分性评价**：
  - 两个大型遥感小目标数据集（DIOR 和 AI-TOD）覆盖了不同尺度和数量级。
  - 对比方法涵盖主流两阶段、单阶段及 Transformer 检测器，对比公平（使用相同骨干时均统一）。
  - 消融实验清晰验证了三个模块的有效性，AP 逐步提升约 50.5% → 51.3%，证明每个模块都有贡献。
  - **不足之处**：
    - 未在更多骨干（如 ResNet-101 / Swin-T）上展示对比结果（文中仅提 ResNet-50）。
    - 未报告推理速度/参数量，实用性分析不够。
    - 消融实验仅在 DIOR 上进行，未在 AI-TOD 上验证模块的跨数据集泛化。
    - 未与最新的遥感检测 Transformer（如 AO2-DETR）进行直接比较（AO2-DETR 仅在相关工作中提到）。

## 6. 主要结论与发现
- QO-DETR 在 DIOR 上达到 **AP 51.3%**，AP_S 13.4%，AP₅₀ 72.3%，显著优于两阶段 Deformable DETR（AP 46.4%）。
- 在 AI-TOD 上达到 **AP 23.6%**，AP_S 30.1%，AP₅₀ 57.6%，大幅超过此前最优的 DetectoRS+NWD（AP 20.8%）。
- 在 DIOR 的 20 个类别中有 14 个取得最佳 AP₅₀，在 AI-TOD 的所有 8 个类别均最优。
- 各模块（QPG、GD、QCR）均能有效提升性能，证明针对小目标的查询优化策略是有效的。

## 7. 优点
- **问题聚焦明确**：专门针对遥感图像小目标检测设计，抓住了“特征弱、噪声大、定位难”三大痛点。
- **方法创新性**：
  - 提出 QPG 利用多类分类分数筛选查询，避免二分类提议的歧义，且只初始化位置嵌入，保留内容特征的可学习性，设计合理。
  - GD 通过引入正/负噪声查询和分组注意力掩码，在不增加推理负担的情况下提升模型抗噪性，是一种有效的去噪训练技巧。
  - QCR 利用级联精炼方式，在相邻层之间传递精炼信息，提高了定位精度。
- **实验扎实**：在两个标准大规模遥感数据集上进行了全面对比和消融，结果先进且一致。
- **代码和资源要求低**：单卡 RTX 3090 即可训练，易于复现。

## 8. 不足与局限
- **骨干网络多样性不足**：仅报告了 ResNet-50 结果，未探索更强骨干或轻量骨干，通用性证据不够充分。
- **缺乏效率分析**：未提供 FLOPs、推理速度、模型参数量、显存占用等关键工程指标，难以评估实际部署可行性。
- **消融实验覆盖不全**：仅在 DIOR 上进行消融，未在 AI-TOD 上验证模块的跨数据集泛化能力；未探究不同噪声尺度 λ₁、λ₂ 的影响。
- **对比方法不够新**：缺少与 2023–2024 年最新的遥感检测 Transformer（如 AO2-DETR、YOLO 变体）的直接比较，结果可能已非 SOTA。
- **场景限制**：实验仅针对水平框标注的数据集（DIOR 和 AI-TOD），未评估任意方向目标检测能力，限制了在旋转目标场景的应用。
- **假设与偏差风险**：方法依赖多类分类分数筛选查询，当类别不平衡或未定义类别时可能效果下降；去噪模块中噪声尺度为固定经验值，场景变化时需调参。

（完）

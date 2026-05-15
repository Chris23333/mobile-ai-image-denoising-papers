# Mobile AI Image Denoising Papers

移动端 AI 影像去噪相关论文文献管理仓库，追踪公开论文、ArXiv 预印本、挑战赛报告和工程可迁移方案。

## 本次更新概览

- **更新日期**：2026-05-15
- **检索主题**：Mobile AI Image Denoising
- **数据源**：arXiv, Semantic Scholar, OpenAlex, Web Search
- **检索关键词**：mobile image denoising, raw image denoising, real image denoising, burst/multi-frame denoising, low-light denoising, neural ISP, efficient/lightweight restoration, noise level map, controllable denoising, quantization/deployment
- **本次收录**：9 篇新增论文
- **推荐精读**：#9, #12, #13（Priority A）
- **说明**：以下内容由自动检索与启发式评分生成，最终结论建议结合论文全文、官方代码和实机部署结果确认。

## 目录

- [2026 年论文](#2026)
- [2025 年论文](#2025)
- [经典论文](#classics)
- [关键词索引](#keywords)
- [更新日志](#changelog)

---

## 2026

### 1. Real Image Denoising with Knowledge Distillation for High-Performance Mobile NPUs

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2605.03680](https://arxiv.org/abs/2605.03680) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2605.03680) |
| **作者** | Faraz Kayani, Sarmad Kayani, Asad Ahmed, Radu Timofte, Dmitry Ignatov |
| **发布日期** | 2026-05-05 |
| **代码** | [NN-Dataset](https://github.com/ABrain-One/NN-Dataset) |
| **会议/挑战** | Mobile AI 2026 Challenge |
| **推荐等级** | A |
| **关键词** | NPU, 知识蒸馏, 硬件感知, 移动端去噪, LiteDenoiseNet |

**摘要**: 提出 NPU-aware 硬件-算法协同设计方案，用于移动端 NPU 上的真实图像去噪。使用高容量教师网络监督轻量级学生网络 (LiteDenoiseNet)，优先使用 NPU 原语（标准 3×3 卷积、ReLU 激活、最近邻上采样），在 MediaTek Dimensity 9500 上推理仅需 34.0ms，Qualcomm Snapdragon 8 Elite NPU 上 46.1ms。学生模型仅 1.96M 参数，通过 α=0.9 的知识蒸馏恢复教师网络 99.8% 的修复质量。

**关键贡献 / 可能价值**:
- NPU-aware 硬件-算法协同设计
- "推理反转"效应：严格遵循 NPU 兼容操作，NPU 执行速度比集成 GPU 快 3.88 倍
- 21.2 倍参数压缩，PSNR 差距仅 0.05 dB
- 工程关注点：NPU 原语约束的设计范式可直接迁移到移动端去噪模型开发

---

### 2. Mobile-friendly Image de-noising: Hardware Conscious Optimization for Edge Application

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2601.11684](https://arxiv.org/abs/2601.11684) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2601.11684) |
| **作者** | Srinivas Miriyala, Sowmya Vajrala, Hitesh Kumar, Sravanth Kodavanti, Vikram Rajendiran |
| **发布日期** | 2026-01-16 |
| **推荐等级** | A |
| **关键词** | NAS, 硬件感知, U-Net, Entropy Regularization, 边缘部署 |

**摘要**: 提出基于 Entropy-Regularized 可微分 NAS（Neural Architecture Search）的硬件感知 U-Net 架构搜索方法，用于移动端图像去噪。在 Samsung Galaxy S24 Ultra 上部署测试，参数减少 12%，设备延迟提升约 2 倍，内存占用减少 1.5 倍，PSNR 仅下降 0.7%。与 SwinIR 相比，GMACs 减少约 18 倍。

**关键贡献 / 可能价值**:
- 首个硬件感知可微分 NAS 用于 U-Net 去噪架构
- 在真实移动设备上验证部署性能
- 高斯去噪与真实世界去噪均表现良好
- 工程关注点：NAS 搜索空间设计可参考用于移动端去噪架构自动化

---

### 9. DRNet: All-in-One Image Restoration via Prior-Guided Dynamic Reparameterization

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2605.08627](https://arxiv.org/abs/2605.08627) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2605.08627) |
| **作者** | Ao Li, Xiaoning Liu, Sheng Li, Yapeng Du, Zhen Long, Lei Luo, Le Zhang, Ce Zhu |
| **发布日期** | 2026-05-09 |
| **代码** | [AVC2-UESTC/DRNet-AiO](https://github.com/AVC2-UESTC/DRNet-AiO) |
| **会议/期刊** | IEEE TMM 2026 |
| **推荐等级** | B |
| **关键词** | 全能图像恢复, 动态重参数化, 小波变换, 多任务, 去噪 |

**摘要**: 提出 Dynamic Reparameterization Network (DRNet)，一种基于初始化阶段重配置范式的全能图像恢复框架。核心组件 DRMLP 由 Task-Specific Modulator (TSM) 引导，有效缓解任务异构性。引入 Continuous Wavelet Transform Encoder (CWTE) 利用频域特征实现轻量化设计。在五项恢复任务上达到 SOTA 性能，且参数效率优越。

**关键贡献 / 可能价值**:
- 初始化阶段重配置范式，消除逐输入计算开销
- DRMLP + TSM 缓解多任务异构性
- CWTE 频域编码器，轻量化设计
- 工程关注点：动态重参数化可迁移到移动端多退化恢复场景；推理时无额外开销

---

### 10. Pre-training Enables Extraordinary All-optical Image Denoising

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2605.07810](https://arxiv.org/abs/2605.07810) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2605.07810) |
| **作者** | Xudong Lv, Yuxiang Sun, Shuo Wang, Nanxing Chen, Jun Guan, Jingtian Hu |
| **发布日期** | 2026-05-08 |
| **领域** | Physics > Optics, cs.CV |
| **推荐等级** | C |
| **关键词** | 光学神经网络, 衍射网络, 预训练, 全光去噪, 迁移学习 |

**摘要**: 报道了一种预训练驱动的全光图像去噪方法。通过两步过程优化衍射网络：先在 345 万张多样但简单的图像上预训练，再在特定任务数据集上微调。相比传统傅里叶域滤波和直接训练的衍射网络，该迁移学习过程在 PSNR 低于 8 dB 的严重噪声图像上表现突出，可将 PSNR 提升至 18 dB 以上。

**关键贡献 / 可能价值**:
- 预训练策略显著提升光学衍射网络去噪性能
- 单一预训练网络可微调处理多种图像风格
- 工程关注点：属于光学计算方向，非电子部署；但预训练+微调范式可启发传统深度去噪网络训练策略
- 风险提示：论文主要面向光学计算场景，与移动端 NPU/GPU 部署无直接关联

---

### 11. Energy-efficient Integer-only vs. Floating-point FLBMF Filters for Low-power Embedded Image Denoising

| 项目 | 内容 |
|------|------|
| **DOI** | [10.1038/s41598-026-51886-0](https://doi.org/10.1038/s41598-026-51886-0) |
| **PDF** | [下载链接](https://www.nature.com/articles/s41598-026-51886-0) |
| **作者** | Benard Nyangena Kiage, Michael W. Kimwele, Wilson K. Cheruiyot, Jael S. Wekesa |
| **发布日期** | 2026-05-11 |
| **期刊** | Scientific Reports (Springer Nature) |
| **推荐等级** | C |
| **关键词** | 整数量化, 低功耗, 嵌入式, FPGA, 模糊逻辑滤波, 脉冲噪声 |

**摘要**: 系统评估整数-only FLBM 和浮点 FLBMF 实现在去噪性能、计算成本和硬件效率之间的权衡。整数-only FLBMF 在 ARM Cortex-M7 微控制器上减少 40% 内存和 55% 执行时间，PSNR 差距仅 ≤0.5dB。在 FPGA 平台上，整数实现实现更低 DSP/LUT 利用率和功耗。

**关键贡献 / 可能价值**:
- 首次在 MCU 和 FPGA 平台上系统评估整数-only 与浮点去噪滤波器
- 量化隶属函数 + 定点运算 + 优化规则评估
- 工程关注点：整数量化思路可迁移到移动端 NPU 的 INT8 去噪模型部署；但论文主要针对医学影像脉冲噪声，与手机摄影高斯/Real噪声场景差异较大
- 风险提示：论文聚焦脉冲噪声 (impulse noise) 和医学影像，对移动端摄影去噪的直接参考价值有限

---

## 2025

### 3. DnLUT: Ultra-Efficient Color Image Denoising via Channel-Aware Lookup Tables

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2503.15931](https://arxiv.org/abs/2503.15931) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2503.15931) |
| **作者** | Sidi Yang, Binxiao Huang, Yulun Zhang, Dahai Yu, Yujiu Yang, Ngai Wong |
| **发布日期** | 2025-03-20 |
| **代码** | [Stephen0808/DnLUT](https://github.com/Stephen0808/DnLUT) |
| **会议** | CVPR 2025 |
| **推荐等级** | A |
| **关键词** | LUT, 通道感知, 轻量化, PCM, L 形卷积 |

**摘要**: 提出基于查找表（LUT）的超高效彩色图像去噪框架 DnLUT。核心组件包括 Pairwise Channel Mixer (PCM) 捕获通道间相关性和空间依赖，以及 L 形卷积设计最大化感受野覆盖。训练后转换为优化的查找表，仅需 500KB 存储，能耗仅为 DnCNN 的 0.1%，推理速度快 20 倍。在 PSNR 上超过所有现有 LUT 方法超过 1dB。

**关键贡献 / 可能价值**:
- PCM 模块：成对通道混合，并行捕获通道间相关性和空间依赖
- L 形卷积：最大化感受野，最小化存储开销
- 500KB 存储 + 0.1% 能耗的极致轻量化
- 工程关注点：LUT 方案天然适合移动端/NPU 部署，推理零计算，仅需查表

---

### 4. NTIRE 2025 Challenge on Efficient Burst HDR and Restoration

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2505.12089](https://arxiv.org/abs/2505.12089) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2505.12089) |
| **作者** | Sangmin Lee, Eunpil Park, Angel Canelo 等 (36 位作者) |
| **发布日期** | 2025-05-17 |
| **会议** | CVPR 2025 Workshop (NTIRE) |
| **推荐等级** | A |
| **关键词** | Burst HDR, 多帧融合, RAW, MFNR, 修复 |

**摘要**: NTIRE 2025 高效 Burst HDR 和修复挑战报告。基于新型 RAW 多帧融合数据集，每个场景包含 9 帧噪声和错位的 RAW 帧及不同曝光级别。参赛者需在严格效率约束下（<30M 参数，<4T FLOPs）开发多帧融合方案。冠军方案 PSNR 达 43.22 dB。

**关键贡献 / 可能价值**:
- 新型 RAW 多帧融合数据集
- 严格效率约束下的多帧 HDR 恢复
- 与 MFNR/RAWHDR 移动端流程高度相关
- 工程关注点：挑战赛方案可直接参考用于移动端多帧降噪/HDR 流程设计

---

### 5. AIM 2025 Challenge on Real-World RAW Image Denoising

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2510.06601](https://arxiv.org/abs/2510.06601) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2510.06601) |
| **作者** | Feiran Li, Jiacheng Li, Marcos V. Conde, Beril Besbinar, Vlad Hosu, Daisuke Iso, Radu Timofte |
| **发布日期** | 2025-10-08 |
| **会议** | AIM 2025 Workshop (ICCV) |
| **推荐等级** | A |
| **关键词** | RAW 去噪, 噪声合成, 低光, 相机无关 |

**摘要**: AIM 2025 真实世界 RAW 图像去噪挑战。基于新建立的评估基准，包含使用 5 台不同 DSLR 相机在野外拍摄的挑战性低光噪声图像。参与者需开发新颖的噪声合成管线、网络架构和训练方法。评估结合全参考指标（PSNR, SSIM, LPIPS）和无参考指标（ARNIQA, TOPIQ）。

**关键贡献 / 可能价值**:
- 多相机泛化性评估基准
- 推动基于合成数据训练的相机无关低光 RAW 去噪
- 噪声合成管线创新
- 工程关注点：相机无关的噪声合成方案对移动端 RAW 去噪训练数据准备有直接价值

---

### 6. Learned Smartphone ISP on Mobile GPUs, Mobile AI 2025 Challenge

| 项目 | 内容 |
|------|------|
| **来源** | [CVPR 2025 Workshop Paper](https://openaccess.thecvf.com/content/CVPR2025W/MAI/papers/Ignatov_Learned_Smartphone_ISP_on_Mobile_GPUs_Mobile_AI_2025_Challenge_CVPRW_2025_paper.pdf) |
| **作者** | Dmitry Ignatov, Radu Timofte 等 |
| **发布日期** | 2025-10 |
| **推荐等级** | B |
| **关键词** | ISP, 移动端 GPU, 学习型 ISP, 智能手机 |

**摘要**: Mobile AI 2025 挑战赛报告，参与者需设计能在移动 GPU 上快速推理的学习型 ISP 模型。提供大规模对齐的智能手机 RAW/DSLR 图像对数据集。

**关键贡献 / 可能价值**:
- 大规模对齐 RAW/DSLR 数据集
- 移动端 GPU 推理基准
- 工程关注点：学习型 ISP 与去噪模块的整合是移动端影像管线关键方向

---

### 12. Calibration-Free Raw Image Denoising via Fine-Grained Noise Estimation

| 项目 | 内容 |
|------|------|
| **DOI** | [10.1109/TPAMI.2025.3550264](https://doi.org/10.1109/TPAMI.2025.3550264) |
| **PDF** | [IEEE Xplore](https://ieeexplore.ieee.org/document/10938243) |
| **代码** | [SonyResearch/raw_image_denoising](https://github.com/SonyResearch/raw_image_denoising) |
| **作者** | Yunhao Zou, Ying Fu, Yulun Zhang, Tao Zhang, Chenggang Yan, Radu Timofte |
| **发布日期** | 2025-03 |
| **期刊** | IEEE TPAMI 2025 (Vol. 47, No. 7, pp. 5368-5384) |
| **推荐等级** | A |
| **关键词** | RAW 去噪, 噪声估计, 无校准, 噪声合成, 实用流程 |

**摘要**: 提出无需系统增益校准和信号无关噪声分析的细粒度噪声估计管线。仅通过收集暗帧即可在约一小时内完成噪声模型建立，将准备工作从数天缩短至数小时。集成细粒度统计噪声模型实现真实噪声合成，支持在正常和低光场景下有效去噪。发表在 IEEE TPAMI，代码已开源。

**关键贡献 / 可能价值**:
- 无校准的 RAW 噪声估计管线：仅需暗帧，从数天缩短至约 1 小时
- 细粒度统计噪声模型，实现高质量噪声合成
- 在正常和低光场景下均验证有效
- 工程关注点：可直接迁移到移动端 RAW 去噪训练数据准备流程；代码已开源，实用性强
- 风险提示：论文基于 Sony 相机数据验证，跨品牌泛化性需进一步确认

---

### 13. Towards Controllable Real Image Denoising with Camera Parameters

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2507.01587](https://arxiv.org/abs/2507.01587) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2507.01587) |
| **代码** | [OBAKSA/CPADNet](https://github.com/OBAKSA/CPADNet) |
| **作者** | Youngjin Oh, Junhyeong Kwon, Keuntek Lee, Nam Ik Cho |
| **发布日期** | 2025-07 |
| **推荐等级** | A |
| **关键词** | 可控去噪, 相机参数, ISO, 快门速度, 自适应降噪 |

**摘要**: 提出一种利用相机参数（ISO、快门速度、F 值）实现可控去噪的框架。将选定的相机参数转换为向量，控制和增强去噪网络的性能。实验表明该方法可无缝为标准去噪网络添加可控性，并提升其性能。代码已开源。

**关键贡献 / 可能价值**:
- 利用相机参数 (ISO, 快门速度, F 值) 实现去噪强度可控
- 可无缝添加到现有去噪网络架构
- 提升去噪性能的同时赋予用户控制力
- 工程关注点：相机参数向量可直接从手机 EXIF/ISP 元数据获取，对移动端自适应去噪具有极高工程价值；可作为噪声强度图的替代/补充方案
- 风险提示：需确认在手机端传感器参数与 DSLR 参数的映射关系

---

### 14. Learned Lightweight Smartphone ISP with Unpaired Data

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2505.10420](https://arxiv.org/abs/2505.10420) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2505.10420) |
| **代码** | [AndreiiArhire/Learned-Lightweight-Smartphone-ISP-with-Unpaired-Data](https://github.com/AndreiiArhire/Learned-Lightweight-Smartphone-ISP-with-Unpaired-Data) |
| **作者** | Andrei Arhire, Radu Timofte |
| **发布日期** | 2025-05-15 |
| **会议** | CVPR 2025 Workshop (Mobile AI) |
| **推荐等级** | A |
| **关键词** | 学习型 ISP, 无配对训练, 轻量化, 智能手机, 对抗训练 |

**摘要**: 提出一种无需配对 RAW-RGB 数据的轻量级学习型 ISP 训练方法。使用多判别器对抗训练和多损失函数引导，从预训练网络的特征图中维持内容结构，同时学习目标 RGB 数据集的颜色和纹理特征。在 Zurich RAW to RGB 和 Fujifilm UltraISP 数据集上评估，轻量化骨干网络适合移动设备部署。

**关键贡献 / 可能价值**:
- 消除 ISP 训练中对配对 RAW-RGB 数据的依赖
- 多判别器对抗训练维持结构与风格
- 轻量化架构适合移动端部署
- 工程关注点：无配对训练方案大幅降低数据准备成本；与移动端去噪模块可联合设计 ISP+Denoise 流程
- 风险提示：无配对训练的色准和细节保持需与配对方法对比确认

---

### 15. The Tenth NTIRE 2025 Image Denoising Challenge Report

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2504.12276](https://arxiv.org/abs/2504.12276) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2504.12276) |
| **作者** | Lei Sun, Hang Guo, Bin Ren, Luc Van Gool, Radu Timofte, Yawei Li 等 (93 位作者) |
| **发布日期** | 2025-04-16 |
| **会议** | CVPR 2025 Workshop (NTIRE) |
| **推荐等级** | B |
| **关键词** | 图像去噪, AWGN, 挑战赛, 高斯噪声, 基准 |

**摘要**: NTIRE 2025 图像去噪挑战赛 (σ=50) 报告。目标是开发在 PSNR 指标下实现高质量去噪的网络架构，无计算复杂度或模型大小约束。任务假设固定噪声水平 (σ=50) 的加性白高斯噪声 (AWGN)。共 290 位参与者注册，20 支团队提交有效结果。

**关键贡献 / 可能价值**:
- 提供当前 SOTA 去噪架构的系统性比较
- 290 参赛者 / 20 有效提交的竞赛规模
- 工程关注点：虽然基于 AWGN 与真实噪声差距大，但冠军方案的网络结构创新可迁移到 Real Noise 去噪
- 风险提示：AWGN σ=50 与移动端真实噪声场景差异显著，结论需谨慎迁移

---

### 16. Low-light Image Denoising with Learnable Diffusion Prior

| 项目 | 内容 |
|------|------|
| **DOI** | [10.1007/s11760-025-04444-6](https://doi.org/10.1007/s11760-025-04444-6) |
| **PDF** | [下载链接](https://link.springer.com/content/pdf/10.1007/s11760-025-04444-6.pdf) |
| **代码** | [drafly/LLIE_LDP](https://github.com/drafly/LLIE_LDP) |
| **作者** | Han, Wang 等 |
| **发布日期** | 2025-07 |
| **期刊** | Signal, Image and Video Processing (Springer) |
| **推荐等级** | B |
| **关键词** | 低光去噪, 扩散模型, RAW 图像, 噪声预测, 多任务学习 |

**摘要**: 提出首个集成噪声预测和去除的多任务扩散模型，用于低光 RAW 图像增强。设计交互模块自适应提取噪声和上下文信息，解决低光 RAW 图像中噪声非均匀性和与图像内容强重叠的问题。

**关键贡献 / 可能价值**:
- 首个噪声预测+去除联合扩散模型
- 交互模块处理噪声-内容重叠
- 工程关注点：扩散模型推理开销大，不适合移动端实时部署；但噪声预测模块和训练策略可迁移
- 风险提示：扩散模型推理速度慢，需多步采样，不适合移动端实时场景

---

### 17. Denoising as Adaptation: Noise-Space Domain Adaptation for Image Restoration

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2406.18516](https://arxiv.org/abs/2406.18516) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2406.18516) |
| **代码** | [KangLiao929/Noise-DA](https://github.com/KangLiao929/Noise-DA) |
| **作者** | Kang Liao, Zongsheng Yue, Zhouxia Wang, Chen Change Loy |
| **发布日期** | 2024-06 (accepted ICLR 2025) |
| **会议** | ICLR 2025 |
| **推荐等级** | B |
| **关键词** | 域适应, 噪声空间, 扩散损失, 合成-真实数据适配, 零推理开销 |

**摘要**: 首次在噪声空间中解决图像恢复的域适应问题。提出 anti-shortcut learning 策略，使扩散模型难以区分合成和真实条件，鼓励两者一致对齐到目标干净分布。扩散模型在训练后丢弃，零额外推理开销。

**关键贡献 / 可能价值**:
- 首次在噪声空间进行域适应，保留低级外观变化
- Anti-shortcut learning 策略促进合成-真实数据对齐
- 扩散模型训练后丢弃，零推理开销
- 工程关注点：合成数据训练+域适应策略对移动端去噪模型的训练数据准备有直接价值；零推理开销意味着不影响部署

---

## Classics

### 7. MFDNet: Lightweight Network Towards Real-Time Image Denoising on Mobile Devices

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2211.04687](https://arxiv.org/abs/2211.04687) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2211.04687) |
| **作者** | Zhuoqun Liu, Meiguind Jin, Ying Chen, Huaida Liu, Canqian Yang, Hongkai Xiong |
| **发布日期** | 2022-11-09 (修订 2023-05-25) |
| **代码** | [JL-DY/MFDNet](https://github.com/JL-DY/MFDNet) |
| **推荐等级** | A |
| **关键词** | 移动端去噪, MFA, RepConv, 内存访问成本, NPU 兼容 |

**摘要**: 识别影响 CNN 模型在移动设备运行时性能的真正瓶颈：内存访问成本和 NPU 不兼容操作。提出移动端友好的注意力模块 MFA 和模型重参数化模块 RepConv，在 SIDD 和 DND 基准上实现实时延迟下的 SOTA 去噪性能。

**关键贡献 / 可能价值**:
- 识别移动端延迟瓶颈：内存访问成本 + NPU 不兼容操作
- MFA 注意力模块：低延迟高性能
- RepConv 重参数化：训练推理解耦
- 工程关注点：内存访问成本分析框架可直接用于移动端去噪模型延迟优化

---

### 8. PMRID: Practical Deep Raw Image Denoising on Mobile Devices

| 项目 | 内容 |
|------|------|
| **代码** | [MegEngine/PMRID](https://github.com/MegEngine/PMRID) |
| **作者** | MegEngine 团队 |
| **会议** | ECCV 2020 |
| **推荐等级** | B |
| **关键词** | RAW 去噪, 移动端, 实用, MegEngine |

**摘要**: 轻量级、高效的基于神经网络的 RAW 图像去噪器，可在主流移动设备上流畅运行并产生高质量去噪结果。

**关键贡献 / 可能价值**:
- 移动端 RAW 去噪的早期奠基性工作
- MegEngine 框架优化移动端推理
- 工程关注点：轻量级 RAW 去噪基线模型，可作为新方法对比参照

---

## Keywords

| 关键词 | 相关论文 |
|--------|----------|
| NPU 部署 | #1, #2, #7 |
| 知识蒸馏 | #1 |
| NAS 架构搜索 | #2 |
| 查找表 (LUT) | #3 |
| 多帧融合 / Burst HDR | #4 |
| RAW 去噪 | #5, #7, #8, #12 |
| 移动端 GPU | #6 |
| 内存访问优化 | #1, #7 |
| 硬件感知设计 | #1, #2, #7 |
| 噪声合成 / 噪声估计 | #5, #12 |
| 可控去噪 | #13 |
| 相机参数 | #13 |
| 无配对训练 | #14 |
| 学习型 ISP | #6, #14 |
| 全能图像恢复 | #9 |
| 动态重参数化 | #9 |
| 域适应 | #17 |
| 扩散模型 | #16, #17 |
| 低光去噪 | #5, #16 |
| 整数量化 / 低功耗 | #11 |
| 光学去噪 | #10 |
| 高斯去噪基准 | #15 |

---

## 更新日志

- **2026-05-15**: 自动检索移动端 AI 影像去噪论文，新增 9 篇候选论文。检索源：arXiv, OpenAlex, Web Search。关键词覆盖 mobile/raw/real/burst/low-light/neural ISP/efficient restoration/controllable denoising/quantization。新增论文 #9-#17。
- **2026-05-15**: 初始版本，收集 8 篇移动端 AI 影像去噪相关论文

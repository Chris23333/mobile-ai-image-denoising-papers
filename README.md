# Mobile AI Image Denoising Papers

移动端 AI 影像去噪相关论文文献管理仓库，追踪 ArXiv 最新研究动态。

## 目录

- [2026 年论文](#2026)
- [2025 年论文](#2025)
- [经典论文](#classics)
- [关键词索引](#keywords)

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

**摘要**: 提出 NPU-aware 硬件-算法协同设计方案，用于移动端 NPU 上的真实图像去噪。使用高容量教师网络监督轻量级学生网络 (LiteDenoiseNet)，优先使用 NPU 原语（标准 3×3 卷积、ReLU 激活、最近邻上采样），在 MediaTek Dimensity 9500 上推理仅需 34.0ms，Qualcomm Snapdragon 8 Elite NPU 上 46.1ms。学生模型仅 1.96M 参数，通过 α=0.9 的知识蒸馏恢复教师网络 99.8% 的修复质量。

**关键贡献**:
- NPU-aware 硬件-算法协同设计
- "推理反转"效应：严格遵循 NPU 兼容操作，NPU 执行速度比集成 GPU 快 3.88 倍
- 21.2 倍参数压缩，PSNR 差距仅 0.05 dB

---

### 2. Mobile-friendly Image de-noising: Hardware Conscious Optimization for Edge Application

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2601.11684](https://arxiv.org/abs/2601.11684) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2601.11684) |
| **作者** | Srinivas Miriyala, Sowmya Vajrala, Hitesh Kumar, Sravanth Kodavanti, Vikram Rajendiran |
| **发布日期** | 2026-01-16 |

**摘要**: 提出基于 Entropy-Regularized 可微分 NAS（Neural Architecture Search）的硬件感知 U-Net 架构搜索方法，用于移动端图像去噪。在 Samsung Galaxy S24 Ultra 上部署测试，参数减少 12%，设备延迟提升约 2 倍，内存占用减少 1.5 倍，PSNR 仅下降 0.7%。与 SwinIR 相比，GMACs 减少约 18 倍。

**关键贡献**:
- 首个硬件感知可微分 NAS 用于 U-Net 去噪架构
- 在真实移动设备上验证部署性能
- 高斯去噪与真实世界去噪均表现良好

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

**摘要**: 提出基于查找表（LUT）的超高效彩色图像去噪框架 DnLUT。核心组件包括 Pairwise Channel Mixer (PCM) 捕获通道间相关性和空间依赖，以及 L 形卷积设计最大化感受野覆盖。训练后转换为优化的查找表，仅需 500KB 存储，能耗仅为 DnCNN 的 0.1%，推理速度快 20 倍。在 PSNR 上超过所有现有 LUT 方法超过 1dB。

**关键贡献**:
- PCM 模块：成对通道混合，并行捕获通道间相关性和空间依赖
- L 形卷积：最大化感受野，最小化存储开销
- 500KB 存储 + 0.1% 能耗的极致轻量化

---

### 4. NTIRE 2025 Challenge on Efficient Burst HDR and Restoration

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2505.12089](https://arxiv.org/abs/2505.12089) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2505.12089) |
| **作者** | Sangmin Lee, Eunpil Park, Angel Canelo 等 (36 位作者) |
| **发布日期** | 2025-05-17 |
| **会议** | CVPR 2025 Workshop (NTIRE) |

**摘要**: NTIRE 2025 高效 Burst HDR 和修复挑战报告。基于新型 RAW 多帧融合数据集，每个场景包含 9 帧噪声和错位的 RAW 帧及不同曝光级别。参赛者需在严格效率约束下（<30M 参数，<4T FLOPs）开发多帧融合方案。冠军方案 PSNR 达 43.22 dB。

**关键贡献**:
- 新型 RAW 多帧融合数据集
- 严格效率约束下的多帧 HDR 恢复
- 与 MFNR/RAWHDR 移动端流程高度相关

---

### 5. AIM 2025 Challenge on Real-World RAW Image Denoising

| 项目 | 内容 |
|------|------|
| **ArXiv ID** | [2510.06601](https://arxiv.org/abs/2510.06601) |
| **PDF** | [下载链接](https://arxiv.org/pdf/2510.06601) |
| **作者** | Feiran Li, Jiacheng Li, Marcos V. Conde, Beril Besbinar, Vlad Hosu, Daisuke Iso, Radu Timofte |
| **发布日期** | 2025-10-08 |
| **会议** | AIM 2025 Workshop (ICCV) |

**摘要**: AIM 2025 真实世界 RAW 图像去噪挑战。基于新建立的评估基准，包含使用 5 台不同 DSLR 相机在野外拍摄的挑战性低光噪声图像。参与者需开发新颖的噪声合成管线、网络架构和训练方法。评估结合全参考指标（PSNR, SSIM, LPIPS）和无参考指标（ARNIQA, TOPIQ）。

**关键贡献**:
- 多相机泛化性评估基准
- 推动基于合成数据训练的相机无关低光 RAW 去噪
- 噪声合成管线创新

---

### 6. Learned Smartphone ISP on Mobile GPUs, Mobile AI 2025 Challenge

| 项目 | 内容 |
|------|------|
| **来源** | [CVPR 2025 Workshop Paper](https://openaccess.thecvf.com/content/CVPR2025W/MAI/papers/Ignatov_Learned_Smartphone_ISP_on_Mobile_GPUs_Mobile_AI_2025_Challenge_CVPRW_2025_paper.pdf) |
| **作者** | Dmitry Ignatov, Radu Timofte 等 |
| **发布日期** | 2025-10 |

**摘要**: Mobile AI 2025 挑战赛报告，参与者需设计能在移动 GPU 上快速推理的学习型 ISP 模型。提供大规模对齐的智能手机 RAW/DSLR 图像对数据集。

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

**摘要**: 识别影响 CNN 模型在移动设备运行时性能的真正瓶颈：内存访问成本和 NPU 不兼容操作。提出移动端友好的注意力模块 MFA 和模型重参数化模块 RepConv，在 SIDD 和 DND 基准上实现实时延迟下的 SOTA 去噪性能。

**关键贡献**:
- 识别移动端延迟瓶颈：内存访问成本 + NPU 不兼容操作
- MFA 注意力模块：低延迟高性能
- RepConv 重参数化：训练推理解耦

---

### 8. PMRID: Practical Deep Raw Image Denoising on Mobile Devices

| 项目 | 内容 |
|------|------|
| **代码** | [MegEngine/PMRID](https://github.com/MegEngine/PMRID) |
| **作者** | MegEngine 团队 |
| **会议** | ECCV 2020 |

**摘要**: 轻量级、高效的基于神经网络的 RAW 图像去噪器，可在主流移动设备上流畅运行并产生高质量去噪结果。

---

## Keywords

| 关键词 | 相关论文 |
|--------|----------|
| NPU 部署 | #1, #2 |
| 知识蒸馏 | #1 |
| NAS 架构搜索 | #2 |
| 查找表 (LUT) | #3 |
| 多帧融合 / Burst HDR | #4 |
| RAW 去噪 | #5, #7, #8 |
| 移动端 GPU | #6 |
| 内存访问优化 | #1, #7 |
| 硬件感知设计 | #1, #2, #7 |
| 噪声合成 | #5 |

---

## 更新日志

- **2026-05-15**: 初始版本，收集 8 篇移动端 AI 影像去噪相关论文

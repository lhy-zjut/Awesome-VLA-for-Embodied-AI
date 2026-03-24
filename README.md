<div align="center">

<h1 align="center"><strong>基于视觉-语言-动作模型的具身智能研究进展</strong></h1>

<b>刘锐, 王文冠, 杨易<sup>*</sup></b>

<b>浙江大学计算机科学与技术学院</b>

<b><sup>*</sup>通讯作者</b>
</div>

## 🏠 About

具身智能作为人工智能与机器人学交叉的前沿领域，旨在使智能体通过与物理世界的动态交互来感知、推理并执行任务。本文按照模型内部 **推理与控制耦合方式** 的不同，对现有 VLA 方法进行整理。整体来看，VLA 研究已从早期的统一端到端建模，逐渐发展出强调推理-执行分离与多层决策分解的结构化范式。

## 🔍 Overview
- **[单系统VLA](#单系统VLA)**：采用统一网络直接完成视觉理解、语言对齐与动作输出，突出端到端建模能力。
- **[双系统VLA](#双系统VLA)**：将高层认知推理与低层动作控制拆分为两个协同模块，突出“慢思考 + 快执行”的结构优势。
- **[层次化系统VLA](#层次化系统VLA)**：通过多层决策结构显式建模任务规划、子目标分解与动作执行过程，突出长时程推理与复杂任务组织能力。

## 单系统VLA
<a id="单系统VLA"></a>

| 方法 | 论文标题 | 发表期刊或会议 | 年份 | 论文 | 代码 |
|---|---|---|---:|---|---|
| RT-2 | RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control | CoRL | 2023 | [Paper](https://arxiv.org/abs/2307.15818) | - |
| RT-2-X | Open X-Embodiment: Robotic Learning Datasets and RT-X Models | ICRA | 2024 | [Paper](https://arxiv.org/abs/2310.08864) | - |
| OpenVLA | OpenVLA: An Open-Source Vision-Language-Action Model | CoRL | 2024 | [Paper](https://arxiv.org/abs/2406.09246) | [GitHub](https://github.com/openvla/openvla) |
| LEO | An Embodied Generalist Agent in 3D World | ICML | 2024 | [Paper](https://proceedings.mlr.press/v235/huang24i.html) | [GitHub](https://github.com/embodied-generalist/embodied-generalist) |
| EcoVLA | Environment-Aware Adaptive Pruning with Interleaved Inference Orchestration for Vision-Language-Action Models | arXiv | 2025 | [Paper](https://arxiv.org/abs/2602.00780) | - |
| ReVLA | ReVLA: Reverting Visual Domain Limitation of Robotic Foundation Models | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.15250) | - |
| TraceVLA | TraceVLA: Visual Trace Prompting Enhances Spatial-Temporal Awareness for Generalist Robotic Policies | ICLR | 2025 | [Paper](https://openreview.net/forum?id=jnpIL.Gz9gQ) | [GitHub](https://github.com/umd-huang-lab/tracevla) |
| Fuse | Beyond Sight: Finetuning Generalist Robot Policies with Heterogeneous Sensors via Language Grounding | ICRA | 2025 | [Paper](https://doi.org/10.1109/ICRA55743.2025.11127987) | - |
| UniAct | Universal Actions for Enhanced Embodied Foundation Models | CVPR | 2025 | [Paper](https://doi.org/10.1109/CVPR52734.2025.02096) | - |
| SpatialVLA | SpatialVLA: Exploring Spatial Representations for Visual-Language-Action Model | arXiv | 2025 | [Paper](https://arxiv.org/abs/2501.15830) | - |
| RoboFlamingo | RoboFlamingo: Decoupled Action Decoding for Real-World Robotic Control | arXiv | 2024 | [Paper](https://arxiv.org/abs/2412.05277) | [GitHub](https://github.com/RoboFlamingo/RoboFlamingo) |
| RoboMamba | RoboMamba: Efficient Vision-Language-Action Model for Robotic Reasoning and Manipulation | NeurIPS | 2024 | [Paper](https://arxiv.org/abs/2406.05246) | [GitHub](https://github.com/lmzpai/roboMamba) |
| OpenVLA-OFT | Fine-Tuning Vision-Language-Action Models: Optimizing Speed and Success | arXiv | 2025 | [Paper](https://arxiv.org/abs/2502.19645) | [GitHub](https://github.com/moojink/openvla-oft) |
| Spec-VLA | Spec-VLA: Speculative Decoding for Vision-Language-Action Models with Relaxed Acceptance | EMNLP | 2025 | [Paper](https://arxiv.org/abs/2507.22424) | [GitHub](https://github.com/PineTreeWss/SpecVLA) |
| FlashVLA | Interactive Post-Training for Vision-Language-Action Models | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.17016) | - |
| CogVLA | CogVLA: Cognition-Aligned Vision-Language-Action Model via Instruction-Driven Routing & Sparsification | NeurIPS | 2025 | [Paper](https://arxiv.org/abs/2508.21046) | [GitHub](https://github.com/JiuTian-VL/CogVLA) |
| UnifiedVLA | Unified Diffusion VLA: Vision-Language-Action Model via Joint Discrete Denoising Diffusion Process | ICLR | 2026 | [Paper](https://openreview.net/forum?id=UvQOcw2oCD) | [GitHub](https://github.com/OpenHelix-Team/Unified-Diffusion-VLA) |
| PD-VLA | Accelerating Vision-Language-Action Model Integrated with Action Chunking via Parallel Decoding | arXiv | 2025 | [Paper](https://arxiv.org/abs/2503.02310) | - |
| 4D-VLA | 4D-VLA: Vision-Language-Action Spatiotemporal Pretraining with Cross-Scene Calibration | arXiv | 2025 | [Paper](https://arxiv.org/abs/2506.22242) | - |
| OE-VLA | Unveiling the Potential of Vision-Language-Action Models with Open-Ended Multimodal Instructions | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.11214) | - |
| ST-VLA | Spatial Traces: Enhancing VLA Models with Spatial-Temporal Understanding | arXiv | 2025 | [Paper](https://arxiv.org/abs/2508.09032) | - |
| VLAS | VLAS: Vision-Language-Action-Speech Model for Auditory-Augmented Manipulation | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.11103) | - |
| DeeR-VLA | DeeR-VLA: Dynamic Inference of Multimodal Large Language Models for Efficient Robot Execution | NeurIPS | 2024 | [Paper](https://arxiv.org/abs/2410.19237) | [GitHub](https://github.com/yueyang130/DeeR-VLA) |
| BitVLA | BitVLA: 1-bit Vision-Language-Action Models for Robotics Manipulation | arXiv | 2025 | [Paper](https://arxiv.org/abs/2506.07530) | [GitHub](https://github.com/ustcwhy/BitVLA) |
| Mole-VLA | MoLe-VLA: Dynamic Layer Routing for Multimodal Reasoning | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.09221) | [GitHub](https://github.com/RoyZry98/MoLe-VLA-Pytorch/) |

## 双系统VLA
<a id="双系统VLA"></a>

| 方法 | 论文标题 | 发表期刊或会议 | 年份 | 论文 | 代码 |
|---|---|---|---:|---|---|
| DP-VLA | A Dual Process VLA: Efficient Robotic Manipulation Leveraging VLM | arXiv | 2024 | [Paper](https://arxiv.org/abs/2410.15549) | - |
| RoboDual | Towards Synergistic, Generalized, and Efficient Dual-System for Robotic Manipulation | arXiv | 2024 | [Paper](https://arxiv.org/abs/2410.08001) | - |
| LCB | From LLMs to Actions: Latent Codes as Bridges in Hierarchical Robot Control | arXiv / IROS | 2024 | [Paper](https://arxiv.org/abs/2405.04798) | - |
| GR00T N1 | GR00T N1: An Open Foundation Model for Generalist Humanoid Robots | arXiv | 2025 | [Paper](https://arxiv.org/abs/2503.14734) | [GitHub](https://github.com/NVIDIA/Isaac-GR00T) |
| CogAct | CogACT: A Foundational Vision-Language-Action Model for Synergizing Cognition and Action in Robotic Manipulation | arXiv | 2024 | [Paper](https://arxiv.org/abs/2411.19650) | [GitHub](https://github.com/microsoft/CogACT) |
| HiRT | HiRT: Enhancing Robotic Control with Hierarchical Robot Transformers | CoRL | 2024 | [Paper](https://arxiv.org/abs/2410.05273) | - |
| Fast-in-Slow | Fast-in-Slow: A Dual-System Foundation Model Unifying Fast Manipulation within Slow Reasoning | arXiv | 2025 | [Paper](https://arxiv.org/abs/2506.01953) | - |
| OpenHelix | OpenHelix: A Short Survey, Empirical Analysis, and Open-Source Dual-System VLA Model for Robotic Manipulation | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.03912) | [GitHub](https://github.com/OpenHelix-Team/OpenHelix) |
| ChatVLA | ChatVLA: Unified Multimodal Understanding and Robot Control with Vision-Language-Action Model | arXiv | 2025 | [Paper](https://arxiv.org/abs/2502.14420) | - |
| Diffusion-VLA | Diffusion-VLA: Generalizable and Interpretable Robot Foundation Model via Self-Generated Reasoning | arXiv | 2024 | [Paper](https://arxiv.org/abs/2412.03293) | - |
| TriVLA | TriVLA: Triple-Stream Vision-Language-Action Model for Future-Frame Prediction and Control | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.09133) | - |
| GF-VLA | GF-VLA: Graph-Fused Vision-Language-Action Model for Interpretable Bimanual Manipulation | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.08356) | - |
| RationalVLA | RationalVLA: A Rational Vision-Language-Action Model with Dual System | arXiv | 2025 | [Paper](https://arxiv.org/abs/2506.10826) | - |
| VQ-VLA | VQVLA: Residual Quantization for Robotic Action Representation Learning | arXiv | 2024 | [Paper](https://arxiv.org/abs/2408.10422) | - |
| TinyVLA | TinyVLA: Towards Fast, Data-Efficient Vision-Language-Action Models for Robotic Manipulation | IEEE RAL | 2025 | [Paper](https://ieeexplore.ieee.org/document/10900471/) | [GitHub](https://github.com/JayceWen/tinyvla) |
| pi0 系列 | π0: A Vision-Language-Action Flow Model for General Robot Control | arXiv | 2024 | [Paper](https://arxiv.org/abs/2410.24164) | - |
| ForceVLA | ForceVLA: Enhancing VLA Models with a Force-Aware MoE for Contact-Rich Manipulation | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.22159) | [GitHub](https://github.com/ft-robotic/ForceVLA) |
| SmolVLA | SmolVLA: A Vision-Language-Action Model for Affordable and Efficient Robotics | arXiv | 2025 | [Paper](https://arxiv.org/abs/2506.01844) | [GitHub](https://github.com/huggingface/VLAb) |
| GR-3 | GR-3: Technical Report | arXiv | 2025 | [Paper](https://arxiv.org/abs/2507.15493) | - |
| Villa-X | Villa-X: Structured Vision-Action Fusion via Joint Diffusion Modeling | arXiv | 2025 | [Paper](https://arxiv.org/abs/2504.07122) | - |
| GraspVLA | GraspVLA: a Grasping Foundation Model Pre-trained on Billion-scale Synthetic Action Data | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.03233) | [GitHub](https://github.com/PKU-EPIC/GraspVLA) |

## 层次化系统VLA
<a id="层次化系统VLA"></a>

| 方法 | 论文标题 | 发表期刊或会议 | 年份 | 论文 | 代码 |
|---|---|---|---:|---|---|
| MomanipVLA | MoManipVLA: Transferring Vision-Language-Action Models for General Mobile Manipulation | CVPR | 2025 | [Paper](https://doi.org/10.1109/CVPR42601.2025.98504) | - |
| ManipLVLM-R1 | ManipLVM-R1: Reinforcement Learning for Reasoning in Embodied Manipulation with Large Vision-Language Models | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.16517) | - |
| PaLM-E | PaLM-E: An Embodied Multimodal Language Model | ICML | 2023 | [Paper](https://arxiv.org/abs/2303.03378) | - |
| Embodied-Reasoner | Embodied-Reasoner: Synergizing Visual Search, Reasoning, and Action for Embodied Interactive Tasks | arXiv | 2025 | [Paper](https://arxiv.org/abs/2503.21696) | [GitHub](https://github.com/zwq2018/embodied_reasoner) |
| RoboPoint | RoboPoint: A Vision-Language Model for Spatial Affordance Prediction in Robotics | CoRL | 2024 | [Paper](https://proceedings.mlr.press/v270/yuan25c.html) | [GitHub](https://github.com/wentaoyuan/RoboPoint) |
| Reinforced Planning | Reinforced Reasoning for Embodied Planning | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.22050) | [GitHub](https://github.com/mail-taii/Reinforced-Reasoning-for-Embodied-Planning) |
| CoM | Chain-of-Modality: Learning Manipulation Programs from Multimodal Human Videos with Vision-Language-Models | ICRA | 2025 | [Paper](https://doi.org/10.1109/ICRA55743.2025.11128270) | - |
| RoVI | RoVI: Programmatic Representation for Implicit Action Modeling | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.19011) | - |
| ReLEP | ReLEP: A Novel Framework for Real-world Long-horizon Embodied Planning | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.15658) | - |
| VILA | Look Before You Leap: Unveiling the Power of GPT-4V in Robotic Vision-Language Planning | arXiv | 2023 | [Paper](https://arxiv.org/abs/2311.17842) | - |
| RoboBrain | RoboBrain: A Unified Brain Model for Robotic Manipulation from Abstract to Concrete | CVPR | 2025 | [Paper](https://doi.org/10.1109/CVPR52734.2025.00168) | [GitHub](https://github.com/FlagOpen/RoboBrain) |
| HiRobot | Hi Robot: Open-Ended Instruction Following with Hierarchical Vision-Language-Action Models | arXiv | 2025 | [Paper](https://arxiv.org/abs/2502.19417) | - |
| DexVLA | DexVLA: Hierarchical Diffusion Planner for Long-Horizon Robotic Tasks | arXiv | 2025 | [Paper](https://arxiv.org/abs/2503.09123) | [GitHub](https://github.com/juruobenruo/DexVLA) |
| Instruct2Act | Instruct2Act: Mapping Multi-modality Instructions to Robotic Actions with Large Language Model | arXiv | 2023 | [Paper](https://arxiv.org/abs/2305.11176) | [GitHub](https://github.com/OpenGVLab/Instruct2Act) |
| RoboMatrix | RoboMatrix: A Skill-centric Hierarchical Framework for Scalable Robot Task Planning and Execution in Open-World | arXiv | 2024 | [Paper](https://arxiv.org/abs/2412.00171) | [GitHub](https://github.com/WayneMao/RoboMatrix) |
| PointVLA | PointVLA: Injecting the 3D World into Vision-Language-Action Models | arXiv | 2025 | [Paper](https://arxiv.org/abs/2503.07511) | - |
| A0 | A0: Ontology-Free Affordance Representation for Cross-Embodiment Transfer | arXiv | 2024 | [Paper](https://arxiv.org/abs/2406.25250) | [GitHub](https://github.com/A-embodied/A0) |
| RoBridge | RoBridge: A Hierarchical Architecture Bridging Cognition and Execution for General Robotic Manipulation | arXiv | 2025 | [Paper](https://arxiv.org/abs/2505.01709) | [GitHub](https://github.com/abliao/RoBridge) |
| RT-H | RT-H: Action Hierarchies Using Language | RSS | 2024 | [Paper](https://arxiv.org/abs/2403.01823) | - |
| ReKep | ReKep: Spatio-Temporal Reasoning of Relational Keypoint Constraints for Robotic Manipulation | arXiv | 2024 | [Paper](https://arxiv.org/abs/2409.01652) | [GitHub](https://github.com/huangwl18/ReKep) |
| HiBerNAC | HiBerNAC: Asynchronous Hierarchical Multi-Agent Coordination | arXiv | 2025 | [Paper](https://arxiv.org/abs/2502.02102) | - |
| LLARVA | LLARVA: Vision-Action Instruction Tuning Enhances Robot Learning | CoRL | 2024 | [Paper](https://proceedings.mlr.press/v270/niu25a.html) | [GitHub](https://github.com/Dantong88/LLARVA) |
| VLA-Touch | VLA-Touch: Enhancing Vision-Language-Action Models with Dual-Level Tactile Feedback | arXiv | 2025 | [Paper](https://arxiv.org/abs/2507.17294) | [GitHub](https://github.com/jxbi1010/VLA-Touch) |

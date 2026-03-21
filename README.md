## 表1 不同动作词元解码建模方式对比

| 建模方式 | 优势 | 劣势 | 适用场景 |
|---|---|---|---|
| 离散化词元 | 泛化性强，零样本迁移能力突出，推理较快 | 存在精度误差，长序列影响输出频率 | 指令跟随、移动导航 |
| 连续回归 | 输出轨迹平滑，精度较高，推理高效 | 难以建模复杂动作分布，泛化能力弱 | 精确轨迹跟踪、动态的连续控制任务 |
| 扩散模型 | 能建模复杂动作分布，策略鲁棒，训练稳定 | 推理慢，计算开销大 | 复杂抓取操控、精细装配 |
| 流匹配 | 推理效率高，平衡表达能力与效率 | 训练数据质量要求高 | 对实时性有要求的操作任务 |

## 表2 基于扩散策略和流匹配的 VLA 性能对比

| 方法 | Push-T 动作模仿平均分数 | Push-T 延迟 | RoboMimic Square 动作模仿平均分数 | RoboMimic Square 延迟 |
|---|---:|---:|---:|---:|
| 扩散策略（Chi 等，2025） | 87.0% | 127.2ms | 77.2% | 53.4ms |
| 流匹配策略（Zhang 等，2024） | 71.0% | 12.9ms | 54.0% | 4.8ms |

## 表3 单系统模型 VLA 方法及其特点

| 方法 | 语言模型 | 视觉编码器 | 学习方式 | 特点 |
|---|---|---|---|---|
| RT-2（Zitkovich 等，2022） | PaLM-E | - | 模仿学习（连续动作）+ 微调（离散动作） | 将动作表征为 VLM 词元以实现泛化 |
| RT-2-X（O'Neill 等，2024） | LLaMA2 | ViT-22B | 模仿学习（连续动作）+ 微调（离散动作） | 跨机器人数据微调以实现模型迁移 |
| OpenVLA（Kim 等，2024） | LLaMA2-7B | DINOv2 + SigLIP | 模仿学习（连续动作） | 开源 7B 参数 VLA 实现通用机器人控制 |
| LEO（Huang 等，2024） | Vicuna-7B | ConvNext | 模仿学习（连续动作）+ 微调（离散动作） | 结合三维特征与 LLM 用于动作决策 |
| EcoVLA（Chen 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 模仿学习（连续动作）+ 微调（离散动作） | 融入思维链以增强策略可解释性 |
| ReVLA（Dey 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 模仿学习（连续动作） | 反向回溯到策略执行提升可解释性 |
| TraceVLA（Zheng 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 模仿学习（连续动作） | 利用视觉轨迹提示实现跨模态时间感知 |
| Fuse（Jones 等，2025） | PaLM-Gemma-3B | - | 模仿学习（连续动作）+ 微调（离散动作） | 使用自然语言用于跨模态微调 |
| UniAct（Zheng 等，2025） | LLaVA-0.5B | SigLIP ViT-L | 策略蒸馏（连续动作） | 提出通用动作空间实现自适应控制 |
| SpatialVLA（Qu 等，2025） | Gemini | - | 模仿学习（连续动作） | 通过三维语义和动作网格改进泛化 |
| RoboFlamingo（Li 等，2024） | MPT-1B | ViT | 模仿学习（连续动作）+ 微调（离散动作） | 适配开源 VLM 用于机器人控制 |
| RoboMamba（Liu 等，2024） | Mamba-2.8B | CLIP/SigLIP ViT-L | 模仿学习（连续动作）+ 微调（离散动作） | 将 Mamba 架构引入 VLA 领域 |
| OpenVLA-OFT（Kim 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 策略蒸馏（连续动作） | 通过 OpenVLA 蒸馏提升性能 |
| Spec-VLA（Wang 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 策略蒸馏（连续动作） | 在解码阶段进行加速，实现无损推理 |
| FlashVLA（Tan 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 模仿学习（连续动作） | 训练加速并提升 VLA 推理效率 |
| CogVLA（Li 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 策略蒸馏（连续动作） | 提出认知对齐框架以实现高效操作 |
| UnifiedVLA（Wang 等，2025） | Emu | - | 模仿学习（连续动作）+ 微调（离散动作） | 将输入信号转换为词元构建统一模型 |
| PD-VLA（Song 等，2025） | Vicuna-1.5B | CLIP ViT-L | 策略蒸馏（连续动作） | 增强基于蒸馏的快速机器人控制并行 |
| 4D-VLA（Zhang 等，2025） | InternVL-1.4B | - | 策略蒸馏（连续动作） | 整合时空线索实现高效 VLA 预训练 |
| OE-VLA（Zhao 等，2025） | Qwen1.5-5B | - | 模仿学习（连续动作）+ 微调（离散动作） | 为开放末端任务引入跨模态交互 |
| ST-VLA（Patratskiy 等，2025） | PalGemma2 | - | 模仿学习（连续动作）+ 微调（离散动作） | 将视觉轨迹投影到深度图增强理解 |
| VLAS（Zhao 等，2025） | Vicuna-7B | CLIP ViT-L | 模仿学习（连续动作）+ 微调（离散动作） | 引入双模态自编码器并构建配对数据集 |
| DeeR-VLA（Yue 等，2024） | MPT-1B / 7B | CLIP ViT-L | 策略蒸馏（连续动作） | 提出动态早退出以减少推理开销 |
| BitVLA（Wang 等，2025） | BitNet1.5 8B | SigLIP ViT-L | 策略蒸馏（连续动作）+ 微调（离散动作） | 设计权重模型以减少部署内存成本 |
| Mole-VLA（Zhang 等，2025） | LLaMA2-7B | DINOv2 + SigLIP | 策略蒸馏（连续动作） | 通过动态模型层激活减少计算量 |

## 表4 双系统模型 VLA 方法及其特点

| 方法 | System2 骨干网络 | System1 学习方式 | 特点 |
|---|---|---|---|
| DP-VLA（Han 等，2024） | OpenVLA | 回归（Regressive） | 提出双系统架构用于机器人操作 |
| RoboDual（Bu 等，2024） | OpenVLA | 可微分（Diffusion-based） | 引入用于控制的 DiT 专家模型 |
| LCB（Shentu 等，2024） | LLaVA | 可微分（Diffusion-based） | 新增特殊词元编码并作为策略条件 |
| GR00T N1（Bjorck 等，2024） | Eagle-2 | 流匹配（Flow-matching） | 结合 VLM 和 DiT 用于人形机器人操作 |
| CogAct（Li 等，2024） | OpenVLA | 可微分（Diffusion-based） | 将动作扩散过程融入 VLA |
| HiRT（Zhang 等，2025） | InstructCLIP | 回归（Regressive） | 提出双系统模型，System 2 以较低频率运行 |
| Fast-in-Slow（Chen 等，2025） | Prismatic | 可微分（Diffusion-based）、自回归（Autoregressive） | 在基于 VLM 的推理器中提高执行效率 |
| OpenHelix（Cui 等，2025） | LLaVA | 可微分（Diffusion-based） | 对连接 VLM 和策略的词元进行辅助训练 |
| ChatVLA-1（Zhou 等，2025） | Qwen2-VL | 可微分（Diffusion-based） | 用于独立感知和控制的共享注意力机制 |
| ChatVLA-2（Zhou 等，2025） | Qwen2-VL | 可微分（Diffusion-based） | 动态路由和开放世界机器人推理 |
| Diffusion-VLA（Wen 等，2025） | Qwen2-VL | 可微分（Diffusion-based） | 通过 FiLM 将 Qwen2-VL 推理与扩散动作融合 |
| TriVLA（Liu 等，2025） | Eagle-2 | 可微分（Diffusion-based） | 将动力学感知模块作为 System 3 补充静态感知 |
| GF-VLA（Li 等，2025） | LLaVA-v1.5 | 回归（Regressive） | 通过人类视频的信息实现可解释的双手操作 |
| RationalVLA（Song 等，2025） | LLaMA2 | 可微分（Diffusion-based） | 引入可学习的隐式接口，实现鲁棒操作 |
| VQ-VLA（Jones 等，2025） | OpenVLA | 变分自编码器（VQ-VAE） | 引入向量量化的动作词元，实现平滑的控制 |
| TinyVLA（Wen 等，2025） | LLaVA | 可微分（Diffusion-based） | 证明高性能 VLA 无需大规模机器人预训练 |
| pi0（Black 等，2025） | PaliGemma | 流匹配（Flow-matching） | 结合 VLM 和基于流匹配的动作专家模型 |
| pi0-FAST（Pertsch 等，2025） | pi0 | 自回归（Autoregressive） | 提出基于 DCT 的动作词元，高效自回归训练 |
| pi0.5（Black 等，2025） | PaliGemma | 流匹配（Flow-matching） | 将高层提示转换为更细粒度的子任务预测 |
| ForceVLA（Yu 等，2025） | pi0 | 可微分（Diffusion-based） | 通过混合专家模型处理力传感模态信息 |
| SmolVLA（Shukor 等，2025） | SmolVLM-2 | 流匹配（Flow-matching） | 采用 SmolVLM-2 和流匹配构建轻量级 VLA |
| GR-3（Cheang 等，2025） | Qwen2.5-VL | 流匹配（Flow-matching） | 结合 VLM 数据和少量轨迹标注，实现鲁棒操作 |
| Villa-X（Chen 等，2025） | PaliGemma | 流匹配（Flow-matching） | 在扩散过程中集成本体感知隐变量信息 |
| GraspVLA（Deng 等，2025） | InternLM2 | 流匹配（Flow-matching） | 利用合成数据实现仿真到开放世界的抓取 |

## 表5 层次化系统模型 VLA 方法及其特点

| 方法 | 骨干网络 | 学习方式 | 特点 |
|---|---|---|---|
| MomanipVLA（Wu 等，2025） | OpenVLA-7B | 模仿学习（IM） | 预测路径点并优化全身轨迹 |
| ManipLVLM-R1（Song 等，2025） | Qwen2.5-VL-3B | 强化学习（RL） | 对轨迹进行 GRPO 调优，分布外场景中表现鲁棒 |
| PaLM-E（Driess 等，2023） | PaLM | 监督微调（SFT） | 训练具备通用机器人操作指令生成能力的 VLM |
| Embodied-Reasoner（Zhang 等，2025） | Qwen2-VL-7B | 监督微调（SFT） | 构建 VLM 和开源数据集用于规划、推理和反思 |
| RoboPoint（Yuan 等，2024） | Vicuna-v1.5-13B | 监督微调（SFT） | 以路径点形式实现 VLM 空间感知决策 |
| Reinforced Planning（Wu 等，2025） | Qwen2.5-VL-7B | 监督微调（SFT）、强化学习（RL） | 在微调模型上进行 GRPO，提升泛化能力 |
| CoM（Wang 等，2025） | Gemini 1.5 Pro | API | 从演示中通过序列多模态提示提取力感知操作 |
| RoVI（Li 等，2025） | GPT-4 / LLaVA-13B | 监督微调（SFT） | 通过层次化结构实现精确操作 |
| ReLEP（Liu 等，2024） | LLaVA-1.6-7B | 监督微调（SFT） | 具有隐式逻辑推理和幻觉缓解的规划框架 |
| ViLA（Hu 等，2023） | GPT-4V | API | 提供感知、推理集成的规划器 |
| RoboBrain（Ji 等，2025） | LLaVA | 监督微调（SFT） | 设计规划、可操作性和轨迹的层次化 VLA |
| HiRobot（Shi 等，2025） | PaliGemma-3B / pi0 | 监督微调（SFT）、模仿学习（IM） | 具有可解释性和复杂任务处理能力 |
| DexVLA（Wen 等，2025） | Qwen2-VL | 监督微调（SFT）、模仿学习（IM） | 结合 VLM 和扩散模块，采用 3 阶段训练方案 |
| Instruct2Act（Huang 等，2023） | ChatGPT | 监督微调（SFT） | 生成调用 API 的程序，实现从指令到动作的映射 |
| RoboMatrix（Mao 等，2024） | Vicuna-v1.5 | 监督微调（SFT）、模仿学习（IM） | 具有模块化调度层、技能层和硬件层的 VLA |
| PointVLA（Li 等，2025） | Qwen2-VL | API | 附加点云编码器以获得空间感知 |
| A₀（Xu 等，2025） | Qwen2.5-7B | 监督微调（SFT）、API | 具有关键点预测的分层扩散模块 |
| RoBridge（Zhang 等，2025） | GPT-4o | 模仿学习（IM）、强化学习（RL） | 通过 VLM 与 RL 动作预测，提高模型迁移性 |
| RT-H（Belkhale，2024） | PaLI-X 55B | 监督微调（SFT）、模仿学习（IM） | 动作层次结构，使用语言驱动的动作表征 |
| ReKep（Huang 等，2024） | GPT-4o | API | 通过关键点约束实现无训练的操作轨迹生成 |
| HiBerNAC（Wu 等，2025） | PaLM2 | 监督微调（SFT） | 提出模仿大脑分层结构的异步模型 |
| LLARVA（Niu 等，2024） | Llama2 7B | 监督微调（SFT）、模仿学习（IM） | 视觉—动作指令调优，结合大型指令调优数据集 |
| VLA-Touch（Bi 等，2025） | GPT-4o | 模仿学习（IM） | 基于扩散的模仿学习将触觉传感集成到 VLA 中 |

## 表6 不同 VLA 方法在 LIBERO 数据集的性能

| 模型 | 参数量 | Spatial | Object | Goal | Long |
|---|---:|---:|---:|---:|---:|
| Diffusion Policy（Chi 等，2025） | - | 78.3 | 92.5 | 68.3 | 50.5 |
| MaIL（Jia 等，2024） | 24.7M | 74.3 | 90.1 | 81.8 | 78.6 |
| MDT（Reuss 等，2024） | 75M | 78.5 | 87.5 | 73.5 | 64.8 |
| Octo（Ghosh 等，2024） | 93M | 78.9 | 85.7 | 84.6 | 51.1 |
| VLA-OS（Gao 等，2025） | 0.5B | 87.0 | 96.5 | 92.7 | 66.0 |
| VLA-Adapter（Wang 等，2025） | 0.5B | 97.8 | 99.2 | 97.2 | 95.0 |
| GraspVLA（Liu 等，2025） | 1.8B | - | 94.1 | 91.2 | 82.0 |
| GR00T N1（Bjorck 等，2025） | 2B | 94.4 | 97.6 | 93.0 | 90.6 |
| SmolVLA（Shukor 等，2025） | 2.2B | 93.0 | 94.0 | 91.0 | 77.0 |
| NORA（Huang 等，2025） | 3B | 92.2 | 95.4 | 89.4 | 74.6 |
| pi0-FAST（Pertsch 等，2025） | 3B | 96.4 | 96.8 | 88.6 | 60.2 |
| pi0（Black 等，2025） | 3B | 96.8 | 98.8 | 95.8 | 85.2 |
| SpatialVLA（Qu 等，2025） | 4B | 88.2 | 89.9 | 78.6 | 55.5 |
| 4D-VLA（Zhang 等，2025） | 4B | 88.9 | 95.2 | 90.9 | 79.1 |
| PD-VLA（Song 等，2025） | 7B | 95.5 | 96.7 | 94.9 | 91.7 |
| ThinkAct（Huang 等，2025） | 7B | 88.3 | 91.4 | 87.1 | 70.9 |
| MolmoAct（Lee 等，2025） | 7B | 87.0 | 95.4 | 87.6 | 77.2 |
| TraceVLA（Zheng 等，2025） | 7B | 84.6 | 85.2 | 75.1 | 54.1 |
| WorldVLA（Cen 等，2025） | 7B | 87.6 | 96.2 | 83.4 | 60.0 |
| CoT-VLA（Zhao 等，2025） | 7B | 87.5 | 91.6 | 87.6 | 69.0 |
| UniVLA（Bu 等，2025） | 7B | 96.5 | 96.8 | 95.6 | 92.0 |
| OpenVLA（Kim 等，2024） | 7B | 84.7 | 88.4 | 79.2 | 53.7 |
| LAPA（Ye 等，2025） | 7B | 73.8 | 74.6 | 58.8 | 55.4 |
| UnifiedVLA（Li 等，2025） | 8.5B | 95.4 | 98.8 | 93.6 | 94.0 |
| FlowVLA（Zhong 等，2025） | 8.5B | 93.2 | 95.0 | 91.6 | 72.6 |

## 表7 不同 VLA 模型的推理效率对比

| 模型 | 执行效率（Hz） | 时延（s） |
|---|---:|---:|
| OpenVLA（Kim 等，2024） | 4.2 | 0.2396 |
| OpenVLA-OFT（Kim 等，2025） | 71.4 | 0.1120 |
| VLA-Adapter（Wang 等，2025） | 219.2 | 0.0365 |

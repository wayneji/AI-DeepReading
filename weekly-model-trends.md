# 每周模型趋势周报

> 最新一期始终放在文件顶部。开放权重模型以开发团队官方 Hugging Face 账号与 Collection 中可下载权重为准；排名针对具体模型版本，不按厂商分配席位。

---

# 每周模型趋势周报｜2026-07-28

## 本周一句话结论

**Kimi K3 今天正式进入 Moonshot 官方 Hugging Face Collection，并以 57 分的 Artificial Analysis Intelligence Index 超过 GLM-5.2 的 51 分，成为当前最强开放权重模型；但闭源前三仍由 Claude Opus 5、Claude Fable 5 和 GPT-5.6 Sol 占据，开放权重的综合差距已缩小到约 2–4 分。**

## Top 11 快速总览

### 中国开放权重 Top 5

| 排名 | 模型 | 发布/权重公开日期 | AA Intelligence Index | 本周判断 |
|---:|---|---:|---:|---|
| 1 | **Kimi K3** | **2026-07-28**（权重进入官方 HF） | **57** | 新榜首；Agent、长周期知识工作、代码和视觉均强，但推理慢、成本高、模型极大 |
| 2 | **GLM-5.2** | 2026-06-17 | **51** | 从榜首降至第二；长周期任务、科学推理和 1M 上下文仍很稳 |
| 3 | **MiniMax M3** | 2026-06-01（权重随后公开） | **44** | 与 DeepSeek V4 Pro 近似并列；原生图像/视频输入和计算机操作使综合面更广 |
| 4 | **DeepSeek V4 Pro** | 2026-04-24 | **44** | 纯文本推理、代码、1M 上下文和成本效率突出，但多模态缺位 |
| 5 | **MiMo-V2.5-Pro** | 2026-04-22 | **42** | 小米进入第一梯队；MIT 许可证、1M 上下文和较低 API 成本是主要优势 |

**本周最大变化：** GLM-5.2 上月刚建立的开放权重领先，被 Kimi K3 直接改写。Kimi K3 在 Agentic knowledge work 上不仅超过 GLM-5.2，也已接近最强闭源模型；但其 2.8T 总参数、104B 激活参数、较慢输出速度和高 API 价格，意味着“能力第一”暂时不等于“部署性价比第一”。

**榜外观察：** Tencent Hy3 以 41 分紧随其后，价格极具攻击性；Qwen 的生态和部署覆盖依然强，但当前官方开放权重旗舰尚无足够独立证据进入本期综合 Top 5。后续若 Qwen 新一代旗舰正式进入官方 HF Collection，榜单可能再次重排。

### 中国以外开放权重 Top 3

| 排名 | 模型 | 发布日期 | AA Intelligence Index | 本周判断 |
|---:|---|---:|---:|---|
| 1 | **Inkling**（Thinking Machines） | 2026-07-15 | **41** | 当前最强美国开放权重模型；1M 上下文、文本/图像/语音输入、Apache 2.0 |
| 2 | **NVIDIA Nemotron 3 Ultra** | 2026-06-04 | **38** | 550B/55B 激活，最大卖点是高吞吐、开放训练数据和配方，适合企业 Agent |
| 3 | **Mistral Medium 3.5 128B** | 2026-04-29 | **30** | 模型更紧凑，统一指令、推理、代码与视觉；综合能力弱于中美最新超大 MoE |

**趋势判断：** 海外开放权重阵营正在恢复活跃，Inkling 和 Nemotron 明显缩小了过去一年对中国开放模型的落差；但当前综合前沿仍由中国模型主导。海外的相对优势主要是许可证、训练透明度、企业工具链和高吞吐，而不是纯智能分数。

### 全球闭源 Top 3

| 排名 | 模型 | 发布日期 | AA Intelligence Index | 领先点 |
|---:|---|---:|---:|---|
| 1 | **Claude Opus 5** | 2026-07-24 | **61** | 当前综合第一；Agentic knowledge work、Coding Agent 和长周期交付最强 |
| 2 | **Claude Fable 5** | 2026-06-09 | **60** | 知识、科学推理和低幻觉表现突出，但价格高并带有安全 fallback 机制 |
| 3 | **GPT-5.6 Sol** | 2026-07-09 | **59** | 代码 Agent、终端任务、科学与网络安全强，综合性价比优于 Fable 5 |

**Gemini 状态：** Google 本周发布 Gemini 3.6 Flash、3.5 Flash-Lite 和 Cyber 变体，重点是速度、token 效率和低成本，而不是重新争夺最强模型榜首。Google 的下一旗舰 Pro 型号仍是决定其是否重返闭源第一梯队的关键。

## 开放权重与闭源模型的真实差距

- **综合智能差距正在迅速缩小：** Kimi K3 的 57 分距离闭源榜首 Opus 5 的 61 分只差 4 分，距离 GPT-5.6 Sol 只差 2 分。
- **Agent 单项已接近甚至局部超过：** Kimi K3 在 GDPval-AA v2 和 AutomationBench-AA 等 Agent 任务上已超过部分上一代闭源旗舰。
- **闭源仍领先于稳定交付：** Opus 5 和 GPT-5.6 Sol 更擅长在复杂工具链中稳定完成长周期任务，并拥有成熟的产品、沙箱、代码执行和企业治理体系。
- **开放模型的代价转向基础设施：** 能下载权重不代表部署便宜。Kimi K3、GLM-5.2 和 DeepSeek V4 Pro 都需要大型集群；真正有性价比的往往是量化版、较小激活参数模型或托管 API。

## 本周其他爆点

### AI 视频从“短片演示”进入长叙事压力测试

本周一部使用 ByteDance Seedance 2.0 制作的 13 分钟 AI 短片引发讨论。它证明生成式视频已经可以进入更长制作流程，但也暴露出连续镜头一致性、角色表演、背景文字和叙事节奏仍不稳定。

当前带音频的文生视频竞技榜中，**Gemini Omni Flash、Dreamina Seedance 2.0、Wan2.7** 位居前列。竞争焦点正从单镜头画质，转向音画同步、角色一致性、多轮编辑和长视频可控性。

## 下周重点观察

1. Kimi K3 权重公开后，第三方推理服务、量化版本和真实代码 Agent 评测是否支持其榜首地位。
2. GLM、DeepSeek、Qwen 是否快速发布回应版本，尤其是官方 Hugging Face Collection 中的新旗舰。
3. Claude Opus 5 的实际开发者口碑是否与预发布评测一致。
4. Google 下一代 Pro 模型是否结束延期并重新进入闭源前三竞争。
5. AI 视频能否在长镜头一致性和可编辑性上出现真正突破。

## 主要来源

- [Moonshot AI 官方 Hugging Face Collections](https://huggingface.co/moonshotai/collections)
- [Kimi K3 官方模型](https://huggingface.co/moonshotai/Kimi-K3)
- [Kimi K3 技术报告](https://arxiv.org/abs/2607.24653)
- [Kimi K3 — Artificial Analysis](https://artificialanalysis.ai/models/kimi-k3)
- [Z.ai 官方 Hugging Face Collections](https://huggingface.co/zai-org/collections)
- [GLM-5.2 — Artificial Analysis](https://artificialanalysis.ai/models/glm-5-2)
- [DeepSeek 官方 Hugging Face Collections](https://huggingface.co/deepseek-ai/collections)
- [DeepSeek V4 Pro — Artificial Analysis](https://artificialanalysis.ai/models/deepseek-v4-pro)
- [MiniMax M3 官方发布](https://www.minimax.io/blog/minimax-m3)
- [MiniMax 官方 Hugging Face Collections](https://huggingface.co/MiniMaxAI/collections)
- [MiMo-V2.5-Pro 官方模型](https://huggingface.co/XiaomiMiMo/MiMo-V2.5-Pro)
- [Inkling — Artificial Analysis](https://artificialanalysis.ai/models/inkling)
- [NVIDIA Nemotron 3 Ultra 官方页面](https://research.nvidia.com/labs/nemotron/Nemotron-3-Ultra/)
- [Mistral Medium 3.5 官方模型](https://huggingface.co/mistralai/Mistral-Medium-3.5-128B)
- [Claude Opus 5 — Artificial Analysis](https://artificialanalysis.ai/articles/opus-5)
- [GPT-5.6 官方发布](https://openai.com/index/gpt-5-6/)
- [Artificial Analysis 文生视频榜](https://artificialanalysis.ai/embed/text-to-video-leaderboard/leaderboard/text-to-video)

---

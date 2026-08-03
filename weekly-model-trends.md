# 每周模型趋势周报

> 最新一期始终放在文件顶部。开放权重模型以开发团队官方 Hugging Face 账号与 Collection 中可下载权重为准；排名针对具体模型版本，不按厂商分配席位。

---

# 每周模型趋势周报｜2026-08-03

> 更新窗口：2026-08-01 至 2026-08-03

## 本期结论

**正式开放权重 Top 11 暂时没有换位，但格局已经进入下一次洗牌前夜：阿里发布了 2.4T 参数的 Qwen3.8-Max Preview，早期榜单信号很强；然而它目前仍是 API/Token Plan 预览型号，Qwen 官方 Hugging Face Collection 尚无对应权重，因此暂不能挑战 Kimi K3 的开放权重榜首席位。与此同时，DeepSeek V4-Flash 以极低价格和仅 13B 激活参数，把“能力第一”之外的成本效率竞争推到新高度。**

## Top 11 快速概览

### 中国开放权重 Top 5

| 排名 | 模型 | 发布/权重状态 | AA Intelligence Index | 本期判断 |
|---:|---|---|---:|---|
| 1 | **Kimi K3** | 2026-07；官方 HF 已提供完整权重 | **57** | —；当前开放权重能力榜首，原生多模态与 Agent 强，但速度、价格和部署规模是明显代价 |
| 2 | **GLM-5.2** | 2026-06；MIT | **51** | —；综合能力略低，但吞吐、40B 激活参数和许可证更适合生产部署 |
| 3 | **MiniMax M3** | 2026-06；官方权重已发布 | **44** | —；以原生图像/视频理解和计算机操作能力暂列同分模型之前；专用许可证需单独核查 |
| 4 | **DeepSeek V4 Pro** | 2026-04-24；Preview；MIT | **44** | —；文本推理、代码、1M 上下文和价格优势突出，但仍属预览版 |
| 5 | **MiMo-V2.5-Pro** | 2026-04；MIT | **42** | —；1M 上下文、宽松许可证和低成本使其继续占据性价比席位 |

**Qwen3.8-Max 是本期最重要的“榜外第一候选”。** Reuters 报道其拥有 2.4T 总参数、每次推理约激活 95B 参数，并在公开竞技场迅速获得很强反馈；阿里云官方目前提供的型号仍是 `qwen3.8-max-preview`，且主要通过 Token Plan/API 使用。Qwen 官方 Hugging Face Collection 最新可见的旗舰开放系列仍是 Qwen3.6、Qwen3.5 等，因此本期不把它计入开放权重 Top 5。

这意味着目前存在两个不同榜单：

- **在线预览能力榜：** Qwen3.8-Max 已可能进入中国最前沿竞争；
- **可下载开放权重榜：** 在权重、模型卡和许可证正式进入官方 HF 前，Kimi K3 仍是第一。

**DeepSeek V4-Flash 的意义不在“突然发布”，而在价格被重新关注。** Artificial Analysis 将其发布日期列为 2026 年 4 月；在最高推理设置下约 40 分，低于本期 Top 5 门槛，但其 284B 总参数、13B 激活参数、约 118 tokens/s，以及极低 API 价格，使它成为批量推理、Agent 子任务和成本敏感业务的突出候选。它没有改写能力榜，却可能改写生产选型榜。

### 中国以外开放权重 Top 3

| 排名 | 模型 | 发布日期 | AA Intelligence Index | 本期判断 |
|---:|---|---:|---:|---|
| 1 | **Inkling**（Thinking Machines） | 2026-07-15 | **41** | —；1M 上下文，支持文本、图像和语音输入，Apache 2.0 |
| 2 | **NVIDIA Nemotron 3 Ultra** | 2026-06-04 | **38** | —；约 200 tokens/s 的高吞吐和开放训练体系仍是核心优势 |
| 3 | **Mistral Medium 3.5 128B** | 2026-04-29 | **30** | —；模型较紧凑且支持视觉，但能力与中国头部旗舰差距明显 |

**海外开放权重本期没有新模型正式改写前三。** Inkling 仍是海外综合最强代表，Nemotron 的优势集中在速度、企业部署和透明度；Mistral 保留较紧凑的工程价值。中国第五名 MiMo 仍略高于海外第一名 Inkling，中国第一名 Kimi K3 则领先 16 分。

**候补关注：** Poolside Laguna S 2.1 和 Upstage Solar-Open2-250B 已在 Hugging Face 获得开发者关注，但独立综合评测尚不足以替换现有前三；它们更适合作为下期观察项，而不是凭厂商 benchmark 直接入榜。

### 全球闭源 Top 3

| 排名 | 模型 | 发布日期 | AA Intelligence Index | 本期判断 |
|---:|---|---:|---:|---|
| 1 | **Claude Opus 5** | 2026-07-24 | **61** | —；综合智能和复杂长周期 Agent 仍居首 |
| 2 | **Claude Fable 5** | 2026-06-09 | **60** | —；知识工作强，但价格非常高且部分任务存在 fallback 变量 |
| 3 | **GPT-5.6 Sol** | 2026-07-09 | **59** | —；综合分略低，但编码 Agent、终端任务与产品工具链竞争力强 |

闭源前三本期没有发布新旗舰。Kimi K3 与 GPT-5.6 Sol 的综合分差仍约 2 分，与 Opus 5 相差约 4 分。**差距已经不再主要体现为“开放模型不会做”，而是闭源平台在复杂工具环境、稳定完成率、安全治理和端到端产品体验上仍更成熟。**

Gemini 3.6 Flash 以约 50 分和非常高的输出速度继续代表另一条路线：它并非能力榜前三，但在实时多模态、1M 上下文、视频/语音输入和大规模低延迟服务方面具有明显产品优势。

## 本期真正发生的变化

1. **Qwen 从“生态强、旗舰暂缺”重新回到能力前沿。** Qwen3.8-Max Preview 的出现意味着 Kimi K3 和 GLM-5.2 面临现实挑战；但是否改写开放榜，要等官方 HF 权重、许可证和独立评测落地。
2. **中国模型竞争正在分成三条战线。** Kimi K3 争最高能力，GLM-5.2 争能力与工程平衡，DeepSeek V4-Flash 争极致成本效率。单一“谁最强”的问题已经不足以指导真实选型。
3. **开放权重的定义必须继续严格执行。** Reuters 将中国路线概括为开放权重趋势，但具体到 Qwen3.8-Max，本期可验证状态仍是 Preview/API；“计划开放”不能提前等同于“权重已开放”。

## 本周其他爆点

### MiniMax H3：视频权重仍在等待落地

MiniMax 7 月 31 日发布的 H3 仍是本周最重要的非语言模型热点。它主打文本、图像、视频和音频输入，可生成带原生声音的视频，并支持编辑与动作迁移。真正会改变行业格局的是公司承诺开放模型权重。

**截至 2026-08-03，MiniMax 官方 Hugging Face 模型列表中仍以 MiniMax M3 为最新主要模型，尚未出现 H3 权重。** 因此 H3 继续归类为“已发布产品、开放权重待兑现”，而不是正式开放视频模型。

如果权重落地，重点不应只看演示画质，而应关注：许可证是否允许商用、训练和推理需要多少 GPU、角色一致性和音画同步能否被第三方复现，以及社区是否能对其进行 LoRA、控制网络和行业微调。

## 下一步观察

1. Qwen3.8-Max 是否进入 Qwen 官方 Hugging Face Collection，具体开放的是 Max 本体还是较小版本。
2. 独立评测是否支持阿里“接近闭源最前沿”的判断，以及它能否超过 Kimi K3 的 57 分。
3. DeepSeek V4-Flash 的真实业务吞吐和成本是否能在第三方服务商上稳定复现。
4. MiniMax H3 权重、模型卡和许可证是否正式发布。
5. Laguna S 2.1、Solar-Open2-250B 是否获得足够独立评测，推动海外开放 Top 3 换位。

## 主要来源

- [Reuters：Alibaba 发布 Qwen3.8-Max，DeepSeek V4-Flash 引发成本关注](https://www.reuters.com/business/retail-consumer/alibaba-unveils-its-most-capable-ai-model-date-not-far-behind-moonshots-size-2026-08-03/)
- [Alibaba Cloud Model Studio：Qwen3.8-Max-Preview](https://modelstudio.alibabacloud.com/)
- [Alibaba Cloud 模型列表](https://help.aliyun.com/en/model-studio/models)
- [Qwen 官方 Hugging Face Collections](https://huggingface.co/Qwen/collections)
- [Kimi K3 官方模型](https://huggingface.co/moonshotai/Kimi-K3)
- [Kimi K3 vs. GLM-5.2 — Artificial Analysis](https://artificialanalysis.ai/models/comparisons/kimi-k3-vs-glm-5-2)
- [GLM-5.2 官方模型](https://huggingface.co/zai-org/GLM-5.2)
- [DeepSeek V4-Flash 官方模型](https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash)
- [DeepSeek V4-Flash vs. GLM-5.2 — Artificial Analysis](https://artificialanalysis.ai/models/comparisons/glm-5-2-non-reasoning-vs-deepseek-v4-flash)
- [MiniMax 官方 Hugging Face 模型列表](https://huggingface.co/MiniMaxAI/models)
- [Inkling — Artificial Analysis](https://artificialanalysis.ai/models/inkling)
- [Nemotron 3 Ultra — Artificial Analysis](https://artificialanalysis.ai/models/nvidia-nemotron-3-ultra-550b-a55b)
- [Mistral Medium 3.5 — Artificial Analysis](https://artificialanalysis.ai/models/mistral-medium-3-5)
- [Claude Opus 5 — Artificial Analysis](https://artificialanalysis.ai/models/claude-opus-5)
- [Claude Fable 5 — Artificial Analysis](https://artificialanalysis.ai/models/claude-fable-5)
- [GPT-5.6 Sol — Artificial Analysis](https://artificialanalysis.ai/models/gpt-5-6-sol)
- [Gemini 3.6 Flash — Artificial Analysis](https://artificialanalysis.ai/models/gemini-3-6-flash)

---

# 每周模型趋势周报｜2026-08-01

> 更新窗口：2026-07-28 至 2026-08-01

## 本周一句话结论

**Top 11 本周没有换位：Kimi K3 继续以 57 分守住开放权重第一，距离闭源榜首 Claude Opus 5 的 61 分仅 4 分；真正的新爆点来自视频生成——MiniMax 于 7 月 31 日发布 H3，并称将在数日内开放权重，开放模型的竞争正在从语言与 Agent 扩展到视频生成。**

## Top 11 快速总览

### 中国开放权重 Top 5

| 排名 | 模型 | 发布/权重状态 | AA Intelligence Index | 本周变化 |
|---:|---|---|---:|---|
| 1 | **Kimi K3** | 2026-07-16 发布；7 月下旬进入官方 HF Collection | **57** | —；第三方评测继续确认其开放权重榜首地位 |
| 2 | **GLM-5.2** | 2026-06-16；MIT | **51** | —；速度、许可证和 40B 激活参数使工程实用性仍很强 |
| 3 | **MiniMax M3** | 2026-06-01；官方权重已发布 | **44** | —；与 DeepSeek V4 Pro 同分，因原生图像/视频输入暂列其前 |
| 4 | **DeepSeek V4 Pro** | 2026-04-24；Preview；MIT | **44** | —；文本推理和成本效率强，但仍是预览版且不支持图像输入 |
| 5 | **MiMo-V2.5-Pro** | 2026-04-22；MIT | **42** | —；1M 上下文和低价格让它仍是性价比代表 |

**榜首判断更稳定了，但没有变得更便宜。** Kimi K3 的权重已经进入 Moonshot 官方 Hugging Face Collection，Artificial Analysis 仍给出 57 分；同时它只有约 35 tokens/s，API 为每百万输入/输出 token 3/15 美元，2.8T 总参数、104B 激活参数，并采用需要额外关注商业条款的专用许可证。因此它是“能力榜首”，但未必是企业自部署或批量推理的首选。

**GLM-5.2 仍可能是更均衡的工程选择。** 它的综合分低 6 分，但 MIT 许可证、40B 激活参数、1M 上下文和明显更高的服务速度，使其在成本、吞吐与能力之间更平衡。

**第三至第五名的差距很小。** MiniMax M3 适合需要图像、视频理解和电脑操作的场景；DeepSeek V4 Pro 更适合纯文本推理和低成本高强度推理；MiMo-V2.5-Pro 则在价格和许可证上更友好。

**榜外观察：** Qwen 仍是生态、尺寸覆盖和本地部署最完整的中国模型家族之一，但截至本期，没有新的官方 HF 旗舰凭独立综合评测进入前五。下一次 Qwen、GLM、DeepSeek 或 MiniMax 的旗舰权重落地，都可能重新洗牌。

### 中国以外开放权重 Top 3

| 排名 | 模型 | 发布日期 | AA Intelligence Index | 本周变化 |
|---:|---|---:|---:|---|
| 1 | **Inkling**（Thinking Machines） | 2026-07-15 | **41** | —；美国开放权重第一，支持文本、图像和语音输入，Apache 2.0 |
| 2 | **NVIDIA Nemotron 3 Ultra** | 2026-06-04 | **38** | —；约 200 tokens/s 的吞吐和训练透明度仍是核心卖点 |
| 3 | **Mistral Medium 3.5 128B** | 2026-04-29 | **30** | —；模型较紧凑，但纯能力已与中国头部拉开明显差距 |

**趋势判断：** 海外开放权重阵营本周没有新旗舰改写排名。Inkling 把美国开放模型提升到 41 分，但仍落后中国第五名 MiMo-V2.5-Pro 1 分，落后 Kimi K3 16 分。海外目前的主要优势仍是 Apache 2.0 等许可证、训练透明度、企业工具链和吞吐，而不是最高综合能力。

### 全球闭源 Top 3

| 排名 | 模型 | 发布日期 | AA Intelligence Index | 本周变化 |
|---:|---|---:|---:|---|
| 1 | **Claude Opus 5** | 2026-07-24 | **61** | —；综合智能和长周期 Agent 仍居首 |
| 2 | **Claude Fable 5** | 2026-06-09 | **60** | —；知识工作强，但价格最高且部分请求可能触发 fallback |
| 3 | **GPT-5.6 Sol** | 2026-07-09 | **59** | —；综合第三，但编码 Agent、终端任务和 token 效率具竞争优势 |

**闭源并非所有单项都领先。** Opus 5 仍是综合第一，但 OpenAI 公布的独立 Coding Agent Index 中，GPT-5.6 Sol max 达到 80，领先 Fable 5；这说明“综合榜第三”并不等于在软件工程工作流中排名第三。

**Gemini 尚未重回前三。** Gemini 3.6 Flash 的重点是更少 token、更低成本、电脑操作和生产级 Agent 吞吐，而不是争夺最高综合分。Google 已公开表示 Gemini 3.5 Pro 仍在测试，并已启动 Gemini 4 的预训练；后续 Pro 旗舰才是改变闭源前三格局的关键。

## 本周真正的变化

1. **Kimi K3 从“刚发布”进入“可验证阶段”。** 权重、技术报告和社区评测已经落地，57 分的领先不再只是发布会口径；接下来需要看量化、第三方推理服务和真实代码 Agent 是否能复现优势。
2. **开放与闭源的综合差距维持在 2–4 分。** Kimi K3 距离 GPT-5.6 Sol 2 分、距 Opus 5 4 分；差距更多体现在稳定交付、工具环境和产品体系，而不是所有 benchmark 的绝对能力。
3. **能力榜与部署榜正在分离。** Kimi K3 最强，但 GLM-5.2、DeepSeek V4 Pro、MiMo-V2.5-Pro 在许可证、激活参数、速度和价格上可能更适合生产。

## 本周其他爆点

### MiniMax H3：开放权重可能首次深入视频生成前沿

MiniMax 于 **2026-07-31** 发布 H3 视频生成模型。根据公司披露与 Reuters 报道，H3 可以同时接收文本、图像、视频和音频，生成最长 15 秒、2K 分辨率并带原生立体声的视频，还支持现有视频编辑和动作迁移。

真正值得关注的不是单纯的 2K 或 15 秒，而是 MiniMax 表示将在数日内发布模型权重。若权重按计划进入官方 Hugging Face，这会把中国开放权重路线从 LLM、VLM 和 Agent 推进到此前高度闭源的视频生成领域。

**当前状态：计划开放权重，但截至 8 月 1 日尚未进入 MiniMax 官方 Hugging Face 模型列表，因此本期只列为热点，不按开放模型正式入榜。**

潜在影响：

- 对 Seedance 2.0、Kling 3.0、Gemini Omni 等闭源或托管视频产品形成价格与可定制性压力；
- 广告、电商、游戏和产品设计团队可能获得可私有化的视频生成基础模型；
- 后续评价重点将从单镜头画质转向音画同步、角色一致性、视频编辑和运动控制。

## 下周重点观察

1. MiniMax H3 权重是否如期进入官方 Hugging Face，以及采用什么许可证。
2. Kimi K3 的量化版、第三方部署与真实 Agent 任务能否保持 57 分级别的优势。
3. GLM、Qwen、DeepSeek 是否发布针对 Kimi K3 的回应型号。
4. Gemini 3.5 Pro 是否正式发布并进入闭源前三竞争。
5. Top 5 是否会从“最大模型能力竞赛”转向“能力、速度、许可证和部署成本”的综合竞争。

## 主要来源

- [Moonshot AI：Kimi K3 官方 Hugging Face Collection](https://huggingface.co/collections/moonshotai/kimi-k3)
- [Kimi K3 — Artificial Analysis](https://artificialanalysis.ai/models/kimi-k3)
- [GLM-5.2 官方模型](https://huggingface.co/zai-org/GLM-5.2)
- [GLM-5.2 — Artificial Analysis](https://artificialanalysis.ai/models/glm-5-2)
- [MiniMax M3 官方模型](https://huggingface.co/MiniMaxAI/MiniMax-M3)
- [MiniMax M3 — Artificial Analysis](https://artificialanalysis.ai/models/minimax-m3)
- [DeepSeek V4 Pro 官方模型](https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro)
- [DeepSeek V4 Pro — Artificial Analysis](https://artificialanalysis.ai/models/deepseek-v4-pro)
- [MiMo-V2.5-Pro — Artificial Analysis](https://artificialanalysis.ai/models/mimo-v2-5-pro)
- [Inkling 官方 Hugging Face Collection](https://huggingface.co/collections/thinkingmachines/inkling)
- [Inkling — Artificial Analysis](https://artificialanalysis.ai/models/inkling)
- [Nemotron 3 Ultra — Artificial Analysis](https://artificialanalysis.ai/models/nvidia-nemotron-3-ultra-550b-a55b)
- [Mistral Medium 3.5 — Artificial Analysis](https://artificialanalysis.ai/models/mistral-medium-3-5)
- [Claude Opus 5 — Artificial Analysis](https://artificialanalysis.ai/models/claude-opus-5)
- [Claude Fable 5 — Artificial Analysis](https://artificialanalysis.ai/models/claude-fable-5)
- [OpenAI：GPT-5.6 正式发布](https://openai.com/index/gpt-5-6/)
- [Google：Gemini 3.6 Flash、3.5 Flash-Lite 与 3.5 Flash Cyber](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-6-flash-3-5-flash-lite-3-5-flash-cyber/)
- [Reuters：MiniMax 发布 H3 视频模型](https://www.reuters.com/world/china/chinas-minimax-releases-h3-video-model-2026-07-31/)

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

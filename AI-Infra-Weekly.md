# AI Infra 周报

> 聚焦中国与海外 Cloud AI Infrastructure、Neocloud 与 AI-native Infra。最新一期始终置于顶部；事实优先采用公司公告、监管文件和官方财报，分析判断不等同于公司指引或 Gartner 官方结论。

---

## 2026-08-07｜GPU脱销之后：低价Token与国产化重写AI Cloud回报率

**观察区间：2026-08-01—2026-08-07**

### 本期核心结论

1. **Inference需求仍在增长，但Token不再天然是高毛利池。** 8月3日，Reuters援引Artificial Analysis称，DeepSeek V4-Flash的公开价为每百万输入/输出Token分别0.14/0.28美元，单次基准测试平均成本约0.03美元。低价模型、订阅制与缓存折扣正在把“Token量增长”与“Token收入、毛利增长”进一步拆开。
2. **中国AI Infra的主要矛盾正从“有没有GPU”变成“稀缺NVIDIA资源如何分配、国产GPU如何形成有效供给”。** 存量高端GPU可以维持高利用率和价格，但新增国产算力只有在模型适配、Serving效率、稳定性和迁移服务完成后，才等同于可销售产能。
3. **阿里、腾讯正在让模型、Agent入口和Cloud计费进一步收敛。** 阿里本周发布Qwen3.8-Max，并继续以Token Plan把Qwen、第三方模型、多模态能力及Claude Code等兼容工具装进统一订阅；腾讯则公告将部分旧Agent模型迁移至DeepSeek V4 Pro。Cloud正在成为模型路由、套餐设计和Token结算层，而不只是API托管方。
4. **海外Neocloud的壁垒正在从“拿到GPU”上升到“拿到电力、低成本资本和长期合同”。** CoreWeave宣布在印度尼西亚建设三个合计360MW的数据中心，计划2028年上线，标志其首次实体进入亚太；与此同时，Financial Times报道Google围绕Anthropic组织了约2,000亿美元的芯片与数据中心融资体系。AI Infra越来越像“技术运营能力 + Structured Finance”的复合行业。
5. **量化私募等新算力买方扩大的是上游资产需求，不必然扩大Neocloud的可服务TAM。** 顶级量化机构可能自购GPU、自建集群，甚至与模型公司或SPV共同持有资产；它们也可能成为稀缺GPU的竞买者。只有接受国产芯片迁移、承诺长期负载或由客户出资而AI Cloud代建代运维时，才是当前更高质量的客户。

---

### 一、关键动态及影响

#### 1. DeepSeek再次压低公开Inference价格

- **【已确认事实】** [Reuters 8月3日报道](https://www.reuters.com/business/retail-consumer/deepseeks-new-ai-model-is-by-far-cheapest-well-known-models-run-research-firm-2026-08-03/)，V4-Flash每百万输入Token为0.14美元、输出Token为0.28美元；Artificial Analysis给出的单次基准测试平均成本约0.03美元，明显低于Kimi K3、OpenAI GPT-5.6 Sol和Anthropic Claude Fable 5。
- **【分析判断】** 这不是“所有高端模型必须跟到同一价格”，而是把高频、可容错、可路由的Inference工作负载重新锚定到极低价格。Coding Agent、搜索、批处理和多Agent协作会首先采用“强模型做规划、低价模型做执行”的分层路由。
- **【行业影响】** Token Hub的调用量可能上升，但若仍按公开API折扣转售，毛利会更快下降。真正可防守的利润将来自批量调度、缓存命中、量化与Serving优化、SLA、私有化和专属并发，而不是API价差。

#### 2. 阿里Qwen3.8-Max：模型首发本身成为订阅获客工具

- **【已确认事实】** [Reuters 8月3日报道](https://www.reuters.com/business/retail-consumer/alibaba-unveils-its-most-capable-ai-model-date-not-far-behind-moonshots-size-2026-08-03/)，阿里发布2.4万亿参数的Qwen3.8-Max，单次请求激活约950亿参数，并支持多模态和100万Token上下文。
- **【已确认事实】** 阿里此前已在[Model Studio Token Plan](https://modelstudio.alibabacloud.com/intl/blog/model-studio-token-plan-individual/)中让Qwen3.8-Max-Preview首发，统一覆盖文本、图像、视频、语音与平台工具，并兼容Claude Code及OpenAI/Anthropic API格式。其Credits按5小时和7天滚动刷新，且可叠加低谷折扣。
- **【分析判断】** 阿里的核心动作不是单独卖一个Qwen模型，而是用新模型拉动订阅，再把开发工具、模型路由和Cloud结算收进Model Studio。它在复制Codex、Claude Code所验证的高频Agent消费形态，同时利用Hyperscaler的模型、算力与计费一体化降低获客成本。

#### 3. 腾讯从自有Agent模型切向DeepSeek V4 Pro

- **【已确认事实】** [腾讯云公告](https://cloud.tencent.com/announce/detail/2393)称，youtu-agent及youtu-mrc-pro将于8月28日起停止调用；套餐用户如未自行切换，将自动迁移至DeepSeek V4 Pro。youtu-agent专属并发也将停止新购和续购。
- **【分析判断】** 这说明MaaS平台可以主动替换底层模型，而用户入口、套餐、计费和Agent工作流继续留在Cloud。对模型公司的挑战是：即使模型被采用，客户关系和收入控制权也可能属于平台；对Token Hub而言，模型路由能力的重要性高于单一模型代理权。
- **【待验证】** 自动迁移后的实际单位成本、并发体验及腾讯自有模型在企业Agent中的份额尚无公开数据，不能据此断言腾讯已放弃自有模型路线。

#### 4. CoreWeave首次实体进入亚太

- **【已确认事实】** [Reuters 8月4日报道](https://www.reuters.com/world/asia-pacific/coreweave-expands-into-indonesia-announces-first-data-center-asia-pacific-2026-08-04/)，CoreWeave将在印度尼西亚建设三个数据中心，合计规划360MW、预计2028年上线，这是其首次在亚太建立实体基础设施。
- **【分析判断】** 这对中国市场短期没有直接供给冲击，但验证了Neocloud的下一阶段竞争是区域电力、数据主权和本地交付。亚太客户未来可以在Hyperscaler之外获得更专业的AI Cloud选项；国内独立AI Cloud若走海外，需要同时具备本地电力、融资、客户承诺和跨区域运维，不能只输出GPU租赁产品。

#### 5. AI Infra开始被大规模Structured Finance重构

- **【可信报道】** [Financial Times 8月4日报道](https://www.ft.com/content/549f2e23-5aa2-49c7-9ea6-a9784ab7087c)，Google围绕向Anthropic提供TPU算力组织了约2,000亿美元的融资体系，涉及芯片采购、Compute SPV、数据中心项目融资以及供应商残值支持。相关安排未被完整纳入公司公开指引，应视为可信报道而非已审计口径。
- **【分析判断】** 全球AI Infra的资本天花板不再由Cloud公司单一资产负债表决定，而由长期客户合同、芯片残值、厂商担保和Private Credit共同决定。这也给中国市场一个提示：基金、量化机构和产业资本更可能先成为算力资产的出资人或共同持有人，再决定是否成为Cloud客户。

---

### 二、竞争格局变化

本周没有足够证据改变此前的中国总体排序：

- **天花板层：** 阿里云 → 火山引擎 → 腾讯云 → 百度智能云 → 华为云
- **SenseCore Arena：** 天翼云 → SenseCore → 金山云 → 并行科技 → 曙光先进计算云 → 首都在线 → UCloud
- **AI-native追赶层：** 硅基流动 → PPIO → 无问芯穹 → 趋境科技 → 基流科技 → ZStack

但三个分项坐标正在变化：

| 分项战场 | 本周相对变化 | 含义 |
|---|---|---|
| 模型能力与Agent入口 | 阿里上升；DeepSeek继续掌握价格锚 | 新模型若同时绑定订阅和开发工具，价值高于只发布API |
| MaaS与Token分发 | 阿里、腾讯强化平台控制权 | 底层模型可替换，用户关系与结算留在Cloud |
| GPUaaS与国产化执行 | 排名暂不变，执行差距扩大 | 装机规模不等于有效产能，国产芯片的模型适配与SLA成为分水岭 |
| 海外Neocloud | CoreWeave的区域与融资优势扩大 | Lambda、Nebius、Crusoe仍是同类对标，但CoreWeave更接近“AI-native Hyperscaler” |
| 新型算力买方 | 量化机构重要性上升，但客户属性分化 | 顶级机构可能自建或竞买，中腰部更可能采购托管/专属集群 |

字节、百度本周未出现足以改变判断的新增公开披露。此前形成的判断仍成立：字节的豆包/飞书/火山整合会增加Agent入口对Token流量的控制；百度以ERNIE、千帆、GPU Cloud和昆仑芯形成全栈闭环。二者对独立GPU Cloud最直接的压力，仍是把模型入口、Inference资源和Cloud账单打包，而不是简单增加一批GPU供给。

Codex与Claude Code本周也未出现需要重估的重大产品发布。全球趋势没有反转：Coding Agent仍是高频Token分发层，OpenAI/Anthropic兼容接口正在成为国内Token Plan的事实接入标准之一。

---

### 三、对GPUaaS与Inference/Token的影响

#### GPUaaS：稀缺资源与国产资源将形成两个价格体系

1. **高端NVIDIA池：** 若存量资源已处于高利用率，短期问题不是找更多客户，而是把容量分配给期限更长、信用更好、单位GPU贡献更高的合同。量化私募可能与AI Cloud竞买这类资源，并非天然增量客户。
2. **国产GPU池：** 真正的销售单位不应是“卡”或“P算力”，而应是通过验证的模型吞吐、首Token延迟、连续服务稳定性和迁移周期。国产化会扩大名义供给，却可能先造成型号碎片化、软件适配与交付成本上升。
3. **商业模式：** 在客户愿意承担CAPEX的情况下，“客户出资 + AI Cloud代建代运维 + 最低使用承诺”比纯GPU租赁更适合承接量化机构、模型公司和大型企业的专属需求。

#### Inference/Token：量增仍确定，利润池继续上移

- 公开Token价将继续下降，尤其是可批处理、可缓存、可路由的工作负载。
- 高毛利环节向模型路由、缓存、量化、推测解码、异构调度、SLA和企业数据隔离迁移。
- Token Hub会出现两极分化：有稳定流量、跨模型调度和硬件议价能力的平台扩大规模；只做API转售的平台被订阅制和Hyperscaler价格挤压。
- 对大型模型公司而言，低价API既是获客手段，也是对基础设施效率的压力测试。没有自研Serving优化或稳定批发算力来源的公司，Token越多未必利润越高。

---

### 四、对SenseCore的具体传导

#### 1. 从“卖可用GPU”切换为“分配稀缺容量”

在存量GPU供给紧张的情景下，销售目标应从新增Logo转为合同质量。建议以四项指标决定资源优先级：最低消费承诺、负载稳定性、回款与信用、迁移到国产GPU的可行性。单纯因为客户有品牌或有AUM，不应获得稀缺资源优先权。

#### 2. 把国产化做成产品，不做成采购口径

SenseCore的优势不应只表述为支持多种国产芯片，而应形成可售卖的“模型—芯片—Serving”矩阵：

- 对Kimi、智谱、DeepSeek等模型公司，给出主力模型在不同国产芯片上的吞吐、时延和单位Token成本；
- 对硅基流动、趋境科技等Token Hub，提供跨模型路由、专属并发、峰谷调度和最低成本方案；
- 对企业与量化客户，提供迁移评估、专属集群、数据隔离和代运维，而不是开放式长尾API。

#### 3. 客户组合建议

| 客户层 | 典型客户 | 资源策略 | 建议优先级 |
|---|---|---|---|
| Anchor | 大型模型公司、头部Token Hub | Take-or-pay、专属容量、联合优化 | 最高 |
| Strategic Builder | 有稳定负载且愿意共建的企业、部分量化机构 | 客户出资或预付、SenseCore代建代运维 | 高 |
| Diversifier | 垂直Agent、金融/科研/工业AI应用 | 国产池、标准SLA、组合采购 | 中 |
| Long tail | 小B、实验性项目、纯比价客户 | 通过伙伴或标准平台服务 | 低 |

量化私募应被放在Strategic Builder而不是默认Anchor：其价值在于可能承担资产投资和形成长期专属负载；风险在于自建、挖人后内化能力，或只争夺稀缺NVIDIA资源。判断一家量化机构是否值得进入Sales Pipeline，应先验证三件事：是否接受国产芯片、是否有可量化的训练/Inference负载、是否愿意签24—36个月最低承诺。

#### 4. 不追求公开API价格战

SenseCore更适合定位为Wholesale Inference Cloud和Managed AI Infrastructure。面对DeepSeek的公开价，不能用零散Token价硬碰，而应出售“可预测成本 + 容量保障 + 迁移服务 + 私有部署”。若合同没有最低消费、容量费或客户预付，纯按Token结算会把利用率和价格风险全部留给SenseCore。

---

### 五、未来3—12个月观察指标

1. **模型价格与真实使用：** DeepSeek V4-Flash、V4-Pro和Qwen3.8-Max的实际调用份额、缓存命中率、促销后价格及企业续费率。
2. **国产GPU有效供给：** 不是新增卡数，而是主流模型在国产芯片上的单位Token成本、稳定运行天数、集群利用率和迁移周期。
3. **大厂Portfolio：** 火山方舟、阿里Model Studio、腾讯ADP/TokenHub、百度千帆是否继续把Agent订阅、Coding工具和MaaS账单合并；第三方模型在各平台的流量占比。
4. **SenseCore执行：** 国产集群的已签客户、最低消费覆盖率、Inference收入中专属容量与纯Token结算的比例。
5. **Neocloud资本结构：** CoreWeave印度尼西亚项目的电力与客户承诺、Nebius/Lambda/Crusoe的新增长合同，以及Private Credit对GPU和数据中心项目的融资成本。
6. **量化机构算力行为：** 是直接采购GPU、租用专属集群、与模型公司共建，还是转向云/API；尤其关注采购主体是否为基金产品、管理人、关联科技公司或SPV。

---

### 六、风险与口径说明

- DeepSeek价格为公开API标价和第三方测评口径，不等于所有企业客户的实现价格或模型全生命周期成本。
- CoreWeave亚太数据中心计划到2028年上线，属于中长期供给，不能计入未来12个月可用产能。
- Financial Times披露的Google/Anthropic融资结构为媒体报道，合同规模、担保和表内外归属仍需监管文件或公司披露验证。
- 国内GPU供给紧张与国产化节奏因型号、区域和客户类型差异很大；“GPU脱销”不代表所有算力、所有芯片均短缺。
- 量化机构的AUM、AI研究能力和可投入AI Infra的CAPEX并非同一口径；招聘采购人才只能视为建设意图信号，不能直接推断采购预算或建成规模。

### 本期一句话判断

> GPU短缺保证了短期利用率，低价Token压缩了长期毛利；SenseCore下一步的胜负，不在于卖出更多卡，而在于把国产算力变成可验证的有效供给，并用长期合同让客户共同承担资产风险。

## 2026-07-31｜Agent入口成为Token分发层，大厂开始重写Inference竞争

**观察区间：2026-07-25—2026-07-31**

### 本期核心结论

1. **Cloud AI Infrastructure 的竞争入口正在上移到 Coding Agent 与企业工作流，但最终消耗仍回到底层 Token 和 GPU。** Codex、Claude Code 已证明，持续执行、代码库理解、工具调用和云端并行任务可以形成高频、长上下文的推理负载。国内阿里百炼、腾讯 TokenHub、火山方舟也开始把 Claude Code、Codex CLI、Qwen Code、CodeBuddy、TRAE 等工具接入订阅型 Token Plan。Coding Agent 不只是 SaaS 产品，而正在成为新的 Token 分发渠道。
2. **字节调整对 GPUaaS 的直接冲击有限，对 Inference/Token 的冲击更大。** 豆包与飞书统一产品侧、火山引擎与飞书统一 GTM 后，字节获得“模型—办公入口—企业销售—MaaS/Cloud”的闭环。它不会立刻改变 GPU 型号、集群网络和交付能力的竞争，却会通过自有流量提高推理池利用率、建立价格/性能基准，并把压力传给 Kimi、智谱、DeepSeek、硅基流动、趋境等模型公司和 Token Hub。
3. **阿里、腾讯和火山正在从“卖某个自研模型”转向“多模型订阅 + Agent工具兼容 + Cloud计费”。** 阿里 Token Plan 已把文本、图像、视频模型和 Harness 工具纳入统一 Credits；腾讯 TokenHub 同时提供混元和多家第三方模型，并兼容 Claude Code、Cursor、Codex CLI 等工具；火山方舟 Coding Plan 同样强调多模型和工具不限。这意味着 Hyperscaler 正在复制独立 Token Hub 的聚合价值，同时用 Cloud、企业入口与账单体系增强分发。
4. **Token Volume 高增长不代表 Token 上游利润同步增长。** IDC 预计中国公有云 MaaS 调用量由 2025 年约 1,944 万亿 Token 增至 2026 年约 40,000 万亿，而收入由约 30.7 亿元增至约 186 亿元。按该预测粗算，混合平均收入从约 1.58 元/百万 Token 降至约 0.47 元，下降约 71%；这不是单一模型报价预测，但明确说明 Volume 增速可能远高于收入和毛利增速。
5. **SenseCore 不应成为另一个面向长尾开发者的公共 MaaS，而应成为 Wholesale Inference Cloud。** 核心客户应是少数大型模型公司、Token Hub 与高负载 AI-native 应用，通过 Dedicated Inference Capacity、最低消费承诺和 SLA 锁定基础利用率；GPU 从 GPUaaS 池转入 Inference 池的唯一硬标准，应是风险调整后的每 GPU 小时毛利更高。

### 关键动态及影响

| 公司 / 产品 | 已确认动态 | 对 AI Infra 的含义 | 本期判断 |
|---|---|---|---|
| 字节：豆包、飞书、火山引擎 | 7 月 30 日调整产品与 GTM：飞书产品团队与豆包整合；飞书 GTM 与火山引擎对应团队整合为“创造力服务平台”，统一服务 MaaS 与 SaaS 客户 | 企业办公入口可直接把 Agent 需求导向豆包与火山方舟，提升自有 Inference 利用率和交叉销售能力 | **上调 Token 分发与 GTM 执行力；GPUaaS 身位不因此直接上调** |
| 字节“大模型业务 ARR” | 媒体称按 7 月平均消耗年化约 40 亿美元，但未披露外部/内部、标价/实收、飞书 AI 与传统 Cloud 的边界 | 该数字约合 287 亿元，已高于 IDC 对 2026 年中国公有云 MaaS 全市场 186 亿元的预测，两个口径显然不可直接比较 | **作为需求势能指标；不计入火山 Cloud AI Infrastructure revenue** |
| 阿里云百炼 | Token Plan 7 月 27 日更新：统一 Credits，可在 Claude Code、Cursor、Qwen Code、Qoder 等工具使用，并覆盖文本、图像、视频模型及工具；Coding Plan 聚合千问及第三方模型 | 阿里把 Qwen 模型、Qoder/Qwen Code、百炼模型市场、Cloud 计费和团队席位做成完整漏斗 | **目前国内最完整的“模型—Coding Agent—MaaS—Cloud”组合之一** |
| 腾讯云 | TokenHub 提供通用 Token Plan 与自研 Hy Token Plan，兼容 Claude Code、CodeBuddy、Cursor、Codex CLI 等；WorkBuddy 对接 QQ/企微生态和 Token Plan | 腾讯由“混元单模型供给”转向“自研模型 + 多模型聚合 + 工作入口”；对独立 Token Hub 的重叠度明显上升 | **上调 Inference 分发能力，整体执行仍需看付费 Token 与企业留存** |
| 百度智能云 | 文心快码 Comate 已形成多智能体 Coding Agent；千帆持续提供模型、Agent开发、数据和运行环境等企业 Agent Infra，但本观察期没有看到与字节调整同量级的新整合披露 | 百度仍偏企业开发、政企交付和工具链，公共 Token 订阅与高频工作入口的新增信号相对弱 | **总体身位不变；企业工程化强于开发者 Token 分发势能** |
| OpenAI Codex / GPT-5.6 | Codex 工作流继续向跨设备同步、云端任务和多角色工作扩展；OpenAI 7 月 30 日将 GPT-5.6 Luna 价格下调 80%、Terra 下调 20% | 全球头部已用“能力分层 + 成本分层 + Agent入口”做流量调度，价格下降会继续传导至中国 Coding/Agent 套餐 | **进一步验证 Agent 是推理需求入口，模型路由是成本控制核心** |
| Anthropic Claude Code / Opus 5 | 7 月 24 日推出 Claude Opus 5，并作为 Claude Code 的高能力模型来源之一；Claude Code持续强化企业治理和代码审查 | 高端 Coding Agent 仍能通过高任务完成率获得溢价，但订阅限额、模型路由和企业治理决定商业化效率 | **全球产品标杆继续抬高任务完成率与企业安全门槛** |
| CoreWeave / 海外 Neocloud | FT 报道 CoreWeave 为与 Anthropic 合同相关的 26 亿美元贷款提高收益率并增加保护条款，最终融资需求改善 | AI算力需求仍强，但资本市场开始更严格地区分客户合同期限、融资成本和资产寿命 | **Neocloud需求逻辑不变，资本成本与合同质量权重上升** |

### Portfolio对比：谁在控制Inference流量

| 玩家 | 模型层 | Agent / Coding入口 | MaaS / Token分发 | Cloud与企业入口 | 当前优势与缺口 |
|---|---|---|---|---|---|
| 阿里 | Qwen全系列及第三方模型 | Qoder、Qwen Code、Claude Code等兼容 | 百炼 Coding Plan、Token Plan、按量API | 阿里云、钉钉及企业客户体系 | 组合最完整；挑战是把产品广度转化为稳定付费与一致体验 |
| 字节 | Doubao/Seed系列及方舟第三方模型 | TRAE、方舟 Coding Plan、豆包企业版 | 火山方舟 MaaS、Agent/Coding订阅 | 飞书工作流与统一 ToB GTM | 自有流量和价格能力最强；外部收入边界与毛利仍不透明 |
| 腾讯 | Hy3/混元及TokenHub第三方模型 | CodeBuddy、WorkBuddy、Claude Code/Codex等兼容 | TokenHub个人版、企业版与API | 企微、QQ、腾讯文档、会议、ima | 入口多、聚合转向快；仍需证明产品之间形成稳定闭环 |
| 百度 | 文心及千帆多模型生态 | Comate/Zulu、多Agent开发 | 千帆 ModelBuilder、AppBuilder和API | 搜索、百度办公/企业与政企渠道 | 企业工程化与行业交付较强；公共 Token 分发新增势能较弱 |
| OpenAI | GPT-5.6分层模型 | Codex、ChatGPT Work、CLI/IDE/Cloud | API、订阅与Credits | ChatGPT、GitHub连接及企业治理 | Agent入口与模型协同领先，正从Coding扩展到通用工作 |
| Anthropic | Claude Sonnet/Opus系列 | Claude Code | Claude Platform、云渠道 | Claude Enterprise及第三方Cloud | Coding任务完成率与企业信任强，但基础设施依赖合作云 |

### 对 GPUaaS 的未来影响

**未来 3—6 个月：格局不会因字节组织调整而突变。** GPUaaS 的采购仍由 GPU 类型、互联、可用容量、SLA、数据位置和价格决定。字节新增推理需求主要会先进入自己的火山体系，不会直接成为 SenseCore 的增量订单。

**未来 6—12 个月：通用 GPU 租赁会出现两股相反力量。**

- 正面：Agent与Coding工作负载扩大，Hyperscaler自用推理吞噬更多GPU，可能继续维持外部高性能GPU供给偏紧。
- 负面：大厂以 Token Plan、MaaS 和应用订阅打包销售，客户越来越按任务结果和 Token 采购，而不是按GPU小时采购；缺少Serving和调度能力的“裸卡云”会被压缩。
- 结果：GPUaaS不会消失，但价值将向长期预留集群、专属推理实例、低延迟网络和可快速转为Inference的弹性池集中。

### 对 Inference / Token 的未来影响

最可能发生的不是 Token 需求不足，而是**流量与利润向掌握入口的一侧集中**：

1. Coding Agent和企业工作流产生持续、高上下文、多步骤调用，Token消耗增长加速。
2. 阿里、腾讯、火山通过订阅套餐聚合模型，决定用户默认调用哪个模型，并逐渐成为模型公司的分发渠道。
3. Kimi、智谱、DeepSeek等模型公司若没有足够强的自有入口，将更依赖Cloud和Token Hub获取流量，同时被要求降价。
4. 硅基流动、趋境等中立Token平台仍有多模型、跨芯片和“不与客户竞争”的价值，但Hyperscaler开始复制其聚合模式，零售利润会受到挤压。
5. 价格压力最终通过模型公司和Token Hub传到GPU/Inference供应商，表现为更低的每Token采购价、更短的承诺周期、更强的弹性要求和更严格的SLA。

### 对 SenseCore 的具体传导

SenseCore 需要把客户分为三层，而不是建设公共API长尾漏斗：

- **头部 Anchor（建议占 Inference 收入/产能 55%—65%）：** Kimi、智谱、DeepSeek等大型模型公司，以及硅基流动、趋境等头部Token Hub。打法是12—24个月容量规划、Take-or-pay、Dedicated Inference与超额Token计费。
- **腰部 Growth（25%—35%）：** Coding Agent、AI搜索、视频/语音生成、企业Agent和垂直模型公司。打法是标准化专属实例、Reserved Throughput和3—12个月承诺，尽量减少项目制开发。
- **长尾 Ecosystem（不超过10%）：** 小模型公司、开发者和小B客户。由Token Hub、模型平台和ISV覆盖，SenseCore只做幕后Wholesale Inference，不承担直接获客和客服成本。

对GPU池的决策应统一为一个指标：

> **Risk-adjusted Gross Profit per GPU Hour = Inference每GPU小时贡献 − 客户集中、流量波动与SLA风险溢价。**

只有当它持续高于GPUaaS每GPU小时贡献时，才把GPU从租赁池转入Inference池。纯按实际Token结算、没有最低消费承诺的合同，不应成为大规模迁卡依据。

### 最新竞争坐标

总体顺序本期不调整，以下仍是分析框架而非 Gartner 官方排名：

- **Ceiling：** 阿里云 → 火山引擎 → 腾讯云 → 百度智能云 → 华为云
- **SenseCore Arena：** 天翼云 → SenseCore 商汤大装置 → 金山云 → 并行科技 → 曙光先进计算云 → 首都在线 → UCloud
- **Chasers & Adjacent：** 硅基流动 → PPIO 派欧云 → 无问芯穹 → 趋境科技 → 基流科技 → ZStack

但在细分维度上发生两项变化：

1. **Token分发与Inference GTM：** 火山与阿里继续拉开与其他国内玩家的差距；腾讯通过TokenHub、WorkBuddy和CodeBuddy快速补位。
2. **独立Token Hub的战略位置：** 市场需求得到验证，但护城河必须从“聚合模型”升级为跨芯片Serving效率、专属部署、中立性和可验证毛利。

### 未来 3—12 个月观察指标

1. 字节是否披露 40 亿美元 ARR 的外部客户、实际确认收入、内部调用和产品边界。
2. 阿里、腾讯、火山 Coding/Token Plan 的真实付费用户、续费率、平均Token消耗和推理毛利。
3. Coding Agent 是否从个人订阅进入企业集中采购，并产生可预测的Reserved Inference需求。
4. Kimi、智谱、DeepSeek、硅基流动和趋境是否签订更长期的外部算力或Token产能合同。
5. SenseCore Inference池的合同覆盖率、每GPU小时毛利、Top 1/Top 3客户集中度，以及GPUaaS与Inference之间的可逆调度时间。
6. CoreWeave、Nebius等Neocloud的新增融资成本、合同期限和客户集中度；资本成本是否开始限制扩张速度。

### 主要风险与口径提示

- 字节 40 亿美元 ARR 目前来自媒体“按平均消耗年化”的说法，不等于审计收入，也不能直接与IDC公有云MaaS市场规模或火山引擎AI Infra收入比较。
- Coding Plan标称折扣不能直接代表底层Inference毛利，套餐并发限制、模型路由、缓存命中和用户未用完额度都会改变真实经济性。
- IDC的平均每Token收入下降是根据市场预测做出的混合口径推算，不是任何单一模型或厂商的价格预测。
- 大模型公司和Token Hub既可能是SenseCore客户，也可能自建推理或反向成为竞争者；合同的最低承诺比客户品牌更重要。

### 主要来源

- [每日经济新闻：字节调整豆包、飞书与火山引擎产品及GTM](https://www.nbd.com.cn/articles/2026-07-30/4526528.html)
- [新浪科技：字节大模型业务ARR约40亿美元的媒体口径](https://finance.sina.com.cn/tech/roll/2026-07-30/doc-inikqcsp5217058.shtml)
- [IDC：中国MaaS市场Token量与收入预测](https://www.idc.com/resource-center/blog/%E4%B8%AD%E5%9B%BDmaas%E5%B8%82%E5%9C%BA%E8%BF%9B%E5%85%A5%E9%AB%98%E9%80%9F%E5%A2%9E%E9%95%BF%E6%9C%9F%EF%BC%8Ctoken%E7%BB%8F%E6%B5%8E%E4%BB%8E%E6%A6%82%E5%BF%B5%E8%B5%B0%E5%90%91%E8%A7%84%E6%A8%A1-2/)
- [阿里云百炼 Token Plan](https://help.aliyun.com/zh/model-studio/token-plan-overview)
- [阿里云百炼 Coding Plan](https://help.aliyun.com/zh/model-studio/coding-plan)
- [Alibaba Cloud：Qwen-Coder-Qoder](https://www.alibabacloud.com/blog/603370)
- [腾讯云 TokenHub Token Plan](https://cloud.tencent.com/document/product/1823/130060)
- [腾讯云 Coding Plan](https://cloud.tencent.com/document/product/1823/130092)
- [腾讯云 WorkBuddy](https://intl.cloud.tencent.com/zh/document/product/1300/81046)
- [百度智能云：文心快码 Comate](https://comate.baidu.com/zh/news?tab=news)
- [OpenAI Codex What's New](https://developers.openai.com/codex/whats-new)
- [OpenAI GPT-5.6及7月30日价格更新](https://openai.com/index/gpt-5-6/)
- [Anthropic Claude应用Release Notes](https://docs.anthropic.com/en/release-notes/claude-apps)
- [FT：CoreWeave与Anthropic合同相关融资条款](https://www.ft.com/content/9d2117af-b3ec-4ca4-b00f-6813ab5075ec)

## 2026-07-28｜超节点走向 Cloud 化，Hyperscaler 算力缺口外溢

**观察区间：2026-07-21—2026-07-28**

### 本周结论

1. **国内竞争单位正在从“GPU 资源”升级为“超节点 + 调度软件 + Token 交付”。** 阿里云将 64 卡灵骏真武 M890 超节点做成标准化 Public Cloud 实例，并提出 Agent Native Cloud；华为 Atlas 950 SuperPoD 则继续强化芯片、互联、集群与 Cloud 的垂直一体化。国内 Hyperscaler 的天花板不仅是 GPU 数量，而是把硬件工程能力变成可持续销售的 Cloud 服务。
2. **SenseCore 的身位上升点在国产异构集群运营，而不是再造一个综合公有云。** “银河计划”提出联合近 20 家伙伴共建 5 个万卡级国产智算集群。如果后续能披露实际交付、利用率与外部客户收入，它会增强 SenseCore 的 Ability to Execute；现阶段仍应把“生态计划”与“已投产、已付费产能”分开。
3. **Token-first AI Infra 获得更清晰的独立品类验证。** 硅基流动的港交所申请文件把自身定义为连接算力、模型与应用的 Token Supply Platform，并披露 2026 年 4 月日均 Token 吞吐量约 5,785 亿、峰值约 10,714 亿。轻资产玩家的护城河越来越取决于跨芯片适配、推理引擎、调度与稳定交付，而不是转售 GPU。
4. **海外 Neocloud 的需求逻辑本周得到 Hyperscaler 侧验证。** Alphabet 明确表示将在 2026 年第三季度扩大使用第三方算力作为过渡，同时把全年 CapEx 指引提高到 1,950亿—2,050 亿美元。结论不是 Hyperscaler 停止自建，而是供给缺口足够大，使第三方 AI Cloud 在一段时间内仍有窗口；代价是采购第三方产能会对 Cloud margin 造成压力。
5. **国内中腰部名单需要加入并行科技。** 其 2025 年营收约 11.10 亿元，其中算力服务约 10.21 亿元、同比增长 66.31%，业务重叠度足以进入 SenseCore Arena；但算力服务毛利率降至 22.03%，说明规模增长与盈利质量必须同时观察。

### 本周关键动态与坐标影响

| 公司 / 市场 | 已确认动态 | 对竞争坐标的影响 | 判断 |
|---|---|---|---|
| 阿里云 | WAIC 期间推出灵骏真武 M890 超节点 Public Cloud 实例，提供 64 卡高性能算力单元；同时提出 Agent Native Cloud | 继续强化国内 Ceiling 第一梯队；竞争从 GPU IaaS 延伸至 Agent 全栈 | **上调 Completeness of Vision** |
| 华为云 | Atlas 950 SuperPoD 真机亮相，单机柜 64 卡，可组成 1,024 卡集群并继续向更大规模扩展 | 国产芯片—互联—集群—Cloud 的垂直闭环更完整；对需要国产化的政企市场尤其强 | **上调技术执行预期** |
| SenseCore 商汤大装置 | 联合近 20 家伙伴发起“银河计划”，目标共建 5 个万卡级国产智算集群 | 从单体重资产 AI Cloud 向国产算力聚合与运营平台延伸；短期仍需验证投产和外部收入 | **Arena 身位稳中偏强** |
| 硅基流动 | 港交所申请文件披露超过 1,000 万注册用户、超过 1.3 万家企业客户和快速增长的 Token 吞吐量 | Token-first 模式从产品概念进入可量化商业验证阶段；与 SenseCore 的推理层竞争增强 | **Chaser 第一位更加稳固** |
| Alphabet / 全球 Neocloud | Google 计划在 Q3 扩大第三方算力使用，并上调全年 CapEx 指引 | CoreWeave、Nebius、Lambda、Crusoe 等获得需求侧验证，但其上限仍受制于客户集中、融资成本与长期合同质量 | **Neocloud 需求逻辑增强** |
| Nebius | 据监管文件报道，NVIDIA 持股比例升至约 9.3% | 芯片厂对战略 AI Cloud 的绑定加深，融资与供货能力改善；不等于客户多元化问题已经解决 | **资本与供给能力上调** |
| 并行科技 | 2025 年算力服务收入约 10.21 亿元，占总营收约 92% | 已不是仅做 HPC 软件或项目交付的边缘玩家，应进入 SenseCore 的现实竞对层 | **新加入 SenseCore Arena** |

### 最新 China 竞争坐标

以下顺序是本周分析框架，不是 Gartner 官方排名。

- **Ceiling：** 阿里云 → 火山引擎 → 腾讯云 → 百度智能云 → 华为云
- **SenseCore Arena：** 天翼云 → SenseCore 商汤大装置 → 金山云 → 并行科技 → 曙光先进计算云 → 首都在线 → UCloud
- **Chasers & Adjacent：** 硅基流动 → PPIO 派欧云 → 无问芯穹 → 趋境科技 → 基流科技 → ZStack

本周调整只有一项：**并行科技进入 Arena 并排在金山云之后；青云科技移出主卡片。** 原因不是青云没有 AI 能力，而是相较 SenseCore，本周可验证的 GPU Cloud 收入体量、算力服务增速与直接竞争相关度更弱。

### 对 SenseCore 的含义

按本系列沿用的工作假设——SenseCore 仅计底层 GPU IaaS/MaaS、Token inference、部署与专家服务，不含日日新模型及上层应用；固定资产约 150 亿元，2025 年收入约 25 亿元、2026 年约 40 亿元——本周变化带来三点判断：

1. **向上追 Hyperscaler：差距没有缩小。** 阿里和华为的超节点发布说明 Ceiling 玩家正在把芯片、网络、调度、开发平台和 Agent 服务一起产品化。SenseCore 很难靠单纯扩 GPU 数量追平，必须证明国产异构集群的利用率、稳定性和 Token 单位成本。
2. **横向竞争更拥挤。** 天翼云拥有算力网与政企渠道；金山云、并行科技、首都在线和 UCloud 提供不同形态的 GPU Cloud；曙光强调国产集群交付。SenseCore 的差异化应落在“大规模集群运营 + 推理优化 + 专家服务”的组合，而不是泛化为综合 Cloud。
3. **向下的推理软件压力加大。** 硅基流动披露的数据证明，Token-first 平台可以在不自持同等规模固定资产的情况下形成吞吐、用户与企业客户规模。SenseCore 需要持续提高 Token & Inference 收入占比，才能改善重资产回报。

### 海外对照

- **天花板：** Google Cloud、AWS、Microsoft Azure。它们的核心优势是全球 Region、开发者与企业生态、资本开支和全栈平台。
- **同身位 / 追赶目标：** CoreWeave、Nebius、Lambda、Crusoe。CoreWeave 的商业化与软件栈领先，Nebius 的资本与大客户合同能力快速上升；Lambda 与 Crusoe 分别代表开发者平台和能源—数据中心垂直整合路线。
- **本周最重要的验证：** Google 一边把 CapEx 提高到约 2,000 亿美元量级，一边仍需采购第三方算力。这说明 Neocloud 的窗口来自“需求增长快于 Hyperscaler 自建速度”，而不是替代 Hyperscaler。

### 下周观察清单

1. “银河计划”是否披露 5 个万卡集群的地点、芯片组合、投产时间、资本承担方与首批付费客户。
2. 阿里云 M890 实例的正式可用 Region、价格、SLA、训练效率与外部客户案例。
3. 硅基流动上市进度，以及 Public Cloud、私有化部署、算力采购成本和毛利率的进一步披露。
4. CoreWeave、Nebius 等 Neocloud 的收入、backlog、客户集中度、融资成本与新增数据中心进度。
5. Google 扩大第三方算力采购后，最终订单落到哪些 Neocloud，以及合同期限和 margin 结构。

### 主要来源

- [商汤大装置：“银河计划”与 5 个万卡级国产智算集群](https://www.sensetime.com/cn/news/51170766)
- [阿里云 WAIC 2026：灵骏真武 M890 超节点与 Agent Native Cloud](https://finance.sina.com.cn/tech/roll/2026-07-21/doc-iniiqquw9170398.shtml)
- [华为 Atlas 950 SuperPoD 在 WAIC 2026 亮相](https://www.c114.com.cn/news/16/a1314164.html)
- [硅基流动港交所申请文件](https://www1.hkexnews.hk/app/sehk/2026/108701/documents/sehk26063002928.pdf)
- [Alphabet 2026 Q2 Earnings Call](https://abc.xyz/investor/events/event-details/2026/2026-Q2-Earnings-Call-2026-GgTAq7Is0z/default.aspx)
- [CoreWeave：2026 Gartner Magic Quadrant for Cloud AI Infrastructure Visionary](https://investors.coreweave.com/news/news-details/2026/CoreWeave-Named-a-Visionary-in-the-2026-Gartner-Magic-Quadrant-for-Cloud-AI-Infrastructure/default.aspx)
- [NVIDIA 持有 Nebius 约 9.3% 股份的监管文件报道](https://www.investopedia.com/nvidia-reveals-a-big-stake-in-this-ai-cloud-company-sending-its-stock-soaring-nebius-nbis-update-12023486)
- [并行科技 2025 年年度报告](https://vip.stock.finance.sina.com.cn/corp/view/vCB_AllBulletinDetail.php?id=12063904&stockid=920493)

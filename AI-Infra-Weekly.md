# AI Infra 周报

> 聚焦中国与海外 Cloud AI Infrastructure、Neocloud 与 AI-native Infra。最新一期始终置于顶部；事实优先采用公司公告、监管文件和官方财报，分析判断不等同于公司指引或 Gartner 官方结论。

---

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

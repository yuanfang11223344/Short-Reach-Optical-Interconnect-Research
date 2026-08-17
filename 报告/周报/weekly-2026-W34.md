# 芯片互连与AI基础设施 每周综述 2026-W34

> 生成时间：2026-08-17 10:00（Asia/Shanghai）。周一例行周报；已先生成 2026-08-17 日报，并纳入其中 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-08-17，后续日报会继续作为 W34 周报素材滚动更新。

## 本周最重要的 5-8 件事

### 🔥 HotOptics 2026 今天把光互连放进 AI 系统三层架构
- 要点：SIGCOMM HotOptics 2026 于 2026-08-17 举行，议程按 AI Scale-Up、AI Scale-Out、AI Scale-Across 分为三段，覆盖 AI Cluster Communications、pure photonic networks、open scale-across optical networks 等主题。[来源](https://conferences.sigcomm.org/sigcomm/2026/hotoptics/)
- 为什么重要：这代表光互连已不再只是模块或器件议题，而是进入 rack-scale、cluster-scale 和 geo-distributed AI 的系统设计讨论。

### 🔥 Hot Interconnects 2026 本周开会，主题直指 scale-up/scale-out/scale-across 边界
- 要点：HotI 2026 将于 2026-08-19 至 2026-08-21 线上举行，主题为 “Scale-Up, Scale-Out, Scale-Across: Do they really differ?”，关注 long-distance 场景下 jitter、burst、congestion、tail latency 与全栈干预。[来源](https://hoti.org/2026/call-for-papers.html)
- 为什么重要：AI 训练和分布式推理正在模糊机内、机柜内、机房内和跨机房互连的边界，互连协议、光传输和调度软件需要共同评审。

### 🔥 Lumentum 和 Coherent 同周财报验证 AI optics 主线
- 要点：Lumentum FY2026 Q4 revenue 为 10.1 亿美元，并强调 1.6T adoption、OCS、CPO lasers、ELS、NPO engagement；Coherent FY2026 Q4 revenue 为 20.5 亿美元，继续受 datacenter/communications 需求拉动。[来源](https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Fourth-Quarter-and-Full-Fiscal-Year-2026-Results/default.aspx)
- 为什么重要：AI optics 的产业焦点已经从 800G/1.6T pluggable 扩展到 InP/laser 产能、optical circuit switching、CPO/NPO 和系统级可服务性。

### 🔥 CoreWeave Q2 2026 把 AI cloud 扩容约束推到 GW 级
- 要点：CoreWeave 披露 active power 增加近 500MW 至 1.5GW，total contracted power 约 3.7GW，并完成 NVIDIA Vera Rubin NVL72 的 bring-up and validation。[来源](https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Second-Quarter-2026-Results/default.aspx)
- 为什么重要：GPU 集群交付已经取决于电力、液冷、光模块、网络拓扑和机房工程的同步推进。

### ⭐ NVIDIA Hot Chips 2026 议程强化平台化 AI factory 叙事
- 要点：NVIDIA 在 Hot Chips 2026 展示 Vera CPU、Rubin GPU、NVLink Switch、Spectrum-X Ethernet、BlueField-4 DPU 等组件，并把 Vera Rubin NVL72 描述为 rack-scale platform。[来源](https://www.nvidia.com/en-us/events/hot-chips-conference/)
- 为什么重要：NVIDIA 正把 scale-up、scale-out、DPU、CPU 和软件栈绑定为平台，开放 Ethernet/UALink/UEC 生态需要从系统可用性而非单项指标竞争。

### ⭐ Foundry-compatible silicon photonics MEMS switch 值得纳入 OCS 跟踪
- 要点：arXiv:2608.03146 展示 zero-change foundry-compatible silicon photonics MEMS optical switch，摘要给出 >30dB extinction ratio、<1.5dB insertion loss 和约 20nW static power。[来源](https://arxiv.org/abs/2608.03146)
- 为什么重要：OCS 能否进入 AI fabric，不只看光学性能，还看制造兼容、封装、控制、电热可靠性和规模运维。

## 本周关键技术进展 3 篇深读

### 1. 光互连从“模块速率竞赛”转向 AI 系统分层
- 背景：过去 800G/1.6T 讨论常围绕 pluggable module、DSP、LPO/CPO、SerDes speed 展开。
- 本周信号：HotOptics 2026 把议程明确拆成 AI Scale-Up、Scale-Out、Scale-Across，并将 optical switching、co-packaged optics、coherent pluggable、hollow-core fiber、photonic accelerators 等放入统一范围。[来源](https://conferences.sigcomm.org/sigcomm/2026/hotoptics/)
- 推演：后续产业评估会更多问“这套光技术解决哪一层 AI 通信问题”，而不只是“单端口多少 T、每 bit 多少 pJ”。scale-up 更关注低时延、封装和一致性；scale-out 更关注拥塞和 reconfigurable fabric；scale-across 更关注光传输、同步、调度和容错。

### 2. AI Ethernet 与专有互连进入平台化竞争
- 背景：NVIDIA 的 NVLink/InfiniBand/Spectrum-X 与开放 UEC/UALink 路线在 scale-up 与 scale-out 层形成不同生态。
- 本周信号：NVIDIA Hot Chips 2026 页面把 Vera Rubin NVL72、NVLink Switch、Quantum-X800、Spectrum-X、BlueField-4 放在同一平台叙事中；HotI 主题同时关注 scale-up、scale-out、scale-across 是否真的不同。[来源](https://www.nvidia.com/en-us/events/hot-chips-conference/)
- 推演：未来采购不会只比较 Ethernet vs InfiniBand 或 UALink vs NVLink，而会比较整套 AI factory 的可部署性，包括网络遥测、拥塞控制、作业调度、故障隔离、可服务性和供应链。

### 3. AI optics 财报指标开始映射到系统瓶颈
- 背景：Lumentum、Coherent 等光器件/模块厂商过去主要被看作 transceiver 或 laser supplier。
- 本周信号：Lumentum 财报强调 1.6T adoption、OCS、CPO lasers、ELS modules、NPO engagements；Coherent Q4 revenue 达 20.5 亿美元，AI data center 光连接继续成为增长变量。[来源](https://www.coherent.com/news/press-releases/fourth-quarter-and-fiscal-year-2026-results)
- 推演：optics 供应链的关键约束会从“模块能否交货”扩展到 InP/laser 产能、CPO external laser source、OCS 控制、NPO 热/维护、multi-rail 系统集成，以及 hyperscaler 对长期产能的绑定。

## 厂商动态汇总

| 厂商 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| Lumentum | FY2026 Q4 revenue 10.1 亿美元，强调 1.6T、OCS、CPO lasers、ELS、NPO | AI optics、laser、OCS、CPO/NPO | https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Fourth-Quarter-and-Full-Fiscal-Year-2026-Results/default.aspx |
| Coherent | FY2026 Q4 revenue 20.5 亿美元，继续受 AI datacenter optics 拉动 | InP、transceiver、photonics capacity | https://www.coherent.com/news/press-releases/fourth-quarter-and-fiscal-year-2026-results |
| CoreWeave | active power 至 1.5GW，contracted power 约 3.7GW，完成 Vera Rubin NVL72 bring-up/validation | AI data center、GPU networking、power/cooling | https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Second-Quarter-2026-Results/default.aspx |
| NVIDIA | Hot Chips/HotI 议程覆盖 Rubin、NVLink、Spectrum-X、BlueField-4 与 gigascale networking | AI factory platform、scale-up/out/across | https://www.nvidia.com/en-us/events/hot-chips-conference/ |
| OIF | current work 覆盖 CEI-224G/448G、CMIS、EEI、NPO/COI | standardization、interop | https://www.oiforum.com/technical-work/current-work/ |
| Vertiv | 扩大 AI-ready cooling 产能，并强调液冷效率评估 | liquid cooling、heat rejection、facility | https://www.prnewswire.com/news-releases/vertiv-expands-global-manufacturing-capacity-for-ai-ready-data-center-cooling-solutions-302830933.html |
| Lightmatter | HotI 2026 主题演讲覆盖 high-radix photonic interconnect 与 inference prefill | photonic interconnect、AI inference | https://lightmatter.co/event/hot-interconnects/ |
| UEC | 将参加 AI Infra Summit 2026 | AI/HPC Ethernet、scale-out fabric | https://ultraethernet.org/event/uec-at-ai-infra-summit-2026/ |

## 趋势观察

- **Scale-up、scale-out、scale-across 正在被同一套 AI workload 压力重新定义。** HotOptics 与 HotI 本周议程同时强化三层视角，后续技术路线应先定位通信层级，再比较 SerDes、optics、protocol 和调度软件。[来源](https://hoti.org/2026/call-for-papers.html)
- **AI optics 的商业验证正在前移到 OCS、CPO/NPO 和 ELS。** Lumentum 和 Coherent 财报说明，光连接需求不只来自 800G/1.6T 模块替换，还来自 in-rack optical penetration、optical switching 和 laser supply chain。[来源](https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Fourth-Quarter-and-Full-Fiscal-Year-2026-Results/default.aspx)
- **电力和液冷是互连部署节奏的硬约束。** CoreWeave active power 与 contracted power 数据表明，GPU 网络能否扩展取决于站点供电、冷却、网络和运维工具是否同时就绪。[来源](https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Second-Quarter-2026-Results/default.aspx)
- **OCS 研究开始强调制造和控制可落地。** Zero-change foundry-compatible MEMS switch、xSwitch、pure photonic networks 等方向显示，研究重点正在从单点光器件进入网络控制与可部署性。[来源](https://arxiv.org/abs/2608.03146)

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| HotOptics 2026 论文/演讲材料 | 2026-08-17 后 | AI optical scale-up/out/across 论文是否公开 slides 或 artifact | https://conferences.sigcomm.org/sigcomm/2026/hotoptics/ |
| Hot Interconnects 2026 | 2026-08-19 至 2026-08-21 | accepted papers、NVIDIA keynote、optical/AI networking 议题 | https://hoti.org/2026/call-for-papers.html |
| Hot Chips 2026 | 2026-08-23 至 2026-08-25 | Vera/Rubin、NVLink Switch、Spectrum-X multiplane architecture | https://www.nvidia.com/en-us/events/hot-chips-conference/ |
| IEEE P802.3dj 后续资料 | 持续跟踪 | D3.x comment、1.6TbE optical/electrical convergence | https://www.ieee802.org/3/dj/public/adhoc/electrical/index.html |
| AI Infra Summit 2026 | 2026-09-15 至 2026-09-17 | AI data centers、data movement、UEC/UALink、physical infrastructure | https://www.ai-infra-summit.com/ |
| OIF 224G/448G 项目更新 | 持续跟踪 | CEI-224G-linear、CEI-448G-VSR/LR、CMIS/EEI/NPO | https://www.oiforum.com/technical-work/current-work/ |

## 📱 分享卡片

- 本周互连关键词是 scale-up、scale-out、scale-across：AI 训练和推理正在把机柜内、机房内、跨机房网络压成一个系统问题。https://hoti.org/2026/call-for-papers.html
- HotOptics 2026 显示光互连已进入 AI 系统会议核心议程，从 CPO/OCS 到 coherent transport 都被放入 AI infrastructure 讨论。https://conferences.sigcomm.org/sigcomm/2026/hotoptics/
- Lumentum 和 Coherent 财报共同说明，AI optics 正从 800G/1.6T 模块需求扩展到 OCS、CPO/NPO、InP/laser 产能。https://www.coherent.com/news/press-releases/fourth-quarter-and-fiscal-year-2026-results
- CoreWeave 的 1.5GW active power 提醒：互连部署速度最终受电力、冷却、光模块和网络运维共同限制。https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Second-Quarter-2026-Results/default.aspx
- Foundry-compatible silicon photonics MEMS switch 是 OCS 走向规模部署的重要研究信号，制造兼容性和控制面同样关键。https://arxiv.org/abs/2608.03146

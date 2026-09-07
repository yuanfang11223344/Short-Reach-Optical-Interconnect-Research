# 芯片互连与AI基础设施 每周综述 2026-W37

> 生成时间：2026-09-07 10:00（Asia/Shanghai）。周一例行周报；已先生成 `2026-09-07.md`，并纳入其中 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-09-07，后续日报继续作为 W37 周报滚动素材。

## 本周最重要的 5-8 件事

### 🔥 OIF 将 224G/448G、Linear optics、CMIS/C-CMIS 与 EEI 推向 ECOC 2026 多厂商互操作
- 要点：OIF 预告 ECOC 2026 展示覆盖 CEI-448G、CEI-224G 多链路类型、Linear optics、CMIS/C-CMIS 与 External Laser Small Form Factor Pluggable 等方向。https://www.oiforum.com/oif-validates-ai-era-interoperability-live-at-ecoc-2026-through-multi-vendor-demonstrations-and-expert-sessions/
- 为什么重要：AI data center 的高速 I/O 验证已经从“SerDes 单点速率”转向 host、retimer、module、management、test equipment 和 optical engine 的组合成熟度。互操作展示不能等同于量产，但它会暴露系统分工和生态短板。

### 🔥 ECOC 2026 optics 提名把 1.6T、6.4T、224G analog front-end、CPO/NPO 和 OCS 放到同一窗口
- 要点：Industry Awards 提名名单覆盖 Ciena Vesta 200 6.4T CPX、Marvell COLORZ 1600、1.6T Optical DSP Platform、OpenLight 1.6T DR8 SiPh PIC、Semtech 224Gbps/lane TIA、Jabil 1.6T DR8 LRO 等。https://www.ecocexhibition.com/industry-awards/
- 为什么重要：200G/lane optics 的真实门槛在完整供应链协同：DSP/PIC、TIA/driver、module design、linear optics、fiber attach、external laser、thermal 和 test flow 都需要同步成熟。

### 🔥 AI fabric 正在形成 UALink、UEC/Ethernet、OIF 三层分工
- 要点：UALink 官网维持规格、management 和 compliance 入口；UEC 9 月有 Member Summit 与 AI Infra Summit 节点；OIF 则承担高速电/光接口和管理面互操作。https://ualinkconsortium.org/
- 为什么重要：accelerator scale-up、cluster scale-out 与 physical-layer interop 不会由单一协议解决。真正的部署问题会出现在层间：故障隔离、拥塞控制、链路训练、telemetry、线缆/光模块可维护性和系统软件调度。

### 🔥 Scale-across networking 把 AI factory 从单园区推向跨数据中心光网络
- 要点：Nokia 文章明确区分 scale-up、scale-out、scale-across，并把 coherent pluggables、high-capacity optical line systems、multi-rail ILA、C+L band 与低时延 fiber medium 作为跨站点 AI cluster 变量。https://www.nokia.com/blog/scale-across-networking-unlocking-ai-factory-scale-with-optical-innovation/
- 为什么重要：AI 训练和大规模推理的基础设施边界正在扩展到 fiber plant、OLS、DCI、调度和数据布局。跨站点 AI 不是普通 DCI 的简单改名。

### ⭐ Broadcom AI semiconductor revenue 继续高增，Tomahawk 6 仍是 102.4T Ethernet switch silicon 公开锚点
- 要点：Broadcom Q3 FY2026 财报披露 AI semiconductor revenue 167 亿美元，同比增长 221%；Tomahawk 6/BCM78910 产品页继续定位 102.4T scale-up/scale-out AI networks。https://investors.broadcom.com/news-releases/news-release-details/broadcom-inc-announces-third-quarter-fiscal-year-2026-financial
- 为什么重要：收入高增说明 AI networking/custom silicon 景气延续，但不能由此拆分推断 Tomahawk、Jericho、DSP 或具体客户出货。技术跟踪应回到产品页、互操作和系统实测。

### ⭐ Rack-scale AI factory 的采购语言继续产品化
- 要点：Supermicro、NVIDIA、Cisco 等公开入口都在强调整柜系统、liquid cooling、validated networking、deployment 和 serviceability。https://www.supermicro.com/en/
- 为什么重要：AI 服务器厂商、网络厂商和集成商边界继续变模糊。互连研究需要同时看 NVLink domain、Ethernet fabric、power shelf、DLC、optics/cables、observability 和运维流程。

## 本周关键技术进展 3 篇深读

### 1. 224G/448G 的关键问题从“能不能跑”转为“谁承担系统复杂度”
- 背景：224G electrical lane、1.6T optics、Linear optics、LRO/LPO、CPO/NPO 和 CMIS/C-CMIS 管理面在同一代 AI switch platform 中相互耦合。
- 本周信号：OIF Q3 member meeting 与 ECOC 互操作预告同时覆盖 CEI-224G/448G、Linear Retimer、Linear optics、CMIS/C-CMIS、EEI 与 ELS。https://www.oiforum.com/oif-closes-q3-member-meeting-with-critical-implementation-agreements-for-high-speed-networks/
- 推演：后续最重要的不是单个器件标称速率，而是 equalization、retiming、link training、telemetry、fault isolation 和 test ownership 如何在 host ASIC、retimer、module、optical engine 和管理软件之间分配。

### 2. CPO/NPO 商业化约束正在从光电器件转向平台工程
- 背景：CPO/NPO 可以缩短 electrical channel、缓解 front-panel optics 功耗和密度压力，但也把 laser source、fiber attach、thermal interface、repair workflow 和 switch lifecycle 绑定得更紧。
- 本周信号：ECOC 提名和 Ciena Vesta 200 线索把 6.4T optical engine、external light source、linear-drive 与 CPO/NPO 放到同一窗口；Lumentum 也把 CPO laser、ELS、NPO 与 1.6T pluggables、OCS 并列讨论。https://www.fibre-systems.com/article/ciena-unveils-64t-vesta-engine-shatter-ai-power-barriers
- 推演：进入更广生态前，CPO/NPO 需要更透明的 TCO 模型：host SerDes 是否计入、laser 如何冗余、故障件如何更换、液冷接口如何标准化、CMIS/telemetry 是否足以支撑大规模运维。

### 3. Photonic interconnect 与 OCS 论文把 workload-level 指标放到中心
- 背景：AI cluster 的互连价值最终要体现在 iteration time、prefill latency、tail latency、job goodput 和故障恢复上，而不是只看端口速率。
- 本周信号：arXiv:2609.01821 评估 high-radix photonic interconnect 对 MoE inference prefill 的建模收益；arXiv:2603.07373 用 parallel OCS scheduling 处理 AI training demand matrix 与 reconfiguration delay。https://arxiv.org/abs/2609.01821
- 推演：后续引用论文时必须保留 workload、topology、batch size、traffic matrix、器件假设和模拟边界；建模收益不能直接外推为真实集群收益。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| OIF | ECOC 2026 互操作展示覆盖 CEI-448G、CEI-224G、Linear optics、CMIS/C-CMIS、EEI | SerDes、linear optics、CPO/NPO、management | https://www.oiforum.com/oif-validates-ai-era-interoperability-live-at-ecoc-2026-through-multi-vendor-demonstrations-and-expert-sessions/ |
| OIF | Q3 会议推进 CEI-224G/448G、Linear Retimer、CMIS/C-CMIS、ELS IA | 高速电接口、线性光学、外部光源 | https://www.oiforum.com/oif-closes-q3-member-meeting-with-critical-implementation-agreements-for-high-speed-networks/ |
| Broadcom | Q3 FY2026 AI semiconductor revenue 167 亿美元，同比增长 221%；Tomahawk 6 维持 102.4T 公开锚点 | AI networking、switch silicon、custom silicon | https://investors.broadcom.com/news-releases/news-release-details/broadcom-inc-announces-third-quarter-fiscal-year-2026-financial |
| Ciena | Q3 FY2026 revenue 16.7 亿美元，同比增长 37%；Vesta 200 6.4T CPX 入围 ECOC 提名 | coherent、AI DCI、6.4T optical engine | https://www.ciena.com/about/newsroom/press-releases/ciena-reports-fiscal-third-quarter-2026-financial-results |
| Lumentum | FY2026 Q4 公开材料延续 1.6T、OCS、CPO laser、ELS、NPO 方向 | lasers、pluggables、OCS、CPO/NPO | https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Fourth-Quarter-and-Full-Fiscal-Year-2026-Results/default.aspx |
| Marvell | COLORZ 1600 与 1.6T Optical DSP Platform 入围 ECOC 提名 | coherent DCI、optical DSP、1.6T | https://www.ecocexhibition.com/industry-awards/ |
| OpenLight / Semtech / Jabil | 1.6T DR8 SiPh PIC、224Gbps/lane TIA、1.6T DR8 LRO 入围 | PIC、analog front-end、module integration | https://www.ecocexhibition.com/industry-awards/ |
| Supermicro | HGX B300 systems 与 GB300 NVL72 racks 作为官网 AI 入口 | rack-scale AI server、liquid cooling、deployment | https://www.supermicro.com/en/ |
| Nokia | scale-across networking 文章聚焦跨数据中心 AI factory | coherent pluggables、OLS、multi-rail optical network | https://www.nokia.com/blog/scale-across-networking-unlocking-ai-factory-scale-with-optical-innovation/ |
| UALink | 规格、management、compliance 与事件入口持续更新 | accelerator scale-up fabric、compliance | https://ualinkconsortium.org/ |
| UEC | Member Summit 与 AI Infra Summit 进入 9 月观察窗口 | optimized Ethernet、telemetry、congestion control | https://ultraethernet.org/events/ |

## 趋势观察

- **互连竞争正在转向 responsibility partitioning。** 224G/448G 之后，equalization、retiming、telemetry、link training 和 failure isolation 放在哪一层，会直接影响功耗、成本、可维护性和多厂商互操作。https://www.oiforum.com/oif-validates-ai-era-interoperability-live-at-ecoc-2026-through-multi-vendor-demonstrations-and-expert-sessions/
- **1.6T 到 6.4T optics 的节奏不会只由模块速率决定。** ELS、CPO/NPO、LRO/LPO、thermal、fiber attach、test automation 和 switch platform integration 会共同决定部署速度。https://www.ecocexhibition.com/industry-awards/
- **AI fabric 会长期多协议共存。** UALink、NVLink、UEC/Ethernet、InfiniBand、OIF electrical/optical IA 和 coherent DCI 分别对应不同距离、故障域和软件栈。https://ualinkconsortium.org/
- **Scale-across 将把光网络重新拉入 AI architecture 决策。** 训练和推理跨园区扩展时，fiber distance、latency、OLS、coherent pluggables 和 job placement 会进入同一优化问题。https://www.nokia.com/blog/scale-across-networking-unlocking-ai-factory-scale-with-optical-innovation/
- **论文结论必须绑定证据类型。** arXiv:2609.01821 和 arXiv:2603.07373 都有明确建模和拓扑边界，适合作为架构方向线索，不应当改写成部署实测结论。https://arxiv.org/abs/2609.01821

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| UEC Member Summit 2026 | 2026-09-14 至 2026-09-16 | UET implementation、congestion control、telemetry、interoperability profile | https://ultraethernet.org/event/ultra-ethernet-consortium-member-summit-2026/ |
| AI Infra Summit 2026 | 2026-09-15 至 2026-09-17 | Data Movement track、UEC/UALink、AI data center physical infrastructure | https://ai-infra-summit.com/events/ai-infra-summit |
| ECOC 2026 Conference | 2026-09-20 至 2026-09-24 | optical communication research、coherent optics、silicon photonics、CPO/NPO | https://www.ecoc2026.org/ |
| ECOC Exhibition 2026 | 2026-09-21 至 2026-09-23 | OIF booth、1.6T/3.2T optics、CPO/NPO、silicon photonics、测试仪表 | https://www.ecocexhibition.com/ |
| OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | open rack、hardware management、rack power/cooling、open AI infrastructure | https://www.opencompute.org/summit/global-summit |
| SC26 | 2026-11-15 至 2026-11-20 | HPC/AI networking、large-scale communication libraries、system software | https://sc26.supercomputing.org/ |

## 📱 分享卡片

- W37 第一条主线：OIF ECOC 2026 把 224G/448G、Linear optics、CMIS/C-CMIS 和 EEI 放进同一互操作现场，AI 网络验证进入系统组合阶段。https://www.oiforum.com/oif-validates-ai-era-interoperability-live-at-ecoc-2026-through-multi-vendor-demonstrations-and-expert-sessions/
- ECOC 2026 optics 提名名单显示 1.6T、6.4T、224G analog front-end、CPO/NPO、OCS 正在同一供应链窗口竞争成熟度。https://www.ecocexhibition.com/industry-awards/
- UALink、UEC 和 OIF 分别覆盖 accelerator scale-up、AI Ethernet scale-out 与物理/管理互操作；AI supernode 的真实瓶颈常在层间。https://ualinkconsortium.org/
- Nokia 的 scale-across networking 提醒：跨数据中心 AI factory 会把 coherent pluggables、OLS、fiber plant 和调度延迟放进同一架构决策。https://www.nokia.com/blog/scale-across-networking-unlocking-ai-factory-scale-with-optical-innovation/
- arXiv:2609.01821 说明推理 prefill 也可能成为 high-radix photonic interconnect 的用例，但当前证据主要是建模，不是实集群实测。https://arxiv.org/abs/2609.01821

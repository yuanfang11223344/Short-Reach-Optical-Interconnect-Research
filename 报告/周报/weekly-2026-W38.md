# 芯片互连与AI基础设施 每周综述 2026-W38

> 生成时间：2026-09-14 10:00（Asia/Shanghai）。周一例行周报；已先生成 `2026-09-14.md`，并纳入其中 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-09-14，后续日报继续作为 W38 周报滚动素材。

## 本周最重要的 5-8 件事

### 🔥 AI Infra Summit 2026 明天开幕，W38 的关键词是 data movement + power/cooling + rack-scale deployment
- 要点：AI Infra Summit 2026 于 9 月 15-17 日在 Santa Clara 举办，产业参与方围绕 AI data centers、compute、data movement、storage、power/cooling 和 physical infrastructure 集中发布路线图。https://www.ai-infra-summit.com/
- 为什么重要：AI infrastructure 的瓶颈正从“GPU 是否够快”扩展到 fabric、memory、optics、storage、供电、液冷和部署流程。互连研究需要把集体通信、网络拥塞、机柜功率密度和运维可见性合并分析。

### 🔥 OIF 与 Ethernet Alliance 把 ECOC 2026 变成 1.6T/224G/管理面互操作验证窗口
- 要点：OIF 官网将 1600ZR、EEI、CEI-112G/224G、CMIS/CPO 管理列为 hot topics；Ethernet Alliance 预告 ECOC 2026 展示 400G/800G/1.6T Ethernet multi-vendor interoperability。https://www.oiforum.com/
- 为什么重要：AI 网络的可采购性不由单一模块速率决定，而由 host ASIC、retimer、module、optical engine、management、FEC、测试仪表和运维软件共同决定。

### 🔥 Corning/Verizon 光纤协议把 AI hyperscaler backbone 拉入互连视野
- 要点：Corning 9 月 8 日新闻稿称 Verizon 与 Corning 达成 2027-2032 年多十亿美元协议，覆盖 80+ million miles 高密度光纤和连接解决方案，用于宽带扩展与 AI hyperscaler 高密度 backbone。https://www.corning.com/worldwide/en/about-us/news-events/news-releases/2026/09/verizon-and-corning-announce-multi-year-multi-billion-dollar-supply-agreement-for-broadband-expansion-and-next-gen-ai-infrastructure.html
- 为什么重要：scale-across AI 不只是 coherent pluggable 或 DCI 路由器问题；fiber plant、长距离低时延路径、供给链和建设周期会影响 AI 数据中心选址与跨站点调度。

### 🔥 d-Matrix/NVIDIA 与 Qualcomm/Amazon 显示第三方 XPU 进入 rack-scale fabric 的两条路径
- 要点：d-Matrix 宣布使用 NVIDIA NVLink Fusion 连接 Raptor XPU 到 NVIDIA AI platform；Qualcomm 官网摘要称其与 Amazon 的多代合作包括 advanced optical connectivity，支持 Amazon data center networks 的高带宽互连。https://www.d-matrix.ai/
- 为什么重要：custom AI silicon 的竞争边界正在上移到 rack-scale fabric、memory、NIC/DPU、Ethernet、optics 和软件栈。没有独立系统评测前，不应把合作公告写成性能或规模部署结论。

### ⭐ UALink 与 UEC 开始进入规格、合规和产业活动的连续验证期
- 要点：UALink 官网摘要提到 Common Specification 2.0 与 200G Data Link/Physical Layer Specification 2.0；UEC 官网开放 1.0.3 规格与 AI Infra Summit 活动入口。https://ualinkconsortium.org/
- 为什么重要：scale-up 与 scale-out 的开放互连会长期共存。真正难点在 collective communication、telemetry、拥塞控制、故障域隔离和软件生态，不在命名本身。

### ⭐ 新增论文把互连问题继续推向 workload-aware 与 grid-to-chip co-design
- 要点：arXiv:2609.04025 讨论 hybrid optical-THz AI datacenter 的 collective synthesis；arXiv:2609.11649 从 grid 到 chip 梳理 AI data center power architecture 与 stability；arXiv:2609.03125 探索 analog photonic interposer。https://arxiv.org/abs/2609.04025
- 为什么重要：互连收益必须绑定 workload、拓扑、功耗和系统稳定性。建模论文很适合作为方向线索，但不能改写成实机部署证据。

## 本周关键技术进展 3 篇深读

### 1. 1.6T/224G 之后，互操作矩阵比单点规格更重要
- 背景：1.6T optics、224G electrical lane、linear optics、retimer、CMIS/C-CMIS、ELS、FEC 与 test equipment 正在同一代 AI switch platform 中相互牵制。
- 本周信号：OIF 和 Ethernet Alliance 均把 ECOC 2026 作为多厂商互操作展示窗口。https://ethernetalliance.org/
- 推演：后续要关注公开 demo 是否给出 host ASIC、module、cable/fiber、management、link training、error counter 和测试设备组合；如果只有宣传口号，仍不能视为部署成熟。

### 2. Third-party XPU 的胜负手是 fabric integration，而不只是矩阵乘性能
- 背景：推理 ASIC、custom XPU 和 hyperscaler 自研芯片需要进入整柜 memory/fabric/management 生态，才能参与大规模 AI factory。
- 本周信号：d-Matrix 选择 NVLink Fusion，Qualcomm/Amazon 合作强调 optical connectivity，Marvell 在 AI Infra Summit 展示 end-to-end connectivity portfolio。https://www.nvidia.com/en-us/data-center/nvlink-fusion/
- 推演：衡量第三方 XPU 时，需要同时看 XPU-to-XPU bandwidth、host CPU coupling、NIC/DPU、collective library、telemetry、rack power、liquid cooling 和故障恢复。单芯片 TOPS/Tokens 指标越来越不足。

### 3. AI data center 进入 grid-to-chip 约束时代
- 背景：机柜功率密度、液冷、供电架构、储能、并网容量和 workload scheduling 已经影响 AI cluster 可部署规模。
- 本周信号：arXiv:2609.11649 把 AI data center 定义为 grid-interactive computing system，并把 rack-level DC bus、facility-level converters 与 system-level grid behavior 放进同一 stability framework。https://arxiv.org/abs/2609.11649
- 推演：互连路线评估要纳入 power delivery 和 cooling：更高 radix、更短 electrical reach、CPO/NPO 或 OCS 的价值，都要回到 tokens-per-watt、job completion time、维护窗口和并网约束。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| OIF | 1600ZR/1600ZR+、EEI、CEI-224G、CMIS/CPO 管理持续作为 hot topics | Coherent DCI、224G electrical、CPO management | https://www.oiforum.com/ |
| Ethernet Alliance | ECOC 2026 预告 400G/800G/1.6T Ethernet 互操作 | AI Ethernet commercialization、test ecosystem | https://ethernetalliance.org/ |
| UALink | Common Spec 2.0 与 200G DL/PHY Spec 2.0 摘要公开 | Accelerator scale-up、open fabric | https://ualinkconsortium.org/ |
| UEC | 1.0.3 specification 与 AI Infra Summit 活动入口公开 | AI/HPC Ethernet full stack | https://ultraethernet.org/ |
| Qualcomm/Amazon | 多代 AI data center collaboration，强调 advanced optical connectivity | Custom silicon、data center networks | https://www.qualcomm.com/ |
| d-Matrix/NVIDIA | Raptor XPU 接入 NVLink Fusion rack-scale platform | Inference ASIC、NVLink Fusion ecosystem | https://www.d-matrix.ai/ |
| Corning/Verizon | 2027-2032 年 80+ million miles 高密度光纤协议 | AI backbone、fiber supply、scale-across | https://www.corning.com/worldwide/en/about-us/news-events/news-releases/2026/09/verizon-and-corning-announce-multi-year-multi-billion-dollar-supply-agreement-for-broadband-expansion-and-next-gen-ai-infrastructure.html |
| Marvell | AI Infra Summit 展示 end-to-end AI data center connectivity portfolio | Scale-up/scale-out connectivity、memory、custom silicon | https://investor.marvell.com/ |
| Ayar Labs | AI Infra Summit 入口突出 CPO 与 rack-level integration | Optical I/O、CPO readiness | https://ayarlabs.com/ |
| Supermicro | Blackwell Ultra/GB300 NVL72、DLC-2、DCBBS 继续作为整柜入口 | Rack-scale systems、power/cooling、deployment | https://www.supermicro.com/en/pressreleases/supermicro-begins-volume-shipments-nvidia-blackwell-ultra-systems-and-rack-plug-and |

## 趋势观察

- **AI interconnect 的“标准化”正在分层。** OIF 管 physical/electrical/management interoperability，Ethernet Alliance 管 Ethernet commercialization，UALink 管 accelerator scale-up，UEC 管 AI/HPC Ethernet stack；实际部署要看这些层如何共同失败和共同恢复。https://www.oiforum.com/
- **CPO/NPO 进入平台工程阶段。** 光引擎本身之外，ELS、fiber attach、thermal、liquid cooling、module management、repair workflow 和 switch lifecycle 都会影响 TCO。https://ayarlabs.com/
- **Scale-across AI 会重估 fiber plant。** Corning/Verizon 的长期协议说明高密度光纤和 backbone 建设已成为 AI hyperscaler capacity planning 的一部分。https://www.corning.com/worldwide/en/about-us/news-events/news-releases/2026/09/verizon-and-corning-announce-multi-year-multi-billion-dollar-supply-agreement-for-broadband-expansion-and-next-gen-ai-infrastructure.html
- **Third-party XPU 需要借力成熟 rack ecosystem。** NVLink Fusion、Spectrum-X、ConnectX/BlueField、optical connectivity 与 custom silicon 的组合，可能比单芯片指标更决定进入 hyperscale 的速度。https://www.nvidia.com/en-us/data-center/nvlink-fusion/
- **论文指标必须绑定假设。** THz-SynC、grid-to-chip power、analog photonic interposer 等论文都提供新方向，但都需要保留 workload、trace、拓扑、工艺和评估边界。https://arxiv.org/abs/2609.04025

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| AI Infra Summit 2026 | 2026-09-15 至 2026-09-17 | Data movement、AI data centers、power/cooling、UEC/UALink、optics | https://www.ai-infra-summit.com/ |
| Marvell at AI Infra Summit | 2026-09-15 至 2026-09-17 | End-to-end data center connectivity、custom silicon、memory | https://www.marvell.com/company/events.html |
| Ayar Labs at AI Infra Summit | 2026-09-15 至 2026-09-17 | Co-Packaged Optics、TeraPHY、rack-level integration | https://ayarlabs.com/ |
| ECOC 2026 Conference | 2026-09-20 至 2026-09-24 | Coherent optics、silicon photonics、datacenter interconnect | https://ecoc2026.org/ECOC2026 |
| ECOC Exhibition 2026 | 2026-09-21 至 2026-09-23 | OIF/Ethernet Alliance interop、1.6T、CPO/NPO/OCS | https://www.ecocexhibition.com/ |
| OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | Open rack、power/cooling、hardware management、serviceability | https://www.opencompute.org/summit/global-summit |
| SC26 | 2026-11-15 至 2026-11-20 | HPC/AI networking、collective communication、large-scale systems | https://sc26.supercomputing.org/ |

## 📱 分享卡片

- W38 主线：AI Infra Summit 把互连、power/cooling、data movement 和整柜部署放到同一工程现场，值得优先跟踪。https://www.ai-infra-summit.com/
- OIF + Ethernet Alliance + UALink + UEC 正在形成分层互连生态；AI supernode 的瓶颈常发生在层与层之间。https://ualinkconsortium.org/
- Corning/Verizon 80+ million miles 高密度光纤协议说明 AI backbone 已经进入长期供给链规划，而不只是数据中心内部网络问题。https://www.corning.com/worldwide/en/about-us/news-events/news-releases/2026/09/verizon-and-corning-announce-multi-year-multi-billion-dollar-supply-agreement-for-broadband-expansion-and-next-gen-ai-infrastructure.html
- d-Matrix 接入 NVLink Fusion、Qualcomm/Amazon 强调 optical connectivity：第三方 XPU 的竞争边界正在扩大到 fabric、memory、optics 和整柜系统。https://www.d-matrix.ai/
- 论文线索转向 workload-aware 与 grid-to-chip co-design：互连价值最终要回到 job completion、tokens-per-watt、稳定性和维护成本。https://arxiv.org/abs/2609.11649

# 芯片互连与AI基础设施 每周综述 2026-W42

> 生成时间：2026-10-12 10:00（Asia/Shanghai）。周一周报；已先补齐 `2026-10-11.md`，再生成 `2026-10-12.md`，并纳入 2026-10-12 日报中的 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-10-12；后续日报可继续作为 W42 滚动素材。

## 本周最重要的 5-8 件事

### 🔥 OCP 2026 开幕，AI interconnect 正式进入系统工程周

- 要点：OCP Global Summit 2026 的 22 个 track 覆盖 AI Open Data Center、Networking、Photonics、Short Reach Optical Interconnect、Sustainability、Systems Management、validation 和 manufacturing test。https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/
- 为什么重要：这把 SerDes、CPO/NPO、UALink、Ethernet fabric、rack power、liquid cooling、telemetry 和 open management 拉到同一个评估框架里。互连不再只是芯片或模块规格，而是 AI factory 是否可部署、可维护、可观测的一部分。

### 🔥 OIF/IPEC 明日集中讨论 224G/448G、CPO/NPO 与 pluggable NPO

- 要点：OIF Workshop 覆盖 224Gbps/448Gbps electrical channel、CPO/NPO、external laser packaging、high-density electrical interconnect、coherent optics 和 CMIS firmware methodology；IPEC workshop 聚焦 pluggable NPO for AI SuperPods/HyperPods scale-up。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/
- 为什么重要：400G/lane 与 CPO/NPO 的核心门槛正在从“能否展示高速链路”转向“供光、清洁、插拔、failure isolation、telemetry 和 firmware 是否能支撑机房运维”。

### 🔥 AMD、NVIDIA、Broadcom、Marvell 把互连放入 open AI infrastructure

- 要点：AMD keynote 关注 open full-stack infrastructure for agentic AI；NVIDIA OCP 页面覆盖 AI Factories at Scale、Spectrum-X、MGX、FBOSS、800 VDC 和 Vera Rubin NVL72；Broadcom 和 Marvell 分别展示 AI networking portfolio 与 open AI infrastructure 议程。https://newsroom.amd.com/news/media-alert-ceo-lisa-su-keynote-2026-ocp/  https://www.nvidia.com/en-us/events/ocp-summit/  https://investors.broadcom.com/news-releases/news-release-details/broadcom-redefines-ai-infrastructure-industry-leading-networking  https://www.marvell.com/company/events/ocp-global-summit-2026.html
- 为什么重要：AI 服务器和超节点竞争正在从 accelerator box 走向 XPU、switch/NIC、optics、rack power、network OS、observability 与开放标准的组合。

### ⭐ Lumentum、Ciena、Lightmatter 代表三条 AI optics 观察线

- 要点：Lumentum OCP speaker lineup 覆盖 external laser、VCSEL 和 OCS；Ciena Vesta 200 6.4T CPX 关注 scale-across optical engine；Lightmatter Passage L20 CPX BiDi 关注 Open CPX 与降低 fiber/connector 数量。https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Speaker-Lineup-at-2026-OCP-Global-Summit/default.aspx  https://www.ciena.com/insights/infobriefs/vesta-200-6-4-t-cpx-optical-engine  https://lightmatter.co/press-release/lightmatter-joins-open-cpx-msa-introduces-the-industrys-first-bidirectional-cpx-optical-engine/
- 为什么重要：AI optics 不只有一种路径。External laser 解决 CPO/NPO serviceability，CPX/CPO 解决靠近 switch/GPU 的带宽密度，OCS 解决 scale-out/scale-across 的拓扑重构。

### ⭐ Luxshare-Tech 把连接器、液冷 I/O、电源和 AI rack architecture 串起来

- 要点：Luxshare-Tech OCP 2026 页面覆盖 CPC、next-generation electrical/optical I/O、224G/448G signal integrity、1600G liquid cooling I/O、solid-state power conversion 和 integrated AI rack architectures。https://en.luxshare-tech.com/company/resources/news/luxshare-tech-ocp-2026.html
- 为什么重要：连接器/线缆/机构/电源厂商正在进入 rack-scale architecture 的定义层；短距互连的可靠性、热设计和可维护性会越来越依赖这些“非芯片”供应链。

## 本周关键技术进展 3 篇深读

### 1. CPO/NPO 的胜负手转向 serviceability

- 背景：CPO/NPO 把 optics 靠近 switch 或 compute，可以降低长电通道损耗，但也把 laser source、fiber attach、cleaning workflow、thermal coupling 和 field replacement 变成系统问题。
- 本周证据：OIF/IPEC 明确讨论 CPO/NPO、external laser packaging、CMIS firmware、pluggable NPO；Lumentum 的 OCP 主题覆盖 deployable CPO-based AI networks 与 external laser source。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/  https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Speaker-Lineup-at-2026-OCP-Global-Summit/default.aspx
- 观察指标：后续应要求发布材料说明现场替换流程、光纤清洁/检测、ELS/laser redundancy、CMIS telemetry、thermal limit、failure mode 和客户验证，而不是只看 Tbps 数字。

### 2. Scale-up interconnect 需要开放软件抽象

- 背景：AI pod 内 accelerator-to-accelerator communication 正从专有链路走向更开放的 UALink、SAI/SONiC、CMIS、OIF CEI/EEI 和 telemetry 协作。
- 本周证据：UALink OCP panel 聚焦 AI compute pod 内互连生态；Marvell OCP 议程包含 UALink-SAI、SAI telemetry 和 memory-semantic AI fabric；OCP co-located events 同时包括 SONiC 与 DMTF。https://ualinkconsortium.org/event/ocp-global-summit-2026/  https://www.marvell.com/company/events/ocp-global-summit-2026.html  https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/
- 观察指标：需要看 link training、拥塞控制、故障隔离、安全、管理面 API、telemetry schema 与 open network OS 是否能形成可部署栈。

### 3. AI factory 评估必须绑定 power/cooling/operations

- 背景：800G/1.6T 网络、CPO/NPO、OCS 和 high-radix fabric 的价值只有在 workload、rack power、liquid cooling、facility grid 和 operations 约束下才完整。
- 本周证据：NVIDIA 把 AI Factories at Scale、FBOSS、800 VDC、Spectrum-X 和 Vera Rubin NVL72 放在同一 OCP 页面；OCP 官方主题从 chiplet、in-rack cooling/power distribution 延伸到 energy storage、integrated telemetry 和 AI cluster networks。https://www.nvidia.com/en-us/events/ocp-summit/  https://www.opencompute.org/summit/global-summit/theme
- 观察指标：后续报告应优先记录 topology、power envelope、cooling interface、fault management、observability 和 workload/token economics；缺少这些上下文的互连效率声明要保守处理。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| OCP | Global Summit 2026 开幕，22 tracks 覆盖 AI datacenter、photonics、networking、SROI、validation、systems management | open AI infrastructure、系统工程 | https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/ |
| OIF / IPEC | OCP co-located workshops 聚焦 224G/448G、CPO/NPO、ELS、CMIS、pluggable NPO | electrical/optical co-design、serviceability | https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/ |
| AMD | Lisa Su OCP opening keynote 讨论 open full-stack infrastructure for agentic AI | open XPU ecosystem、AI factory | https://newsroom.amd.com/news/media-alert-ceo-lisa-su-keynote-2026-ocp/ |
| NVIDIA | OCP 页面覆盖 AI Factories at Scale、Spectrum-X、MGX、FBOSS、800 VDC、Vera Rubin NVL72 | rack-scale AI factory、Ethernet fabric、operations | https://www.nvidia.com/en-us/events/ocp-summit/ |
| Broadcom | 展示 Tomahawk/Jericho/Thor/TH6-Davisson CPO AI networking portfolio | Ethernet scale-up/scale-out、CPO partner demos | https://investors.broadcom.com/news-releases/news-release-details/broadcom-redefines-ai-infrastructure-industry-leading-networking |
| Marvell | OCP 议程含 UALink-SAI、SAI telemetry、memory-semantic AI fabric、custom HBM | switch/interconnect/software abstraction | https://www.marvell.com/company/events/ocp-global-summit-2026.html |
| Lumentum | OCP topics 覆盖 external laser、VCSEL、OCS、deployable CPO networks | CPO/NPO 供光、D2D、OCS | https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Speaker-Lineup-at-2026-OCP-Global-Summit/default.aspx |
| Ciena | Vesta 200 6.4T CPX 与 OCP 页面聚焦 AI scale-across connectivity | CPX optical engine、可维护 optics | https://www.ciena.com/insights/infobriefs/vesta-200-6-4-t-cpx-optical-engine |
| Lightmatter | Passage L20 CPX BiDi 作为 Open CPX optical engine 样本 | BiDi CPX、fiber/connector reduction | https://lightmatter.co/press-release/lightmatter-joins-open-cpx-msa-introduces-the-industrys-first-bidirectional-cpx-optical-engine/ |
| Luxshare-Tech | OCP 展示 224G/448G SI、1600G liquid cooling I/O、solid-state power、AI rack architecture | connector/cable/power/rack integration | https://en.luxshare-tech.com/company/resources/news/luxshare-tech-ocp-2026.html |

## 趋势观察

- **OCP 把互连从器件发布拉回系统边界。** SerDes、CPO/NPO、UALink、Spectrum-X、800 VDC、rack power、liquid cooling 与 systems management 必须一起看。https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/
- **CPO/NPO 的“可服务化”比峰值带宽更值得盯。** External laser、pluggable NPO、CMIS telemetry、fiber cleaning、field replacement 和 failure isolation 会决定进入客户机房的速度。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/
- **开放 scale-up pod 需要多层标准协同。** UALink 解决 accelerator pod 连接，OIF 解决高速 electrical/optical interface，OCP/SONiC/SAI/DMTF 解决系统管理与部署生态。https://ualinkconsortium.org/event/ocp-global-summit-2026/
- **AI optics 供应链正在分层。** ELS、VCSEL D2D、CPX/CPO/NPO、OCS、optical engine、connector/cable/power/rack integration 分别对应不同距离和不同运维边界。https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Speaker-Lineup-at-2026-OCP-Global-Summit/default.aspx
- **当前证据仍需保守。** 今天的强证据主要是官方议程、会前材料和论文；若 OCP 现场出现新指标、客户案例或量产时间，需要原始来源逐条核验。https://www.opencompute.org/summit/global-summit/theme

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | AI clusters、photonics、networking、validation、power/cooling | https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/ |
| OIF Workshop @ OCP | 2026-10-13 | 224G/448G、CPO/NPO、ELS、CMIS、coherent optics | https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/ |
| IPEC Optical Interconnect Workshop @ OCP | 2026-10-13 | Pluggable NPO、AI SuperPods/HyperPods scale-up | https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/ |
| UALink panel @ OCP | 2026-10-14 | UALink ecosystem、scale-up AI pods | https://ualinkconsortium.org/event/ocp-global-summit-2026/ |
| Optica/APC PECC Summit | 2026-10-20 至 2026-10-21 | Photonic-enabled cloud computing、OCS、memory wall、short-reach optical interconnect | https://www.optica.org/events/industry_events/2026/pecc_summit_optica_apc_photonic_enabled_cloud_computing_summit/ |
| SC26 | 2026-11-15 至 2026-11-20 | HPC/AI networking、large-scale systems、workload evidence | https://sc26.supercomputing.org/attendees/ |

## 📱 分享卡片

- W42 开局主线：OCP 2026 把 AI interconnect 从 lane rate 推向 open infrastructure、rack-scale operations 和 serviceability。https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/
- CPO/NPO 要过的工程关包括 external laser、CMIS、fiber attach、清洁维护、热耦合、故障定位和现场替换。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/
- AMD、NVIDIA、Broadcom、Marvell 的 OCP 线索要放在 AI factory 系统里读：XPU、switch、NIC/DPU、optics、power、cooling、network OS 缺一不可。https://www.nvidia.com/en-us/events/ocp-summit/
- Lumentum、Ciena、Lightmatter、Luxshare-Tech 代表 AI optics 与 rack supply chain 的几条关键路线：ELS/VCSEL/OCS、CPX optical engine、BiDi CPX、连接/液冷/电源。https://en.luxshare-tech.com/company/resources/news/luxshare-tech-ocp-2026.html
- 保守判断：本周刚开始，当前周报以 10 月 12 日日报和 OCP 官方材料为基础；后续现场发布需要逐条刷新和核验。https://www.opencompute.org/summit/global-summit/theme

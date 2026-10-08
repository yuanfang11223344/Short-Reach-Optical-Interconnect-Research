# 芯片互连与AI基础设施 每周综述 2026-W41

> 生成时间：2026-10-08 11:20（Asia/Shanghai）。断档补齐周报；已补齐并纳入 2026-10-05 至 2026-10-08 日报中的 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-10-05 至 2026-10-08；后续日报可继续作为 W41 滚动素材。

## 本周最重要的 5-8 件事

### 🔥 OCP 2026 前夜，AI interconnect 的议题从器件展示转向系统工程

- 要点：OCP 官方 22 个 track 覆盖 AI Clusters、Networking、Photonics、Short Reach Optical Interconnect、validation、power/cooling 与 systems management；AI Clusters 明确包含 scale-up、scale-out、scale-across networking、800G/1.6T interconnects、cluster telemetry 与 liquid cooling。https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/
- 为什么重要：这说明下一阶段判断 CPO/NPO/1.6T/UALink 的方式，不应只看模块或 lane rate，而要看 rack、电力、液冷、管理面、制造测试和 workload telemetry 是否能闭环。

### 🔥 OIF 与 IPEC co-located workshops 把 CPO/NPO 关键问题摊到桌面

- 要点：OIF workshop 明确覆盖 224G/448G electrical channel、CPO/NPO architectures、external laser packaging、high-density electrical interconnect、coherent optics 与 CMIS firmware methodology；IPEC workshop 聚焦 pluggable NPO 对 AI SuperPods scale-up 的意义。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/
- 为什么重要：CPO/NPO 的核心门槛正在从“能否发光”转为“是否可部署、可管理、可维护、可跨厂商互通”。

### 🔥 UALink 继续推动开放 scale-up accelerator interconnect

- 要点：UALink Consortium 将在 OCP 2026 举办 “Powering AI at Scale: Inside the UALink Ecosystem” panel，官方说明 UALink 面向 AI compute pod 内 accelerator 与 switch 之间的低时延、高带宽互连。https://ualinkconsortium.org/event/ocp-global-summit-2026/
- 为什么重要：如果 UALink、SAI、SONiC、telemetry 与 optical/electrical PHY 能形成更开放的抽象，AI scale-up pod 的供应链多样性会提高；但真实部署仍需客户系统验证。

### 🔥 NVIDIA、AMD、Marvell 把 AI factory 的竞争带到 open infrastructure 语境

- 要点：NVIDIA OCP 页面强调 AI Factories at Scale、MGX ecosystem、FBOSS、800 VDC、Spectrum-X 与 Vera Rubin NVL72；AMD 宣布 Lisa Su 将在 OCP opening keynote 讨论 open full-stack infrastructure for agentic AI；Marvell OCP 议程覆盖 connectivity-bound AI、SAI telemetry、memory-semantic fabric 与 UALink-SAI。https://www.nvidia.com/en-us/events/ocp-summit/  https://newsroom.amd.com/news/media-alert-ceo-lisa-su-keynote-2026-ocp/  https://www.marvell.com/company/events/ocp-global-summit-2026.html
- 为什么重要：AI 服务器/超节点的竞争不再是 GPU 盒子单点，而是芯片、switch、DPU/NIC、rack power、network OS、observability 和 interconnect 标准的组合。

### ⭐ Lumentum 把 external laser、VCSEL D2D 与 OCS 放进 OCP 议程

- 要点：Lumentum 宣布 OCP 2026 speaker lineup，主题覆盖 deployable CPO-based AI networks 的 external laser source、12.8T VCSEL solutions、Zero-Touch OCS fabrics；此前 ECOC 材料还包括 DWDM ELSFP 与 1060 nm VCSEL optical D2D demo。https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Speaker-Lineup-at-2026-OCP-Global-Summit/default.aspx  https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx  https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Qualcomm-and-Corning-to-Demonstrate-High-Density-1060-nm-VCSEL-Optical-D2D-Connectivity-for-AI-Scale-Up-at-ECOC-2026/default.aspx
- 为什么重要：AI optics 供应链正在同时探索三类路径：external laser source 解决 CPO/NPO 可维护性，VCSEL/D2D 解决近距离高密度连接，OCS 解决 scale-out/scale-across 的动态拓扑。

### ⭐ Marvell Investor Day 强化“connectivity at every distance”叙事

- 要点：Marvell Investor Day 2026 官方页称管理层讨论公司战略、增长机会以及在下一代 AI 和数据中心基础设施中的角色；公司活动页还列出 OCP Global Summit、AI Networking Summit、SC26 等后续节点。https://www.marvell.com/company/events/investor-day-2026.html  https://www.marvell.com/company/events.html
- 为什么重要：Marvell 的公开材料把 custom silicon、switching、memory/storage、optical DSP/SiPh/CPO 等串成 AI infrastructure portfolio；需要继续区分战略叙事、demo 与客户规模部署。

## 本周关键技术进展 3 篇深读

### 1. CPO/NPO 进入“可部署性”阶段

- 背景：CPO/NPO 的短 electrical reach 有助于降低 I/O 功耗，但会把 laser source、fiber attach、thermal coupling、cleaning workflow 和 field replacement 推到系统边界。
- 本周证据：OIF workshop 把 CPO/NPO、external laser packaging、CMIS firmware 放入同一议题；IPEC workshop 专门讨论 pluggable NPO；Lumentum 的 DWDM ELSFP 说明 external laser source 正在被做成可服务模块。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/  https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx
- 观察指标：后续应看 ELSFP/CPX/NPO 是否给出现场替换流程、监控接口、热插拔限制、清洁/检测工具、failure mode 和客户验证，而不是只看带宽密度。

### 2. Scale-up optical/electrical interconnect 需要开放抽象

- 背景：AI pod 内的 accelerator-to-accelerator communication 正在从封闭背板和专有互连走向 UALink、SAI/SONiC、CMIS/EEI 等多层抽象。
- 本周证据：UALink OCP panel 讨论 ecosystem、interoperability 与 supply chain diversity；Marvell OCP 议程包含 UALink-SAI、SAI telemetry、memory-semantic fabric；OIF CEI-448G framework 提到与 UALink、UEC、OCP、IEEE 802.3 等 SDO 协作。https://ualinkconsortium.org/event/ocp-global-summit-2026/  https://www.marvell.com/company/events/ocp-global-summit-2026.html  https://www.oiforum.com/wp-content/uploads/OIF-FD-CEI-448G-01.0.pdf
- 观察指标：标准是否能覆盖 link bring-up、training、telemetry、fault isolation、congestion management、security 和 management-plane API。

### 3. AI factory 评估必须把 interconnect 放进 power/cooling/operations

- 背景：800G/1.6T 网络、CPO/NPO、OCS 和 high-radix fabrics 的价值只有在 workload、rack power、cooling、facility grid 和 operations 约束下才完整。
- 本周证据：NVIDIA OCP 页面列出 MGX ecosystem、800 VDC、FBOSS、hardware fault management、Spectrum-X 与 Vera Rubin NVL72；OCP track 覆盖 cluster telemetry、liquid cooling、validation 和 manufacturing testing。https://www.nvidia.com/en-us/events/ocp-summit/  https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/
- 观察指标：报告和产品发布应说明 workload、topology、power envelope、cooling interface、fault management 与 token/economic metrics；缺少这些上下文的互连效率声明需要保守处理。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| OCP | 发布/更新 2026 Global Summit 22 个 track，覆盖 AI Clusters、Photonics、Networking、Short Reach Optical Interconnect 等 | open AI infrastructure、系统验证 | https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/ |
| OIF | OCP co-located workshop 聚焦 224G/448G、CPO/NPO、ELS、CMIS、coherent optics | 标准互操作、electrical/optical co-design | https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/ |
| UALink | OCP panel 讨论 UALink ecosystem 和 AI compute pod 内互连 | scale-up accelerator interconnect | https://ualinkconsortium.org/event/ocp-global-summit-2026/ |
| NVIDIA | OCP 页面聚焦 AI Factories at Scale、MGX、FBOSS、800 VDC、Spectrum-X、Vera Rubin NVL72 | rack-scale AI factory | https://www.nvidia.com/en-us/events/ocp-summit/ |
| AMD | 宣布 Lisa Su OCP opening keynote，主题为 open full-stack infrastructure for agentic AI | open XPU ecosystem、gigawatt-scale deployment | https://newsroom.amd.com/news/media-alert-ceo-lisa-su-keynote-2026-ocp/ |
| Marvell | Investor Day 2026；OCP 议程覆盖 connectivity-bound AI、SAI telemetry、UALink-SAI | custom silicon、switch、AI interconnect platform | https://www.marvell.com/company/events/investor-day-2026.html |
| Lumentum | OCP speaker lineup 覆盖 external laser、VCSEL、OCS；ECOC 展示 ELSFP/D2D | CPO/NPO serviceability、scale-up/scale-out optics | https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Speaker-Lineup-at-2026-OCP-Global-Summit/default.aspx |
| Corning / GF / Marvell | Polarcor、SiGe capacity、fiber/connectivity 等供应链线索延续 | laser optics、foundry、fiber backbone | https://www.corning.com/cn/zh/products/advanced-optics/news-events/news-releases/2026/09/Corning-Announces-Polarcor-Capacity-Expansion-to-Support-Multi-Year-Supply-Agreement.html |

## 趋势观察

- **OCP 正在接管 ECOC 后的系统级讨论。** ECOC 证明 optical/electrical demo 与互操作，OCP 更接近 rack、power、cooling、network OS、fault management 和 open BOM。https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/
- **CPO/NPO 的胜负手是 serviceability。** External laser、pluggable NPO、detachable fiber attach、CMIS/telemetry、cleaning workflow 会决定是否能进入客户机房。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/
- **Open scale-up interconnect 需要多层标准协同。** UALink 解决 accelerator pod 互连抽象，OIF 解决高速 electrical/optical interface，OCP/SONiC/SAI 解决系统管理和部署生态。https://ualinkconsortium.org/event/ocp-global-summit-2026/
- **AI optics 供应链正在上移。** SiGe、Polarcor、fiber density、VCSEL arrays、ELSFP、OCS、CPX optical engine 都会影响实际 deployment cadence。https://gf.gcs-web.com/news-releases/news-release-details/globalfoundries-and-marvell-expand-collaboration-next-generation
- **仍无足够独立评测支撑“大规模替代”结论。** 本周公开证据主要是官方议程、官方 demo、标准材料和论文；需要继续区分 demo/roadmap/产品可用性/生产部署。https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | AI clusters、photonics、networking、validation、power/cooling | https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/ |
| AMD opening keynote @ OCP | 2026-10-12 | open full-stack infrastructure for agentic AI | https://newsroom.amd.com/news/media-alert-ceo-lisa-su-keynote-2026-ocp/ |
| NVIDIA at OCP | 2026-10-12 至 2026-10-15 | AI Factories at Scale、MGX、FBOSS、800 VDC、Spectrum-X | https://www.nvidia.com/en-us/events/ocp-summit/ |
| OIF Workshop @ OCP | 2026-10-13 | 224G/448G、CPO/NPO、ELS、CMIS、coherent optics | https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/ |
| UALink panel @ OCP | 2026-10-14 | UALink ecosystem、scale-up AI pods | https://ualinkconsortium.org/event/ocp-global-summit-2026/ |
| SC26 | 2026-11-15 至 2026-11-20 | HPC/AI networking、large-scale systems | https://sc26.supercomputing.org/attendees/ |

## 📱 分享卡片

- W41 主线：OCP 前夜，AI interconnect 的关键词从“更高速率”变成“开放标准 + 可维护光学 + rack-scale operations”。https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/
- CPO/NPO 要过的不是 demo 关，而是 external laser、CMIS、telemetry、清洁维护、液冷、故障定位和现场替换这组工程关。https://www.opencompute.org/events/ocp-summit/2026-ocp-global-summit/co-located-events/
- UALink、OIF CEI/EEI、SAI/SONiC 与 OCP open infrastructure 正在形成 scale-up AI pod 的多层标准栈。https://ualinkconsortium.org/event/ocp-global-summit-2026/
- Lumentum 的 OCP 议程把 external laser、VCSEL 和 OCS 放在一起，提示 AI optics 不只服务机柜内 scale-up，也会影响 scale-out/scale-across。https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Announces-Speaker-Lineup-at-2026-OCP-Global-Summit/default.aspx
- 保守判断：本周仍以官方议程和 demo 证据为主，暂无独立评测证明 CPO/NPO 已在客户 GPU pod 中大规模替代 pluggable optics。https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx

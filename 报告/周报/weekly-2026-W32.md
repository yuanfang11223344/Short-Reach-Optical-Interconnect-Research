# 芯片互连与AI基础设施 每周综述 2026-W32

> 生成时间：2026-08-03 10:00 CST  
> 覆盖范围：2026-08-03 至 2026-08-03；周一首日版，已先生成并纳入当日 `2026-08-03.md` 的 `🔥` 与 `⭐` 条目。  
> 说明：本周仍在进行中，周报用于建立 W32 观察框架；后续日报会继续补充和刷新本周判断。

## 本周最重要的 5-8 件事

### 🔥 OIF ECOC 2026 互操作预告把 448G/224G 推到台前

- 要点：OIF 宣布将在 ECOC 2026 展示 optical systems、448G 与 224G CEI、common management 等互操作能力。来源：https://www.oiforum.com/oif-brings-industry-wide-interoperability-to-life-at-ecoc-2026-accelerating-scalable-efficient-networks-for-the-ai-era/
- 为什么重要：448G 的瓶颈不是 headline speed，而是 channel、package、connector、module management 和 compliance test 的共同成熟。对 2026 下半年供应链，ECOC 会成为观察 448G/224G 从规范走向工程验证的重要窗口。

### 🔥 IEEE P802.3dj 继续锚定 200G/lane 与 1.6TbE 量产节奏

- 要点：P802.3dj 任务组继续推进 200 Gb/s electrical/lane、800GbE 与 1.6TbE PHY/PMD 相关工作。来源：https://www.ieee802.org/3/dj/
- 为什么重要：交换 ASIC、optical DSP、retimer、AEC/DAC、连接器和测试仪表都需要围绕 P802.3dj 的节奏进行资源投入；标准成熟度会直接影响 1.6T optics 与 AI cluster network 的部署窗口。

### 🔥 CPO/COI 的关键问题从器件指标转向系统可运维性

- 要点：OIF EEI/COI 文档、3D optoelectronics/CPO 论文和产业评论共同强调 thermal-aware co-design、serviceability、external laser、standardization 与 robustness。来源：https://www.oiforum.com/documents/informative-documents/ ; https://arxiv.org/abs/2603.21313
- 为什么重要：CPO 若进入 AI data center，评价指标不能只看 pJ/bit 和 bandwidth density，还要看现场替换、良率、热耦合、管理接口和库存模型。

### ⭐ AI Ethernet 的竞争点正在向软件和系统 co-design 扩展

- 要点：NVIDIA Spectrum-X 继续作为 accelerated Ethernet 样板，UEC 则从开放规范角度覆盖 transport、congestion、telemetry 和软件栈。来源：https://www.nvidia.com/en-us/networking/ethernet/spectrum-x/ ; https://ultraethernet.org/
- 为什么重要：训练集群的有效吞吐取决于 collective pattern、tail latency、congestion recovery 和 telemetry feedback。未来比较 Ethernet fabric 时，单端口速率会越来越不够。

### ⭐ Scale-up fabric 进入开放方案与厂商方案并行阶段

- 要点：NVLink 仍是 rack-scale scale-up 的性能参照，UALink 提供开放 accelerator-to-accelerator 互连路径，Marvell 则用 scale-up/scale-out/scale-across 框架描述 AI infrastructure 分层。来源：https://www.nvidia.com/en-us/data-center/nvlink/ ; https://www.ualinkconsortium.org/ ; https://www.marvell.com/solutions/data-center/scaling-ai-infrastructure.html
- 为什么重要：Scale-up 的胜负不只在物理层，endpoint、switch ASIC、collective library、memory semantics 和软件生态会共同决定部署难度。

### ⭐ Cooling capacity 成为 AI infrastructure 的实际交付约束

- 要点：Vertiv 扩大 AI-ready cooling 制造能力，CoreSite 2026 outlook 将 power/cooling 作为 data center 运营重点。来源：https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-expands-global-manufacturing-capacity-for-ai-ready-data-center-cooling-solutions/ ; https://www.coresite.com/blog/data-center-outlook-2026-power-and-cooling-challenges-and-solutions-are-top-of-mind
- 为什么重要：AI 机柜上线不只受 GPU、switch 和 optics 供货影响，也受 chiller、CDU、testing lab、grid connection 和 on-site power 影响。

## 本周关键技术进展 3 篇深读

### 1. 448G/224G CEI：从规范推进到互操作工程

**背景：** 224G/200G-lane 是 1.6T Ethernet 和 AI backend network 的现实基线，448G 则是下一代 switch radix 与 power budget 的候选路径。  
**本周信号：** OIF ECOC 2026 预告把 448G、224G CEI、optical systems 和 management 放进互操作演示；OIF current work 继续列出 CEI-224G-Linear 等项目。来源：https://www.oiforum.com/oif-brings-industry-wide-interoperability-to-life-at-ecoc-2026-accelerating-scalable-efficient-networks-for-the-ai-era/ ; https://www.oiforum.com/technical-work/current-work/  
**产业影响：** 448G 的第一批真实壁垒会落在 channel model、advanced materials、connector、package、equalization、thermal 和 BERT/compliance 工具。模块厂若只跟 optics，不跟 electrical channel 和 management，风险会被后移到系统验证阶段。

### 2. CPO/COI：AI scale-up optics 的系统边界问题

**背景：** CPO 的价值主张是把 optics 靠近 switch ASIC 或 accelerator，降低 electrical reach 和 energy per bit，但它同时改变了可维护性、外置光源、热管理和供应链责任边界。  
**本周信号：** OIF EEI/COI 文档给出节能 photonic interconnect 的标准化方向；arXiv:2603.21313 明确把 CPO 视为架构承诺，而非器件优化。来源：https://www.oiforum.com/documents/informative-documents/ ; https://arxiv.org/abs/2603.21313  
**产业影响：** 未来一段时间 CPO、NPO、LPO 和 retimed pluggable 会并行。领先厂商需要同时证明 optical engine、ELS、socketability、yield、field service、thermal telemetry 和 network OS 可协同。

### 3. Optical Circuit Switching：AI training network 的调度问题

**背景：** AI training 的 collective communication 呈现重复、可预测、高 bisection bandwidth 的流量特征，传统 packet switch fabric 在功耗、buffer 和拥塞上面临压力。  
**本周信号：** `Scheduling Parallel Optical Circuit Switches for AI Training` 从 parallel OCS 调度角度讨论 AI training 网络；`InfiniteHBD` 则探索在 transceiver 级嵌入 OCS 构建 high-bandwidth domain。来源：https://arxiv.org/abs/2603.07373 ; https://arxiv.org/html/2502.03885v5  
**产业影响：** OCS 的机会在于绕开部分 O-E-O 转换、降低功耗和提供可重构 topology；风险在控制平面复杂度、故障隔离、作业调度耦合和与 Ethernet/NVLink/UALink 分层协同。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| OIF | 预告 ECOC 2026 互操作演示 | 448G/224G CEI、optical systems、module management | https://www.oiforum.com/oif-brings-industry-wide-interoperability-to-life-at-ecoc-2026-accelerating-scalable-efficient-networks-for-the-ai-era/ |
| IEEE 802.3dj | 持续推进 200G/lane、800GbE、1.6TbE | SerDes、PHY/PMD、optics、compliance | https://www.ieee802.org/3/dj/ |
| Ethernet Alliance | OFC 2026 AI-scale Ethernet 互操作与技术复盘 | 1.6T Ethernet ecosystem readiness | https://ethernetalliance.org/blog/2026/05/27/ofc-2026-the-tech-leads-perspective/ |
| NVIDIA | Spectrum-X、NVLink 继续作为 AI fabric 标尺 | Accelerated Ethernet、scale-up fabric、software co-design | https://www.nvidia.com/en-us/networking/ethernet/spectrum-x/ |
| Marvell | 强调 scale-up/scale-out/scale-across AI infrastructure | 224G SerDes、1.6T connectivity、custom silicon | https://www.marvell.com/solutions/data-center/scaling-ai-infrastructure.html |
| Broadcom | Optical DSP 与 AI Ethernet 组合仍是模块和交换系统参考 | DSP/FEC、switch silicon、CPO/pluggable optics | https://www.broadcom.com/products/ethernet-connectivity/optical-dsp |
| Credo | 7 月博客聚焦 PCIe Gen6、observable optical、AI connectivity | AEC/retimer/optical connectivity | https://credosemi.com/blogs-and-insights/ |
| Vertiv | 扩大 AI-ready cooling solutions 制造能力 | Chiller、CDU、testing lab、thermal infrastructure | https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-expands-global-manufacturing-capacity-for-ai-ready-data-center-cooling-solutions/ |
| CoreSite | 2026 outlook 聚焦 power/cooling | Colocation、on-site power、liquid cooling readiness | https://www.coresite.com/blog/data-center-outlook-2026-power-and-cooling-challenges-and-solutions-are-top-of-mind |

## 趋势观察

- **448G 将先表现为“工程生态成熟度竞赛”。** 谁能把 SerDes IP、package substrate、connector、PCB material、optical module、management 和 compliance test 更早打通，谁就更接近 AI network 下一轮平台窗口。
- **CPO 的短期对手不是单一 pluggable，而是运维惯性。** Hyperscaler 需要证明故障替换、外置光源、热漂移、良率和生命周期成本可控，CPO 才能从高端样板扩展到规模部署。
- **AI fabric 正在分层：scale-up、scale-out、scale-across 各自需要不同物理层和软件栈。** NVLink、UALink、UEC Ethernet、CPO、OCS 不一定互斥，更可能在不同层级共存。
- **液冷和供电正成为网络设备间接变量。** 高密度 rack 会影响 front-panel optics、cable bend radius、switch placement、PDU/UPS 布局和维护通道，网络架构团队需要更早参与 facility design。

## 下周关注

| 事件 | 时间 | 关注点 | 链接 |
|---|---|---|---|
| ECOC 2026 准备资料 | 持续跟踪 | OIF 448G/224G CEI、optical systems、management 演示细节 | https://www.ecocexhibition.com/ |
| IEEE P802.3dj 资料更新 | 持续跟踪 | Draft、comment resolution、200G/lane electrical/optical 细节 | https://www.ieee802.org/3/dj/ |
| Ethernet Alliance TEF 2026 | 2026-10-07 至 2026-10-08 | AI Ethernet、400G/lane signaling、fabric architecture | https://ethernetalliance.org/blog/2026/04/22/defining-ethernets-next-chapter-in-the-age-of-ai-tef-2026/ |
| OCP Global Summit 2026 | 2026-10-13 至 2026-10-16 | Open rack、liquid cooling、power shelf、CPO、open networking | https://www.opencompute.org/summit/global-summit |
| Credo/Marvell/Broadcom 官方更新 | 持续跟踪 | AEC/retimer、1.6T optical DSP、CPO switch、224G/448G SerDes | https://credosemi.com/blogs-and-insights/ |

## 分享卡片

- OIF 已把 ECOC 2026 互操作焦点放到 448G/224G CEI、optical systems 和 management。https://www.oiforum.com/oif-brings-industry-wide-interoperability-to-life-at-ecoc-2026-accelerating-scalable-efficient-networks-for-the-ai-era/
- 1.6TbE 的量产节奏仍看 IEEE P802.3dj；200G/lane 牵动 SerDes、optics、connector 和测试生态。https://www.ieee802.org/3/dj/
- CPO 真正难点是系统可维护性，不只是 optical engine bandwidth density。https://arxiv.org/abs/2603.21313
- AI Ethernet 的下一轮竞争在 congestion control、telemetry 和软件协同。https://ultraethernet.org/
- AI data center 的交付瓶颈已经扩展到 chiller、CDU、on-site power 和测试能力。https://www.vertiv.com/en-us/about/news-and-events/corporate-news/2026/vertiv-expands-global-manufacturing-capacity-for-ai-ready-data-center-cooling-solutions/

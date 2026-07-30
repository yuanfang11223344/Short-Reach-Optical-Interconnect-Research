# 芯片互连与AI基础设施 每周综述 2026-W31

> 截至 2026-07-30 的周内补齐版。覆盖 2026-07-27 至 2026-07-30；素材来自本次补齐日报、标准组织页面、厂商官方资料、产业媒体与 arXiv。

## 本周最重要的 5-8 件事

### 🔥 IEEE P802.3dj July 2026 session 资料沉淀
- 要点：July session 页面已经发布 agenda、motions/strawpolls、comment resolution 与 unapproved minutes 入口。[来源](https://www.ieee802.org/3/dj/public/26_07/index.html)
- 为什么重要：这说明 200G/lane/1.6TbE 不再是概念讨论，而进入多 track 细节收敛；SerDes、optics、logic 的边界会在 comment resolution 中具体化。

### 🔥 OIF CEI-448G-VSR/LR 成为 448G 电互连主线
- 要点：OIF Current Work 同时列出 chip-to-module VSR 与 backplane LR 项目。[来源](https://www.oiforum.com/technical-work/current-work/)
- 为什么重要：448G 的架构风险在通道损耗、advanced materials、connector、package 和 DSP power；这会直接影响下一代 switch ASIC 与 optical module/NPO/CPO 分工。

### 🔥 NVIDIA Spectrum-X Ethernet Photonics 继续推动 CPO 平台化
- 要点：Rubin/Vera Rubin 资料把 200G SerDes、CPO 与 AI-optimized fabric 放入同一系统。[来源](https://nvidianews.nvidia.com/news/vera-rubin-full-production-agentic-ai-factory)
- 为什么重要：这意味着 CPO 竞争点从 optical engine 指标转向 switch silicon、external laser、NOS、热设计与现场可维护性。

### ⭐ UALink 2.0 把 In-Network Compute 带入 scale-up fabric
- 要点：Common 2.0 引入 reductions、aggregations、synchronization 和 collectives。[来源](https://ualinkconsortium.org/wp-content/uploads/2026/04/UALink-2.0-Specification-PR_FINAL.pdf)
- 为什么重要：若生态落地，GPU/NIC endpoint、switch ASIC 和 collective library 的职责边界会变化，开放 scale-up 不只是互连线缆标准。

### ⭐ UEC 1.0.2 提供 AI scale-out Ethernet 开放参考
- 要点：UEC 规范覆盖 transport、congestion、telemetry 和 compliance。[来源](https://ultraethernet.org/wp-content/uploads/sites/20/2026/01/UE-Specification-1.0.2-1.pdf)
- 为什么重要：Scale-out 网络需要和 UALink scale-up 分层协同，Ethernet 的可观测性和拥塞控制会影响训练效率。

### ⭐ 液冷与供电约束上升到架构层
- 要点：Schneider、Panasonic 和 arXiv 资料都指向 rack density、CDU/chiller、facility DC/MVDC 的系统设计。[来源](https://blog.se.com/datacenter/2026/07/28/data-center-power-density-planning-liquid-cooled-ai-data-centers-around-grid-and-power-constraints/)
- 为什么重要：AI cluster 的瓶颈不再只在 GPU 和网络，供电转换级数、热回路和机房接入能力会决定可部署规模。

## 本周关键技术进展（3篇深读）

### 448G SerDes 从 framework 走向 IA
- 背景现状：224G PAM4 已进入 1.6T Ethernet 与 scale-up fabric 实现周期，448G 需要重新评估封装、通道、均衡和测试。
- 本周新进展：OIF 当前工作列出 CEI-448G-VSR/LR，framework 文档给出应用空间、技术挑战和 interoperability test 问题。[来源](https://www.oiforum.com/technical-work/current-work/)
- 对产业链影响：对产业链影响是 SerDes IP、connector、PCB材料、package substrate、ATE/BERT 和 compliance 工具同步升级；未来 1-2 年会看到更多 448G test chip、linear/retimed 边界讨论和 channel model 收敛。

### CPO 从光引擎技术变成网络平台技术
- 背景现状：800G/1.6T pluggable 仍是现实主力，但 AI rack 的端口密度和能效把 optics 推向 switch package。
- 本周新进展：NVIDIA Spectrum-X Ethernet Photonics 与 Rubin 资料把 CPO、200G SerDes 和 AI fabric 同步描述，OIF EEI 资料同时讨论 retimed、half-retimed、linear 光接口。[来源](https://www.nvidia.com/en-us/networking/spectrumx/)
- 对产业链影响：供应链不只比 PIC/laser，还要比 ELS、socketability、yield、field service、thermal 和 NOS 遥测；未来 1-2 年 CPO/NPO/linear pluggable 会并行，直到平台可靠性数据足够。

### AI data center 进入 grid-to-chip 设计阶段
- 背景现状：机柜功率密度上升让传统 facility 与服务器分层优化失效，冷却和供电必须在集群设计初期一起建模。
- 本周新进展：arXiv:2606.25095 讨论 facility-level DC/MVDC，Schneider 讨论 2026 rack density 与液冷规划，Panasonic 发布 CDU/chiller 产品。[来源](https://arxiv.org/abs/2606.25095)
- 对产业链影响：影响方向是 power module、busbar、CDU、chiller、监控和网络拓扑共同设计；未来 1-2 年 50-70kW 机柜会常态化，更高密度系统推动 800V/HVDC 与 warm-liquid cooling 验证。

## 厂商动态汇总

| 厂商 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| Broadcom | Taurus 400G/lane optical DSP 作为 3.2T module DSP 参考点 | DSP/FEC/400G-lane optics | https://investors.broadcom.com/news-releases/news-release-details/broadcom-delivers-industrys-first-400glane-optical-dsp-next |
| Marvell | 本周未见新增一手公告，继续跟踪 1.6T/3.2T DSP 与 PAM4/optical DSP 路线 | optical DSP、switch connectivity | https://www.ieee802.org/3/dj/public/26_07/index.html |
| Credo | 本周未见新增一手公告，继续跟踪 retimer、AEC 和 224G 互连生态 | retimer/AEC、AI back-end network | https://www.oiforum.com/oif-validates-critical-interoperability-live-at-ofc-2026-through-multi-vendor-demonstrations-and-expert-panels/ |
| Synopsys | 224G SerDes 与 UALink/UEC 生态文章继续作为 IP 侧参考 | PHY/controller/verification IP | https://www.synopsys.com/articles/224g-serdes-interoperability-ai-hpc.html |
| Cadence | 本周未见新增一手公告，继续跟踪高速 SerDes verification 与 advanced packaging 设计流 | EDA、IP、封装协同 | https://socionextus.com/pressreleases/socionext-to-showcase-advanced-packaging-and-serdes-architecture-at-designcon-2026/ |
| NVIDIA | Rubin/Vera Rubin、Spectrum-X Ethernet Photonics 与热管理讨论持续发酵 | CPO switch、AI rack-scale network | https://nvidianews.nvidia.com/news/vera-rubin-full-production-agentic-ai-factory |
| Intel | 本周未见新增一手公告，继续跟踪硅光子与 Ethernet/UEC 生态 | silicon photonics、scale-out Ethernet | https://ultraethernet.org/wp-content/uploads/sites/20/2026/01/UE-Specification-1.0.2-1.pdf |
| 国内厂商 | 中际旭创年报路线覆盖 3.2T、Coherent Lite、NPO/XPO/OCS；本周未见新增一手量产公告 | 光模块、NPO/XPO、OCS | https://static.cninfo.com.cn/finalpage/2026-03-31/1225056493.PDF |

## 趋势观察

- **448G 的第一性问题是系统损耗预算，不是单个 SerDes headline speed。** OIF CEI-448G-VSR/LR 把 reach、connector 和 advanced materials 写入项目目标，IEEE 802.3dj 也在通过 comment resolution 处理 optics/electrical/logic 接口细节。[来源](https://www.oiforum.com/technical-work/current-work/)
- **CPO 的采用节奏会被“可维护性”决定。** NVIDIA 将 CPO 放入 Spectrum-X/Rubin 平台，OIF EEI 同时覆盖 retimed、half-retimed、linear，多路线并行说明 hyperscaler 仍在权衡 field service、ELS、yield 和功耗。[来源](https://www.nvidia.com/en-us/networking/spectrumx/)
- **AI 基础设施投资正在从芯片采购扩展到电力和热回路。** rack density、liquid cooling、facility DC/MVDC 资料共同说明，网络拓扑和供电散热将一起限制集群规模。[来源](https://blog.se.com/datacenter/2026/07/28/data-center-power-density-planning-liquid-cooled-ai-data-centers-around-grid-and-power-constraints/)

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| Optica Advanced Photonics Congress 资料沉淀 | 2026-07-27 至 2026-07-30 | silicon photonics、PIC、photonic integration paper/postdeadline | https://www.optica.org/events/congress/advanced_photonics_congress/ |
| IEEE P802.3dj July 资料后续更新 | 持续跟踪 | approved minutes、comment resolution、D3.x 进度 | https://www.ieee802.org/3/dj/public/26_07/index.html |
| Ethernet Alliance TEF 2026 | 2026-10-07 至 2026-10-08 | AI Ethernet、400G/lane signaling、fabric architecture | https://ethernetalliance.org/blog/2026/04/22/defining-ethernets-next-chapter-in-the-age-of-ai-tef-2026/ |
| OCP Global Summit 2026 | 2026-10-13 至 2026-10-16 | open rack、liquid cooling、power、networking | https://www.opencompute.org/events/past-events/2026-ocp-china-day |

## 📱 分享卡片

- IEEE 802.3dj July 2026 资料公开，200G/lane 正在进入规范细节收敛。https://www.ieee802.org/3/dj/public/26_07/index.html
- OIF CEI-448G-VSR/LR 让 448G 从 framework 走向具体接口项目。https://www.oiforum.com/technical-work/current-work/
- NVIDIA Spectrum-X Ethernet Photonics 把 CPO 推向 AI 网络平台级验证。https://www.nvidia.com/en-us/networking/spectrumx/
- UALink 2.0 的 In-Network Compute 可能改变 endpoint 和 switch ASIC 边界。https://ualinkconsortium.org/wp-content/uploads/2026/04/UALink-2.0-Specification-PR_FINAL.pdf
- AI data center 的硬约束正在变成 power density、liquid cooling 和 grid-to-chip。https://arxiv.org/abs/2606.25095

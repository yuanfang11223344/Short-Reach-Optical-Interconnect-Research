# 芯片互连与AI基础设施 每周综述 2026-W36

> 生成时间：2026-08-31 10:00（Asia/Shanghai）。周一例行周报；已先生成 `2026-08-31.md`，并纳入其中 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-08-31，后续日报继续作为 W36 周报滚动素材。

## 本周最重要的 5-8 件事

### 🔥 OIF ECOC 2026 将 224G/448G electrical I/O、CMIS、Co-Packaging 与 EEI 拉到同一互操作现场
- 要点：OIF ECOC 2026 页面称 39 家成员公司将展示 Optical Systems、448G/224G CEI、CMIS、Co-Packaging、EEI 等互操作方向。https://www.oiforum.com/meetings-events/oif-ecoc-2026/
- 为什么重要：AI 网络的部署风险不再只是 SerDes eye opening，而是 host、retimer、module、management、connector、thermal 和测试仪表能否协同。ECOC 的价值在于把这些边界放进同一验证场。

### 🔥 Cisco / NVIDIA / Supermicro 把 rack-scale AI factory 变成可订购的企业基础设施组合
- 要点：Cisco 公告称 2026 年 10 月开始提供 Supermicro compute solutions，覆盖 high-density liquid-cooled 与 air-cooled AI servers；FAQ 进一步说明 Cisco Silicon One N9300 用于 front-end fabric，NVIDIA Spectrum-X Ethernet silicon based Cisco N9100 用于 back-end fabric。https://investor.cisco.com/news/news-details/2026/Cisco-Expands-Secure-AI-Factory-with-NVIDIA-for-the-Rack-Scale-Era/default.aspx
- 为什么重要：企业、neocloud 和 sovereign cloud 采购 AI 基础设施时，关注点正从 GPU 服务器扩展到 validated architecture、网络拓扑、安全、observability、渠道支持和运维模型。

### 🔥 Spectrum-X Multiplane 与 UEC/UALink 并行推进，AI fabric 正在形成三层分工
- 要点：NVIDIA Hot Chips 期间强调 Spectrum-X Multiplane、Vera Rubin、NVLink Fusion 与 BlueField-4；UALink 200G 1.0 规格定义 AI pod 内 accelerator 与 switch 的低延迟互连；UEC 9 月将进入 AI Infra Summit 和 Member Summit 节点。https://blogs.nvidia.com/blog/vera-rubin-lpx-spectrum-x-nvlink-fusion/
- 为什么重要：scale-up、scale-out、scale-across 不会由单一协议解决。NVLink/UALink 更靠近 accelerator domain，UEC/Spectrum-X 类 Ethernet 方案服务大规模 scale-out，ZR/ZR+/campus optics 继续扩展 AI campus。

### 🔥 ECOC Market Focus 把 CPO/NPO 的主战场从“光引擎”推进到标准、连接和可服务性
- 要点：ECOC 页面把 co-packaged 与 near-package optics 称为 2026 年主要技术热点之一，并强调 standards、robust technologies、fiber connectivity、manufacturability 和 operational aspects。https://www.ecocexhibition.com/visit/market-focus/market-focus-session-information/
- 为什么重要：CPO/NPO 若要从少数超大客户扩展到更宽生态，关键不只是能效，还包括故障替换、光源冗余、热界面、CMIS/管理面和多厂商 supply chain。

### ⭐ 1.6T optics 生态从模块演示走向 LPO/LRO/CMIS/200G-per-lane 的系统验证
- 要点：Jabil ECOC exhibitor news 展示 1.6T DR8 LRO optical transceiver；Amphenol ECOC 页面把 1.6T OSFP 与 200G-per-lane、OSFP MSA、IEEE 802.3 和 OIF-CMIS compliance 绑定。https://www.ecocexhibition.com/exhibitor-news/
- 为什么重要：1.6T 的难点是 host SerDes、BER、热设计、功耗、switch platform 与管理接口一起达标。LPO/LRO 降功耗的同时，也会把链路裕量和调试压力推回 host/system。

### ⭐ Photonic switching 与 AI Ethernet 论文把“可运行系统带宽”放到中心
- 要点：arXiv:2605.21187 讨论 Spectrum-X multiplane architecture 与硬件加速 load balancing；arXiv:2608.03146 把 foundry-compatible silicon photonics MEMS optical switch 指向 AI/ML clusters 的高带宽低延迟互连。https://arxiv.org/abs/2605.21187
- 为什么重要：未来互连指标会更接近 workload 结果：iteration time、tail latency、故障恢复时间、job goodput、隔离性和容量比例扩展，而不只是端口速率。

## 本周关键技术进展 3 篇深读

### 1. 224G/448G 进入系统互操作阶段，标准组织开始处理“组合复杂度”
- 背景：200G/lane 光模块、224G electrical I/O、1.6T OSFP、LPO/LRO 和 CPO/NPO 在同一代系统中相互耦合。只验证单一芯片或单一模块已不足以判断 AI cluster 可部署性。
- 本周信号：OIF ECOC 2026 把 CEI-448G、CEI-224G、CMIS、Co-Packaging 与 EEI 放到同一互操作演示；OIF current work 中 CEI-224G-Linear 面向 Ethernet、UEC、AI/ML 的低功耗、低复杂度、低延迟场景。https://www.oiforum.com/technical-work/current-work/
- 推演：后续要持续跟踪 224G host SerDes 与 linear optics、retimed linear receive、NPO、CMIS link training 之间的责任划分。哪个环节承担 equalization、retiming、telemetry 和 fault isolation，会决定真实功耗和运维复杂度。

### 2. Rack-scale AI factory 的核心商品正在变成“网络+计算+冷却+运维”的一体包
- 背景：GB200/GB300/Vera Rubin 等 rack-scale 系统把 GPU、CPU、NIC、DPU、NVLink Switch、Ethernet/InfiniBand、power shelf 和 liquid cooling 绑定到同一部署单元。
- 本周信号：Cisco Secure AI Factory with NVIDIA 增加 Supermicro liquid/air-cooled systems；NVIDIA MGX 第三代 rack architecture 统一 compute、networking servers、cooling、power 和 connectors；GB300 NVL72 页面给出 ConnectX-8 SuperNIC 为每 GPU 提供 800 Gb/s network connectivity 的官方参照。https://www.nvidia.com/en-us/data-center/gb300-nvl72/
- 推演：AI 服务器厂商、网络厂商和云服务商的边界会继续变模糊。采购侧需要把 front-end fabric、back-end fabric、storage network、observability、安全和 lifecycle service 一起评估，而不是单独比较 GPU server SKU。

### 3. CPO/NPO 的商业化约束正在从光电器件转向平台工程
- 背景：CPO 可以缩短 electrical channel 并降低前面板功耗压力，但它也把光源、FAU/connector、热设计、repair workflow 和 switch lifecycle 绑定到更复杂的系统里。
- 本周信号：ECOC Market Focus 关注 CPO/NPO 标准与可服务性；JLT CPO/LPO/DSP 功耗比较提供模型边界；Coherent sampling 高导热 SiC substrate 表明热路径和先进材料也被 AI infrastructure 拉进竞争范围。https://opg.optica.org/jlt/abstract.cfm?uri=jlt-44-16-7158
- 推演：CPO/NPO 进入更广生态前，需要更透明的 TCO 模型：switch ASIC host SerDes 是否计入、laser source 如何冗余、故障件如何更换、液冷接口如何标准化、CMIS/telemetry 是否足以支撑大规模运维。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| OIF | ECOC 2026 互操作演示覆盖 448G/224G CEI、CMIS、Co-Packaging、EEI | SerDes、linear optics、CPO/NPO、module management | https://www.oiforum.com/meetings-events/oif-ecoc-2026/ |
| Cisco / NVIDIA / Supermicro | Secure AI Factory 扩展到 rack-scale，2026 年 10 月开始提供 Supermicro compute solutions | enterprise AI factory、liquid cooling、validated networking | https://www.cisco.com/c/en/us/solutions/collateral/artificial-intelligence/cisco-secure-ai-factory-nvidia-rackscale-faq.html |
| NVIDIA | Hot Chips 期间强调 Vera Rubin、Spectrum-X Multiplane、NVLink Fusion、BlueField-4；GB300 NVL72 给出每 GPU 800 Gb/s network connectivity 参照 | scale-up/out AI fabric、rack-scale systems | https://blogs.nvidia.com/blog/vera-rubin-lpx-spectrum-x-nvlink-fusion/ |
| UALink | 200G 1.0 specification 公开，面向最多 1,024 accelerators | open accelerator scale-up interconnect | https://ualinkconsortium.org/specification/ |
| UEC | 将在 AI Infra Summit 2026 参展，并举行 9 月 Member Summit | optimized Ethernet for AI/HPC、implementation collaboration | https://ultraethernet.org/event/uec-at-ai-infra-summit-2026/ |
| Broadcom | Tomahawk 6 继续作为 102.4T switch silicon 与 200G/lane 参照 | AI Ethernet switching、SerDes | https://www.broadcom.com/company/news/product-releases/63146 |
| Coherent | 开始 sampling 300 mm high thermal conductivity SiC substrates | AI semiconductor thermal materials | https://www.coherent.com/ |
| Jabil / Amphenol | ECOC 2026 相关页面展示 1.6T DR8 LRO 与 1.6T OSFP/200G-per-lane 模块能力 | 1.6T optics、LRO/LPO、CMIS/OSFP ecosystem | https://www.amphenol-cs.com/connect/ecoc-2026.html |
| AMD | Helios 继续作为 OCP ORW、UALink、UEC 开放 rackscale design 观察项 | open rackscale AI、MI455X、Vulcano AI NIC | https://www.amd.com/en/products/rackscale-solutions/helios.html |

## 趋势观察

- **AI 互连的分层会按 workload 和故障域重组。** NVLink/UALink 解决 accelerator domain 内的低延迟 scale-up，Spectrum-X/UEC 类 Ethernet 路线承担大规模 scale-out，coherent/ZR 与 campus optics 承担跨楼宇或跨站点 scale-across。https://ualinkconsortium.org/specification/
- **1.6T 模块进入 200G-per-lane 后，host/system 承担的责任变重。** LPO/LRO 降低模块内 DSP 负担，但对 host SerDes、channel、telemetry 和产线测试提出更高要求；互操作测试将比单模块 datasheet 更重要。https://www.oiforum.com/technical-work/current-work/
- **CPO/NPO 的普及取决于运维模型，而不只是能效模型。** 标准、光源冗余、光纤连接、液冷、故障替换和管理接口会决定它能否从 hyperscaler 定制扩展到更宽市场。https://www.ecocexhibition.com/visit/market-focus/market-focus-session-information/
- **Rack-scale AI 的采购语言正在产品化。** Cisco/NVIDIA/Supermicro 的组合说明客户越来越希望购买 validated rack architecture，而不是自行集成 GPU server、switch、NIC、DPU、安全和 observability。https://investor.cisco.com/news/news-details/2026/Cisco-Expands-Secure-AI-Factory-with-NVIDIA-for-the-Rack-Scale-Era/default.aspx
- **论文评价应绑定系统假设。** CPO/LPO/DSP 功耗比较、Spectrum-X multiplane 评估、photonic MEMS switch 都有明确 workload、拓扑、器件和建模边界；报告引用时需要保留这些边界，避免把研究结论外推为全场景指标。https://arxiv.org/abs/2605.21187

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| UEC Member Summit 2026 | 2026-09-14 至 2026-09-16 | UET implementation、congestion control、telemetry、interoperability profile | https://ultraethernet.org/event/ultra-ethernet-consortium-member-summit-2026/ |
| AI Infra Summit 2026 | 2026-09-15 至 2026-09-17 | Data Movement track、UEC/UALink、AI data center physical infrastructure | https://www.ai-infra-summit.com/ |
| ECOC Exhibition 2026 | 2026-09-21 至 2026-09-23 | OIF booth 2126、1.6T/3.2T optics、CPO/NPO、silicon photonics | https://www.ecocexhibition.com/ |
| UALink / OCP Global Summit | 2026-10-12 至 2026-10-17 | open accelerator interconnect 与 OCP rack ecosystem 对齐 | https://ualinkconsortium.org/events/ |
| OCP Global Summit 2026 | 2026-10-13 至 2026-10-16 | rack power/cooling、hardware management、open AI infrastructure | https://www.opencompute.org/summit/global-summit |
| SC26 | 2026-11-15 至 2026-11-20 | HPC/AI networking、large-scale communication libraries、system software | https://sc26.supercomputing.org/ |

## 📱 分享卡片

- 本周主线：OIF ECOC 2026 把 CEI-448G、CEI-224G、CMIS、Co-Packaging、EEI 放进同一互操作现场，AI 网络验证进入系统组合阶段。https://www.oiforum.com/meetings-events/oif-ecoc-2026/
- Cisco / NVIDIA / Supermicro 的 rack-scale Secure AI Factory 给出 2026 年 10 月可订购时间锚点，AI factory 正从集成工程走向渠道产品。https://www.cisco.com/c/en/us/solutions/collateral/artificial-intelligence/cisco-secure-ai-factory-nvidia-rackscale-faq.html
- UALink、UEC、Spectrum-X 和 NVLink Fusion 同时推进，说明 AI fabric 会长期是多协议分层，而不是单一标准胜出。https://blogs.nvidia.com/blog/vera-rubin-lpx-spectrum-x-nvlink-fusion/
- CPO/NPO 的真正门槛是标准、连接、热设计和可服务性；能效只是进入生产讨论的第一张门票。https://www.ecocexhibition.com/visit/market-focus/market-focus-session-information/
- 1.6T optics 的关键词正在变成 200G-per-lane、LRO/LPO、CMIS、OSFP 和 switch platform 互操作。https://www.amphenol-cs.com/connect/ecoc-2026.html

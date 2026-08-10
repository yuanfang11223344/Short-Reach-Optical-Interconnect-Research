# 芯片互连与AI基础设施 每周综述 2026-W33

> 补齐生成时间：2026-08-10 16:30（Asia/Shanghai）。本周目前覆盖 2026-08-10 周一日报，并补充 8 月上旬公开来源；后续本周日报会继续作为周报素材滚动更新。

## 本周最重要的 5-8 件事

### 🔥 OIF 448G 与 224G linear optics 并行推进
- 要点：OIF Current Work 同时列出 CEI-448G-VSR/LR 与 224G linear optical module electrical specifications。[来源](https://www.oiforum.com/technical-work/current-work/)
- 为什么重要：这说明下一代短距互连不是单点速率竞赛，而是 448G electrical reach、224G linear optics、LPO/CPO/NPO 多形态共同竞争。

### 🔥 IEEE 802.3dj July 资料成为 1.6TbE 收敛依据
- 要点：July session 页面保留 motions、comment resolution、unapproved minutes 等资料入口。[来源](https://www.ieee802.org/3/dj/public/26_07/index.html)
- 为什么重要：对 SerDes/optics 工程师来说，下一步要看 D3.x comment 如何影响 reference equalizer、FEC、optical compliance 和 channel model。

### 🔥 NVIDIA Spectrum-XGS 把 AI Ethernet 推向 scale-across
- 要点：官方称 XGS 用于连接分布式数据中心，形成 giga-scale AI super-factory。[来源](https://nvidianews.nvidia.com/news/nvidia-introduces-spectrum-xgs-ethernet-to-connect-distributed-data-centers-into-giga-scale-ai-super-factories)
- 为什么重要：这把网络问题从单机房 scale-out 扩大到跨站点调度、拥塞控制和 job placement，对 fabric telemetry 和软件栈提出更高要求。

### ⭐ UALink 2.0 与 UEC 1.0.2 形成 scale-up/scale-out 开放参考
- 要点：UALink 2.0 引入 In-Network Compute，UEC 1.0.2 覆盖 AI Ethernet transport/congestion/telemetry。[来源](https://ualinkconsortium.org/wp-content/uploads/2026/04/UALink-2.0-Specification-PR_FINAL.pdf)
- 为什么重要：开放互连生态正在补齐协议层，但与 NVIDIA 平台化路线的竞争会持续。

### ⭐ AI data center 的电力和冷却约束继续上移
- 要点：Schneider、CoreSite、TechRadar 等资料都强调 power density、grid interconnect、on-site power、liquid cooling。[来源](https://blog.se.com/datacenter/2026/07/28/data-center-power-density-planning-liquid-cooled-ai-data-centers-around-grid-and-power-constraints/)
- 为什么重要：机柜功率、供电架构和散热回路会直接影响 GPU cluster 拓扑、部署节奏和资本开支。

### ⭐ CPO 短期与 LPO/pluggable 并行，长期看平台集成能力
- 要点：产业分析认为 800G LPO/pluggable 仍是现实主流，CPO 更适合高密度、强平台集成场景。[来源](https://mapyourtech.com/co-packaged-optics-architecture-status-and-the-path-to-1-6t-switches/)
- 为什么重要：CPO 的关键门槛不是带宽演示，而是 ELS、socketability、热、良率、field service 和系统遥测。

## 本周关键技术进展（3篇深读）

### 448G/224G linear optical 的分层竞争
- 背景现状：224G PAM4 已进入规模部署与 1.6T 互连周期，448G 需要重新平衡通道损耗、封装、FEC 和 equalization。
- 本周新进展：OIF 同时推进 CEI-448G-VSR/LR 和 224G full linear optical electrical specifications。[来源](https://www.oiforum.com/technical-work/current-work/)
- 对产业链影响与推演：SerDes IP、connector、package substrate、PCB 材料、ATE/BERT 和 compliance 工具都会被拉入升级；未来 1-2 年 448G test chip 与 224G linear pluggable/NPO 的边界会更清楚。

### AI Ethernet 从 scale-out 走向 scale-across
- 背景现状：传统 data center fabric 主要服务单站点训练/推理，跨站点通常受 latency、拥塞和调度限制。
- 本周新进展：NVIDIA Spectrum-XGS 官方定位是把分布式数据中心连接成 unified AI super-factory。[来源](https://nvidianews.nvidia.com/news/nvidia-introduces-spectrum-xgs-ethernet-to-connect-distributed-data-centers-into-giga-scale-ai-super-factories)
- 对产业链影响与推演：这会让网络软件、telemetry、job scheduler、storage locality 与 WAN optical transport 一起进入 AI infrastructure 设计；未来 1-2 年 hyperscaler 会更重视跨站点 fabric SLA。

### Power/cooling 成为 AI cluster 架构输入
- 背景现状：GPU 节点和网络升级推动 rack density 超过传统风冷机房能力。
- 本周新进展：Schneider 指出平均 rack density 和 50-70kW AI rack 准备度问题；CoreSite 与 TechRadar 强调 on-site power、microgrid、liquid cooling 和 permitting。[来源](https://blog.se.com/datacenter/2026/07/28/data-center-power-density-planning-liquid-cooled-ai-data-centers-around-grid-and-power-constraints/)
- 对产业链影响与推演：供电、热、网络拓扑会更早合并评审；未来 1-2 年 CDU/chiller、HVDC、behind-the-meter power 与 warm-liquid cooling 会更常出现在 AI factory reference design 中。

## 厂商动态汇总

| 厂商 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| Broadcom | Taurus 400G/lane optical DSP 仍作为 3.2T module DSP 路线参考 | 400G/lane DSP、FEC、optical module | https://investors.broadcom.com/news-releases/news-release-details/broadcom-delivers-industrys-first-400glane-optical-dsp-next |
| Marvell | 本次未见新增一手公告，继续跟踪 1.6T/3.2T PAM4/optical DSP 与 switching connectivity | optical DSP、SerDes | https://www.ieee802.org/3/dj/public/26_07/index.html |
| Credo | 本次未见新增一手公告，继续跟踪 retimer/AEC 与 224G back-end network | retimer、AEC、AI fabric | https://ethernetalliance.org/blog/2026/07/21/keeping-ethernet-moving-forward-q2-2026-highlights/ |
| Synopsys | 224G SerDes 与 UALink/UEC 生态资料继续作为 IP enablement 参考 | SerDes IP、verification、controller | https://www.synopsys.com/articles/224g-serdes-interoperability-ai-hpc.html |
| Cadence | AI factory IP whitepaper 把 CEI-448G、CPO、UEC、UALink、OCP platform 放入系统协同问题 | EDA/IP、系统设计 | https://www.cadence.com/content/dam/cadence-www/global/en_US/documents/tools/silicon-solutions/building-ai-factories-with-ip-solutions-wp.pdf.html |
| NVIDIA | Spectrum-XGS/Spectrum-X 推进 scale-across 与 AI Ethernet 平台化 | AI Ethernet、distributed AI factory | https://nvidianews.nvidia.com/news/nvidia-introduces-spectrum-xgs-ethernet-to-connect-distributed-data-centers-into-giga-scale-ai-super-factories |
| Intel | 本次未见新增一手公告，继续跟踪 silicon photonics 与 UEC/open Ethernet 生态 | silicon photonics、Ethernet | https://ultraethernet.org/wp-content/uploads/sites/20/2026/01/UE-Specification-1.0.2-1.pdf |
| 国内厂商 | 中际旭创公开年报路线覆盖 3.2T、Coherent Lite、NPO/XPO/OCS；本次未见新增一手量产公告 | 光模块、NPO/XPO、OCS | https://static.cninfo.com.cn/finalpage/2026-03-31/1225056493.PDF |

## 趋势观察

- **短距互连进入“电接口与光接口共同优化”阶段。** OIF 把 448G VSR/LR 与 224G linear optical 共同推进，说明 CPO/NPO/LPO 的真实竞争点会落在 channel、power、testability 和 operations。[来源](https://www.oiforum.com/technical-work/current-work/)
- **AI Ethernet 正从单数据中心 fabric 走向跨数据中心系统。** NVIDIA Spectrum-XGS 将 scale-across 放到台前，UEC 则提供开放 scale-out 参考，后续差异会体现在拥塞控制、遥测和软件栈。[来源](https://nvidianews.nvidia.com/news/nvidia-introduces-spectrum-xgs-ethernet-to-connect-distributed-data-centers-into-giga-scale-ai-super-factories)
- **液冷和电力已经是芯片互连架构的外部约束。** 50-70kW 乃至更高 rack density 让网络带宽、GPU 放置、线缆/光模块功耗和机房电力成为同一个设计问题。[来源](https://blog.se.com/datacenter/2026/07/28/data-center-power-density-planning-liquid-cooled-ai-data-centers-around-grid-and-power-constraints/)

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| IEEE P802.3dj 后续资料更新 | 持续跟踪 | approved minutes、D3.x comments、1.6TbE timeline | https://www.ieee802.org/3/dj/public/26_07/index.html |
| Ethernet Alliance TEF 2026 | 2026-10-07 至 2026-10-08 | AI Ethernet、UEC、400G/lane signaling | https://ethernetalliance.org/blog/2026/04/22/defining-ethernets-next-chapter-in-the-age-of-ai-tef-2026/ |
| OCP Global Summit 2026 | 2026-10-13 至 2026-10-16 | open rack、liquid cooling、power、optical/networking | https://www.opencompute.org/events/past-events/2026-ocp-global-summit |
| OIF 448G/224G Linear 项目更新 | 持续跟踪 | VSR/LR IA、linear optics electrical specification | https://www.oiforum.com/technical-work/current-work/ |

## 📱 分享卡片

- OIF 正同时推进 448G VSR/LR 和 224G linear optics，短距互连进入电光协同阶段。https://www.oiforum.com/technical-work/current-work/
- NVIDIA Spectrum-XGS 把 AI Ethernet 从 scale-out 推向跨数据中心 scale-across。https://nvidianews.nvidia.com/news/nvidia-introduces-spectrum-xgs-ethernet-to-connect-distributed-data-centers-into-giga-scale-ai-super-factories
- UALink 2.0 的 In-Network Compute 让 switch ASIC 可能承担更多 collective 工作。https://ualinkconsortium.org/wp-content/uploads/2026/04/UALink-2.0-Specification-PR_FINAL.pdf
- 液冷和电力接入已经决定 AI rack 能否真正部署，不只是设施配套。https://blog.se.com/datacenter/2026/07/28/data-center-power-density-planning-liquid-cooled-ai-data-centers-around-grid-and-power-constraints/
- CPO 短期与 LPO/pluggable 并行，长期拼系统可维护性和平台集成。https://mapyourtech.com/co-packaged-optics-architecture-status-and-the-path-to-1-6t-switches/

# 芯片互连与AI基础设施周报｜2026-W46

> 覆盖 2026-11-09—2026-11-15｜Asia/Shanghai｜补齐于 2026-11-10。素材先取本周已生成的 11-09 日报中 `🔥`、`⭐` 条目，并以公司公告、开放社区资料、会议官网和 arXiv 原文复核补充。下列“计划”“演示”“论文实验”和“已上线”均按原始证据分别表述。

## 本周最重要的 6 件事

1. 🔥 **400G/lane 的设计空间正在变成调制、均衡与实现带宽的共同取舍。** `arXiv:2609.24570` 对 PAM4/PAM6/PAM8/MLSE 的结论来自受限带宽信道数值评估，提示速率路线不能脱离 DSP、封装和真实通道来比较。[原文](https://arxiv.org/abs/2609.24570)
2. 🔥 **TFLN 电光频梳给出高密度 WDM 的实测案例。** `arXiv:2610.34821` 报告 46 wavelength、98.84km 已部署光纤上的 16.56Tb/s coherent transmission；这属于论文实验，不能直接推作短距模块或 CPO 量产证据。[原文](https://arxiv.org/abs/2610.34821)
3. 🔥 **RADICAL 把可重构光连接接入了小规模 GPU testbed。** `arXiv:2610.31941` 在四台 GPU server、SFP28 环境下演示 direct-connect fabric；其 25Gb/s 路径恢复、损耗和串扰等结果限于论文原型条件。[原文](https://arxiv.org/abs/2610.31941)
4. ⭐ **Cisco 与 NVIDIA 的 USFP 计划把 400Gb/s-per-lane 推到可插拔生态讨论。** 两家公司称其目标是 12.8Tb/s capacity，并与 TE Connectivity、Amphenol 推动多源硬件生态；这是公开计划与目标规格，非已普遍部署的产品。[Cisco 公告](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/nvidia-and-cisco-new-pluggable-optics-to-scale-ai-factories.html)
5. ⭐ **AI 连接产业链出现“电—光”协同整合信号。** Marvell 与 Lumentum 于 11 月 2 日宣布拟合并，意图组合 electrical/optical interconnect、switching、laser、transceiver 与 OCS 能力；交易仍受完成条件约束，不能写成已完成整合或客户交付。[联合公告](https://investor.lumentum.com/financial-news-releases/news-details/2026/Marvell-and-Lumentum-to-Combine-Creating-a-Category-Leader-in-AI-Connectivity/default.aspx)
6. 📌 **SC26 进入网络与系统证据密集期。** 官方日程为 11 月 15—20 日，SCinet 的 live operations 为 11 月 14—20 日；本周应关注实机演示、网络架构和论文发布，而不把会前材料当作结果。[SC26 日程](https://sc26.supercomputing.org/all-dates-deadlines/)｜[SCinet](https://sc26.supercomputing.org/scinet/)

## 本周关键技术进展 3 篇深读

### 1. 400G SerDes：调制阶数不是单变量竞赛

`arXiv:2609.24570` 的价值在于将 PAM4、PAM6、PAM8 与 MLSE 放进不同 bandwidth constraint 下比较。论文所述较优解随约束改变而变化，说明 lane-rate 决策要同时评价通道频响、FEC/均衡复杂度、功耗和可制造性。这里的效果是作者数值评估下的 KP4-FEC 门限可达性，不是某种方案已在量产 switch/NIC 的统一胜出。[原文](https://arxiv.org/abs/2609.24570)

### 2. TFLN 频梳：把多波长发射集成度与长距稳定性放到同一实验

`arXiv:2610.34821` 的实验把 50GHz 片上电光频梳用于跨两个数据中心的 98.84km 光纤传输，并报告 46 wavelength、16.56Tb/s coherent transmission。它对 AI 基础设施的启示是可扩展 WDM 光源值得持续跟踪；但文中不是机架内 pluggable/CPO 的可靠性、热设计或成本报告，因此这些工程指标仍待独立来源补足。[原文](https://arxiv.org/abs/2610.34821)

### 3. RADICAL：光路重构的收益取决于控制面是否匹配流量

`arXiv:2610.31941` 通过 microring-based spatial-and-wavelength selective switch 实现可重构 direct-connect，并演示 Linux networking stack 与 GPU server testbed。与其只看物理重构能力，更关键的是调度粒度、训练 collective 的通信形态、重构开销和故障恢复能否共同闭环；论文证明了原型可行性，不等于大规模 AI fabric 的运维成熟度。[原文](https://arxiv.org/abs/2610.31941)

## 厂商动态汇总

| 厂商/组织 | 本周应跟踪事项 | 证据边界 |
|---|---|---|
| Cisco / NVIDIA | USFP 的 400Gb/s-per-lane、12.8Tb/s 目标与多源生态计划。 | 公告中的设计与计划，非大规模部署证明。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/nvidia-and-cisco-new-pluggable-optics-to-scale-ai-factories.html) |
| Cisco | G302 为 51.2T、200G SerDes 的 ToR 路线图，公告称计划于 2026 年底前出货。 | 目标与计划；应同 G300 已出货表述分开阅读。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/cisco-advances-scalability-and-openness-at-ocp-2026.html) |
| Lumentum / Astera Labs / Corning | 三方在 OCP 展示 1060nm VCSEL PCIe-over-optics rack-level proof-of-concept。 | 演示条件为多条 32Gb/s NRZ 光通道与 error-free PCIe-5 link，不外推为通用生产部署。[来源](https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Astera-Labs-and-Corning-to-Demonstrate-1060-nm-VCSEL-Based-PCIe-over-Optics-for-AI-Rack-Scale-Connectivity-at-the-2026-OCP-Global-Summit/default.aspx) |
| Marvell / Lumentum | 宣布拟合并，提出对 scale-across、scale-out、scale-up、scale-in 的端到端协同目标。 | 拟议交易及管理层预期，等待交易进展与产品路线图证据。[来源](https://investor.lumentum.com/financial-news-releases/news-details/2026/Marvell-and-Lumentum-to-Combine-Creating-a-Category-Leader-in-AI-Connectivity/default.aspx) |
| AMD / Cisco / HUMAIN | 其公告称 AMD Instinct MI355X 与 Cisco Silicon One、800G optics 的 AI 基础设施已上线服务客户。 | 厂商联合公告中的部署声明；未来 250MW 与 1GW 均为计划。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m08/amd-cisco-and-humain-expand-saudi-arabia-ai-infrastructure.html) |

## 趋势观察

- 光学正在从 scale-out 继续逼近 rack/PCIe 和 scale-up 边界，但它必须与 package、switch、控制面和运维共同验证。
- 400G/lane 将比较焦点从“最高线速”转向通道带宽、均衡/FEC、功耗与可插拔生态的组合。
- OCS、direct-connect 与 packet fabric 的价值不在单独的端口数，而在重构时间、流量可预测性、保护路径和调度软件的协同。

## 下周关注

1. 跟踪 SC26 11 月 15—20 日的网络、AI/HPC 系统与 exhibitor forum 是否发布可复核的实机细节。[Program](https://sc26.supercomputing.org/Program/)
2. 关注 USFP 的标准化、机械/热设计及多源器件参与者的后续公开资料，避免将初始公告当成标准定稿。
3. 继续区分 Marvell—Lumentum 的交易进度、财务预期和实际产品协同的各自证据。

## 分享卡片

> **本周主线：AI 互连的“光靠近算力”正在同时推进三件事——更高 lane rate、可重构拓扑和电—光协同供应链。真正的分水岭仍是可复核的系统级功耗、可靠性、控制面和规模化部署证据。**
>
> [400G SerDes 研究](https://arxiv.org/abs/2609.24570)｜[TFLN WDM 实验](https://arxiv.org/abs/2610.34821)｜[RADICAL 原型](https://arxiv.org/abs/2610.31941)｜[SC26](https://sc26.supercomputing.org/Program/)

---
本周已纳入 11-09 日报的 `🔥`、`⭐` 条目及 11-10 复核材料；6 件重点、3 篇深读，11 个去重原始 URL。未将公司计划、交易、会议预告或论文原型写成独立验证的量产/规模化部署。

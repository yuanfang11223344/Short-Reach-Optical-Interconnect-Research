# 芯片互连与AI基础设施 每周综述 2026-W25

> 覆盖周期：2026-06-15 至 2026-06-21。本周本地日报素材来自 2026-06-17 日报，并补充搜索标准组织、OFC/ISSCC/DesignCon 论文线索、CPO/硅光子产业链、国内厂商、UALink/ESUN/UEC、AI data center capex 与供电散热方向。本文重点面向数字芯片/SerDes 设计、短距光互连、AI rack-scale infrastructure。

## 本周最重要的 8 件事

1. 🔥 **224G retimer 开始服务 UALink、ESUN、Ethernet 多协议 scale-up fabric**
   - 要点：Credo 发布 Blue Heron 224G AI scale-up retimer，官方称其面向 UALink、ESUN、Ethernet，目标是恢复 40+dB 224G 链路，让 GPU tray、switch tray、cable backplane 的物理摆放更灵活。
   - 为什么重要：AI rack-scale 互连从“芯片内部 NVLink/专有 fabric”走向开放协议时，最先暴露的是电气 reach 和链路稳定性。224G retimer 成为 UALink/ESUN 能否工程化落地的关键器件之一。
   - 来源：https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx

2. 🔥 **OIF CEI-224G-Linear 与 Compute Optics Interface 把短距光互连推向标准化讨论**
   - 要点：OIF current work 显示 CEI-224G-Linear 项目面向 next-gen Ethernet、UEC、AI/ML，目标支持低功耗、低成本、低延迟 full linear optical modules；OIF 另有 Compute Optics Interface white paper 讨论 AI compute scale-up 的光互连架构选择。
   - 为什么重要：linear optics、LPO、CPO、NPO 的路线争论最终都要落到电接口、链路预算、FEC/retimer 位置和可测试性。OIF 工作项说明 224G linear optics 已经从厂商方案进入标准协商层。
   - 来源：https://www.oiforum.com/technical-work/current-work/
   - 来源：https://www.oiforum.com/wp-content/uploads/OIF-EEI-COI-WP-01.0.pdf

3. 🔥 **Broadcom 与 Marvell 同时强化 1.6T/3.2T 光互连 silicon 栈**
   - 要点：Broadcom 在 OFC 2026 展示 400G/lane optical DSP、400G EML/PD、200G/lane VCSEL/EML/CWL 与 CPO；Marvell 扩展 1.6T optical DSP portfolio，Ara X/Ara T/Petra/Aquila M 从 Q1 2026 起采样。
   - 为什么重要：1.6T 模块进入量产周期时，竞争不只是模块外形，而是 DSP、EML/PD、TIA、MACsec、TRO、gearbox、CPO switch 的系统组合。Broadcom 偏 switch ASIC + optics 垂直整合，Marvell 偏 optical DSP 和模块生态深耕。
   - 来源：https://investors.broadcom.com/news-releases/news-release-details/broadcom-showcases-industry-leading-solutions-scaling-ai
   - 来源：https://investor.marvell.com/news-events/press-releases/detail/1013/marvell-ushers-in-the-1-6t-era-with-expanded-optical-dsp-platform-portfolio-redefining-ai-data-center-end-to-end-connectivity

4. 🔥 **Broadcom Tomahawk 6 - Davisson 102.4Tbps CPO switch 把 CPO 推向 switch ASIC 量产路径**
   - 要点：Broadcom 官方称 Tomahawk 6 - Davisson 是 102.4Tbps Ethernet switch with co-packaged optics，面向 scale-up 与 scale-out AI cluster。
   - 为什么重要：CPO 最现实的第一站不是直接上 GPU/XPU package，而是先在 switch ASIC 侧解决 102.4T/204.8T 时代的电 I/O 和功耗问题。光引擎良率、可维护性、laser 策略和现场更换模型会决定后续扩散速度。
   - 来源：https://investors.broadcom.com/news-releases/news-release-details/broadcom-announces-tomahawkr-6-davisson-industrys-first-1024
   - 来源：https://www.broadcom.com/products/ethernet-connectivity/switching/strataxgs/bcm78910-series

5. 🔥 **NVIDIA GB300 NVL72 与 Vera Rubin Ultra NVL576 显示 scale-up domain 正从单柜走向多柜**
   - 要点：GB300 NVL72 是 fully liquid-cooled rack-scale architecture；NVIDIA 博客称 Vera Rubin Ultra NVL576 通过 two-layer all-to-all NVLink topology，把 8 个 72-GPU rack 组合成 576-GPU NVLink domain，并使用 copper 与 direct optical connections。
   - 为什么重要：这意味着互连工程边界从 board/channel、module、rack 进一步扩展到 multi-rack pod。对 SerDes/optics 来说，direct optical connection 会越来越接近 GPU fabric 核心路径。
   - 来源：https://www.nvidia.com/en-us/data-center/gb300-nvl72/
   - 来源：https://developer.nvidia.com/blog/nvidia-vera-rubin-pod-seven-chips-five-rack-scale-systems-one-ai-supercomputer/

6. ⭐ **ESUN、UALink、UEC 形成开放 AI fabric 的多层竞争与互补**
   - 要点：OCP ESUN 聚焦 Ethernet for Scale-Up Networking；UALink 1.0 定义 AI computing pod 内 accelerator-switch 低延迟高带宽互连；UEC specification v1.0.2 继续推动 AI/HPC 网络语义优化。
   - 为什么重要：开放互连不会只靠一个协议胜出。ESUN 试图把 Ethernet 拉进 scale-up，UALink 更偏 accelerator fabric 和 memory semantics，UEC 偏 scale-out transport 优化；它们共同决定 224G PHY、retimer、switch ASIC 和 NIC/XPU 接口的需求形态。
   - 来源：https://www.opencompute.org/blog/introducing-esun-advancing-ethernet-for-scale-up-ai-infrastructure-at-ocp
   - 来源：https://ualinkconsortium.org/specification/
   - 来源：https://ultraethernet.org/wp-content/uploads/sites/20/2026/01/UE-Specification-1.0.2-1.pdf

7. 🔥 **AI data center capex 正从“现金流扩建”转向“资本市场融资+电力锁定”**
   - 要点：Axios 报道 NVIDIA 启动大规模债券融资，Goldman Sachs 估算 2026 年 hyperscaler investment 可能达 7700 亿美元；IBD 报道 AI/data center 项目融资和债务规模继续扩大；TechRadar 与 BVP 分别强调 800VDC/HVDC 与 190GW hyperscale announced capacity。
   - 为什么重要：这说明 AI infrastructure 已成为资本、电力、土地、冷却、网络的综合工程。对光互连产业链，capex 强度会拉动 800G/1.6T 光模块、AEC、CPO、液冷与供电设备，但项目延期和电网瓶颈会带来波动。
   - 来源：https://www.axios.com/2026/06/16/ai-nvidia-bonds-debt
   - 来源：https://www.investors.com/news/technology/ai-data-centers-suppliers-nvidia-debt/
   - 来源：https://www.techradar.com/pro/why-800vdc-is-the-emergent-electrical-backbone-of-next-generation-data-centers
   - 来源：https://www.bvp.com/atlas/roadmap-the-ai-data-center-stack

8. ⭐ **中国光模块与硅光子产业链仍是 800G/1.6T 周期的关键变量**
   - 要点：TrendForce 预计 2026 年 AI optical transceiver market 达 260 亿美元，并提到台湾供应链在 EML laser chips、passive optical components、module packaging/testing、silicon photonics 与 LPO 上推进；LightCounting 中国 optics 报告关注中国光组件和模块市场的历史与预测；证券时报等国内报道持续跟踪中际旭创、新易盛、光迅、澜起等厂商。
   - 为什么重要：800G/1.6T 的出货不只看美国 hyperscaler capex，也受中国模块厂产能、良率、封装、硅光渗透率和出口限制影响。国内厂商在模块、内存接口、PCIe/CXL retimer/AEC 上的进展值得持续跟踪。
   - 来源：https://www.trendforce.com/presscenter/news/20260420-13017.html
   - 来源：https://www.lightcounting.com/report/january-2026-vendors-markets-for-optics-in-china-383
   - 来源：https://www.stcn.com/article/detail/3626796.html
   - 来源：https://www.montage-tech.com/cn/Press_Releases

## 本周关键技术进展（3篇深读）

### 1. 224G/448G SerDes 与 retimer：开放 scale-up fabric 的底座

- 背景现状：AI super-node 正从单机、单柜扩展到多 tray、多柜。NVLink 仍是 NVIDIA 生态的强绑定优势，但 UALink、ESUN、UEC 正在试图把开放协议带进 scale-up 和 scale-out。无论协议怎么定义，最终都需要 224G PAM4 lane、低抖动时钟、强均衡、FEC/retimer 策略和可测试通道模型。
- 本周新进展：Credo Blue Heron 把 224G retimer 明确绑定到 UALink、ESUN、Ethernet；Synopsys 224G PHY IP 页面强调支持 UALink 200G 与 DesignCon 2026 互操作演示；Cadence 224G-LR PHY 强调 LR/MR/VSR 覆盖；Socionext 在 DesignCon 2026 展示 224G/448G SerDes realistic package design analysis。
- 对产业链的影响：retimer 将从 PCIe/CXL server board 器件扩展为 AI rack-scale fabric 的基础器件；SerDes IP 厂商、封装/板级 SI、测试仪器、connector/cable 厂商都会被拉入同一条验证链。
- 未来 1-2 年推演：224G 会先成为 1.6T Ethernet、UALink/ESUN、AEC/retimer 的主战场；448G 会更多停留在 package/channel/测试方法探索阶段，短期更可能以 DesignCon/OFC/ISSCC 论文和 demo 形态出现，而不是大规模商用。
- 来源：https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx
- 来源：https://www.synopsys.com/designware-ip/interface-ip/ethernet/224g-ethernet-phy-ip.html
- 来源：https://www.cadence.com/en_US/home/tools/silicon-solutions/design-ip/high-speed-ethernet/224g-lr-ser-des-phy.html
- 来源：https://socionextus.com/pressreleases/socionext-to-showcase-advanced-packaging-and-serdes-architecture-at-designcon-2026/

### 2. CPO、NPO 与 silicon photonics：从“器件性能”转向“可制造生态”

- 背景现状：CPO 的技术诱因很清楚：ASIC 带宽持续增长，但可插拔模块到 switch ASIC 的电走线越来越吃功耗和 SI margin。然而 CPO 的量产难点不只是光引擎性能，还包括 ELS、fiber attach、thermal keep-out、现场维护、良率分摊和供应链标准化。
- 本周新进展：Broadcom Tomahawk 6 - Davisson 已以 CPO Ethernet switch 形态宣布出货；APC 在 OFC 2026 组织 silicon photonics and CPO standardized ecosystem 讨论；Siemens EDA 文章强调 2026 年 CPO 的关键趋势，包括封装、热、EDA 与系统验证；PIC Magazine 讨论 silicon photonics 与 InP 供应链的关系，提醒 SiPh 并不消灭 InP，而是改变 InP 的需求形态。
- 对产业链的影响：CPO 会把传统光模块供应链重新拆分：模块厂、PIC foundry、InP laser/PD、advanced packaging、EDA、电源/热设计和系统厂要更早协同。封装和测试的价值占比上升，单纯组装能力的差异化会下降。
- 未来 1-2 年推演：CPO 先在 switch 侧放量，NPO/on-board optics 作为工程折中路线继续存在；GPU/XPU 侧 CPO 更依赖平台级架构成熟。硅光子供应链会继续向 foundry 化、标准化和外部光源生态演进。
- 来源：https://investors.broadcom.com/news-releases/news-release-details/broadcom-announces-tomahawkr-6-davisson-industrys-first-1024
- 来源：https://www.ofcconference.org/program/special-events/silicon-photonics-and-co-packaged-optics-standardized-ecosystem/
- 来源：https://blogs.sw.siemens.com/semiconductor-packaging/2026/02/05/five-key-trends-of-co-packaged-optics-cpo-in-2026/
- 来源：https://picmagazine.net/article/124176/Shifting_supply_chains_in_the_era_of_photonics

### 3. AI data center 基础设施：供电、冷却、连接和资本成为同一张约束图

- 背景现状：AI 集群规模增长带来三类耦合问题：第一，GPU/XPU 数量上升导致 scale-up/scale-out fabric 复杂度上升；第二，rack power density 上升推动液冷和 HVDC；第三，数据中心建设受到电网、土地、水资源和社区审批限制。
- 本周新进展：Tom's Hardware 报道 2026 年美国多个数据中心项目被阻或延迟，原因涉及电价、水耗和噪声；TechRadar 讨论 800VDC 作为下一代数据中心供电骨干；BVP 统计 2026 年初全球 hyperscale announced capacity 约 190GW；Axios 与 IBD 报道 AI infrastructure 债务融资和 capex 继续抬升。
- 对产业链的影响：互连工程师需要把“链路功耗”放进 rack-level power budget，而不是只优化单 lane pJ/bit。液冷 CDU、busbar、HVDC、电源模块、光模块、AEC 和 switch ASIC 的路线选择将互相影响。
- 未来 1-2 年推演：高功率 rack 会推动 800VDC/HVDC、液冷标准化、整柜交付和现场施工能力升级；项目延期会使光模块需求节奏更不均匀，但不会改变带宽和能效升级的大方向。
- 来源：https://www.tomshardware.com/tech-industry/artificial-intelligence/more-than-75-data-center-build-outs-worth-usd130-billion-have-been-successfully-blocked-in-the-first-four-months-of-2026-bipartisan-opposition-mounts-nationwide-over-fears-of-soaring-power-and-water-costs
- 来源：https://www.techradar.com/pro/why-800vdc-is-the-emergent-electrical-backbone-of-next-generation-data-centers
- 来源：https://www.bvp.com/atlas/roadmap-the-ai-data-center-stack
- 来源：https://www.axios.com/2026/06/16/ai-nvidia-bonds-debt

## 厂商动态汇总

| 厂商 | 本周/近期动作 | 影响方向 | 链接 |
|---|---|---|---|
| Broadcom | OFC 2026 展示 400G/lane optical DSP、400G EML/PD、CPO；Tomahawk 6 - Davisson 102.4T CPO switch 已宣布出货 | switch ASIC + optics 垂直整合；CPO 先在 switch 侧落地 | https://investors.broadcom.com/news-releases/news-release-details/broadcom-showcases-industry-leading-solutions-scaling-ai |
| Marvell | 扩展 1.6T optical DSP portfolio，Ara X/Ara T/Petra/Aquila M 从 Q1 2026 起采样 | 1.6T DSP、TRO、gearbox、coherent-lite optical DSP | https://investor.marvell.com/news-events/press-releases/detail/1013/marvell-ushers-in-the-1-6t-era-with-expanded-optical-dsp-platform-portfolio-redefining-ai-data-center-end-to-end-connectivity |
| Credo | 发布 Blue Heron 224G multiprotocol AI scale-up retimer | 224G retimer、UALink/ESUN/Ethernet physical reach | https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx |
| Synopsys | 224G Ethernet PHY IP 页面强调 UALink 200G 与高损耗通道支持 | ASIC PHY IP、UALink 生态、1.6T port-level interoperability | https://www.synopsys.com/designware-ip/interface-ip/ethernet/224g-ethernet-phy-ip.html |
| Cadence | 224G-LR SerDes PHY 覆盖 LR/MR/VSR，面向 AI/HPC 互连 | 统一 PHY 覆盖 scale-up/scale-out，降低多接口 IP 组合复杂度 | https://www.cadence.com/en_US/home/tools/silicon-solutions/design-ip/high-speed-ethernet/224g-lr-ser-des-phy.html |
| NVIDIA | GB300 NVL72 与 Vera Rubin Ultra NVL576 继续推进 rack-scale/multi-rack NVLink domain | GPU fabric 从单柜扩展到多柜，direct optical connection 接近核心路径 | https://developer.nvidia.com/blog/nvidia-vera-rubin-pod-seven-chips-five-rack-scale-systems-one-ai-supercomputer/ |
| OCP/ESUN | 推动 Ethernet for Scale-Up Networking 工作组 | Ethernet 进入开放 scale-up AI fabric | https://www.opencompute.org/blog/introducing-esun-advancing-ethernet-for-scale-up-ai-infrastructure-at-ocp |
| UALink Consortium | 维护 UALink 1.0/2.0 规格与白皮书 | 开放 accelerator fabric 与 memory semantics | https://ualinkconsortium.org/specification/ |
| 中际旭创/新易盛/光迅等 | 国内报道持续关注 800G/1.6T 出货与硅光渗透 | 中国光模块供应链在 AI 模块周期中继续关键 | https://www.stcn.com/article/detail/3626796.html |
| 澜起科技 | DDR5 RCD、PCIe/CXL 互连、AEC/CXL MXC 等方向持续更新 | 国内内存接口和服务器互连芯片生态 | https://www.montage-tech.com/cn/Press_Releases |

## 论文与技术资料速读

1. 🔥 **arXiv:2603.21313 / 3D optoelectronics and co-packaged optics**
   - 重点：把 CPO 放在 3D optoelectronics、封装、热、可靠性和标准化框架中讨论，适合作为 CPO 系统工程读物。
   - 链接：https://arxiv.org/abs/2603.21313

2. 🔥 **arXiv:2602.12521 / Photonic Rails in ML Datacenters with Opus**
   - 重点：用 optical circuit switches 重构 ML datacenter rail fabric，论文声称在特定评估条件下可显著降低网络功耗和成本，但需要接受 OCS reconfiguration latency 带来的训练 overhead。
   - 链接：https://arxiv.org/abs/2602.12521

3. ⭐ **arXiv:2604.12566 / Scalable 3D silicon nitride photonic interposer for high-density optical interconnects**
   - 重点：讨论 3D SiN photonic interposer 用于高密度 optical interconnect，可作为 CPO/NPO routing 与封装扩展性的参考。
   - 链接：https://arxiv.org/html/2604.12566v1

4. ⭐ **arXiv:2510.15893 / Accelerating Frontier MoE Training with 3D Integrated Optics**
   - 重点：从 MoE training 的通信瓶颈出发，讨论 3D integrated optics 如何支撑更大的 logical GPU domain。
   - 链接：https://arxiv.org/html/2510.15893v1

5. ⭐ **npj Nanophotonics / Photonics to scale AI data centers**
   - 重点：综述 CPO、OCS、silicon photonics 在 package、rack、network 层级解决 bandwidth、latency、power bottleneck 的潜力。
   - 链接：https://www.nature.com/articles/s44310-025-00105-1

## 趋势观察

1. **224G 是 2026 年 AI 互连的共同语言，448G 仍处在工程前哨。**
   - 依据：Credo、Synopsys、Cadence、OIF、Keysight 都围绕 224G 做产品、IP、标准或测试；DesignCon 2026 出现 448G 封装分析，但大规模部署仍需要等 channel、package、ADC/DAC、jitter budget 和测试生态成熟。
   - 链接：https://www.keysight.com/us/en/learn/hubs/emerging-technologies/800g/224-gbps.html
   - 链接：https://www.signalintegrityjournal.com/articles/4262-designcon-2026-ai-driven-infrastructure-and-system-level-design

2. **CPO 的关键战场从“能不能做出光引擎”转向“能不能维护、量产、标准化”。**
   - 依据：Broadcom CPO switch 出货、OFC 2026 APC 供应链生态讨论、Siemens 的 CPO trends、PIC Magazine 对 SiPh/InP 供应链拆解都指向同一点：CPO 成败取决于系统工程，而不是单点器件性能。
   - 链接：https://www.ofcconference.org/program/special-events/silicon-photonics-and-co-packaged-optics-standardized-ecosystem/
   - 链接：https://picmagazine.net/article/124176/Shifting_supply_chains_in_the_era_of_photonics

3. **AI data center 的瓶颈正在从 GPU 采购扩展到电力、冷却、融资和施工能力。**
   - 依据：美国多个 data center build-out 被阻或延迟；800VDC/HVDC 成为供电架构候选；Meta/Google 等投资 skilled trades training；AI infrastructure 债务融资扩大。
   - 链接：https://www.businessinsider.com/google-meta-invest-trades-training-ai-data-center-boom-2026-6
   - 链接：https://www.investors.com/news/technology/ai-data-centers-suppliers-nvidia-debt/

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| IEEE 802.3dj 公开资料更新 | 持续关注，7 月 plenary 前后 | 200G/lane electrical/optical、1.6TbE、FEC、test methodology | https://www.ieee802.org/3/dj/public/index.html |
| OIF CEI-224G / Compute Optics Interface 工作项 | 持续关注 | linear optics、224G full linear module、AI compute scale-up optical interface | https://www.oiforum.com/technical-work/current-work/ |
| UALink 规格与生态新闻 | 持续关注 | UALink 2.0、switch/retimer/PHY 生态、与 ESUN/UEC 的关系 | https://ualinkconsortium.org/news/ |
| OCP ESUN 工作组资料 | 持续关注 | Ethernet scale-up networking、XPU interface、lossless/error-resilient topology | https://www.opencompute.org/blog/introducing-esun-advancing-ethernet-for-scale-up-ai-infrastructure-at-ocp |
| DAC 2026 | 2026-07-26 至 2026-07-29 | EDA、3D IC、high-speed IP、advanced packaging、AI silicon design flow | https://dac.com/2026 |
| OCP APAC Summit 2026 | 2026-08-11 至 2026-08-12 | AI cluster、cooling、open data center、ESUN/OCP 生态 | https://www.opencompute.org/summit/2026-ocp-apac-summit |

## 📱 分享卡片

1. 🔥 **224G retimer 正在成为开放 AI scale-up fabric 的底层器件。** Credo Blue Heron 同时面向 UALink、ESUN、Ethernet，说明开放协议落地首先要解决的是 224G 链路 reach 和可靠性。https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx

2. 🔥 **CPO 先在 switch ASIC 侧进入现实。** Broadcom Tomahawk 6 - Davisson 102.4T CPO switch 显示，CPO 的第一波量产更可能从 Ethernet switch 开始，而不是直接上 GPU package。https://investors.broadcom.com/news-releases/news-release-details/broadcom-announces-tomahawkr-6-davisson-industrys-first-1024

3. ⭐ **OIF CEI-224G-Linear 把 linear optics 推进标准化。** 对 1.6T/3.2T 模块来说，FEC、retimer、linear drive 和测试方法会比单纯 lane speed 更关键。https://www.oiforum.com/technical-work/current-work/

4. 🔥 **NVIDIA NVL576 暗示 direct optical connection 会靠近 GPU fabric 核心。** 当 scale-up domain 从单柜扩到 8 柜，铜互连 reach 和功耗会逼近上限。https://developer.nvidia.com/blog/nvidia-vera-rubin-pod-seven-chips-five-rack-scale-systems-one-ai-supercomputer/

5. 🔥 **AI data center 不是只买 GPU，而是买电力、冷却、土地和网络。** 2026 年数据中心融资、HVDC、液冷和项目审批成为 AI 产业链的主约束。https://www.bvp.com/atlas/roadmap-the-ai-data-center-stack


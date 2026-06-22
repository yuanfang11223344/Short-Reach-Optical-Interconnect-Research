# 芯片互连与AI基础设施 每周综述 2026-W26

> 覆盖周期：2026-06-22 至 2026-06-28。本周截至 2026-06-22 仅有当日日报，因此周报以 2026-06-22 日报中的 🔥/⭐ 事件为基础，并补充标准进展、会议论文、硅光子/CPO 产业链、国内厂商、UALink/ESUN/UEC、AI 算力资本开支与数据中心供电/液冷方向。若本周后续日报继续生成，应在下次周报刷新时增量吸收。

## 本周最重要的 8 件事

1. 🔥 **448G SerDes 正式进入 OIF 项目化：VSR/LR 在 2026 年 2 月启动**
   - 要点：OIF OFC 2026 资料显示，CEI-448G framework 已形成公共语言，CEI-448G-VSR 与 CEI-448G-LR 新项目在 2026 年 2 月启动；典型应用包括 chip-to-chip、backplane/midplane/cable 与 rack 内 chassis-to-chassis。
   - 为什么重要：这把 448G 从“未来速率”推进到“可分工的标准项目”。对 SerDes 设计而言，ADC/DAC 架构、FFE/DFE、FFE adaptation、FEC、package/channel 和测试 correlation 都会被重新定义。
   - 来源：https://www.oiforum.com/wp-content/uploads/OIF_EEI_Panel_OFC26.pdf
   - 来源：https://www.oiforum.com/wp-content/uploads/OIF-FD-CEI-448G-01.0.pdf

2. 🔥 **Ethernet Alliance/OIF 资料显示 448G 技术路径会高度依赖 DSP 化收发机和 advanced AFE**
   - 要点：TEF panel 把 448G 可行性拆到 DAC-based TX、ADC-based RX、advanced AFE、SNR-oriented ADC calibration、收敛/自适应算法和先进工艺。
   - 为什么重要：448G 不是简单“224G x2”。它会使 RX ADC、clocking、DSP 算法、package-aware channel model 和量产测试成为同等关键的工程变量。
   - 来源：https://ethernetalliance.org/wp-content/uploads/2025/12/OIF_TEF_Panel2_2512.pdf

3. 🔥 **Rubin full production 把 2026 下半年 rack-scale AI server 供应链拉入执行期**
   - 要点：NVIDIA 宣布 Vera Rubin platform ramping into full production；Rubin-based products 将在 2026 下半年由合作伙伴提供。Vera Rubin NVL72 配置 72 Rubin GPU、36 Vera CPU 和 NVLink 6。
   - 为什么重要：Rubin 不是单颗 GPU 代际，而是 rack-scale system 代际。NVLink、ConnectX/BlueField、direct optical、液冷、800 VDC 和整柜交付会同步成为产业链核心约束。
   - 来源：https://nvidianews.nvidia.com/news/vera-rubin-full-production-agentic-ai-factory
   - 来源：https://nvidianews.nvidia.com/news/nvidia-vera-rubin-platform

4. 🔥 **800 VDC 从架构讨论进入供应链展示：LITEON 展示 Vera Rubin NVL72 power infrastructure**
   - 要点：LITEON 在 COMPUTEX 2026 展示 800 VDC power infrastructure、rack integration 和 liquid cooling，明确面向 NVIDIA Vera Rubin NVL72。
   - 为什么重要：AI rack power density 推高后，供电架构不再是机房后端问题，而会影响 rack mechanical、电源架、busbar、冷板/管路、维护安全和整柜认证。
   - 来源：https://www.liteon.com/en/news/press-center/content/liteon-nvidia-mgx-computex-2026

5. 🔥 **AI data center 的瓶颈继续外溢到并网、自备电源和用水审批**
   - 要点：FERC 正推进大型 AI data center load 接网加速；Bloom Energy mid-year report 经 ITPro 报道称超过 60% 开发商计划自发电；Oracle Project Jupiter 因水资源问题引发争议。
   - 为什么重要：光模块和 SerDes 的需求强度长期由 AI capex 支撑，但短期项目上线节奏会被电力、水、土地和社区审批强烈调制。
   - 来源：https://www.tomshardware.com/tech-industry/data-centers/us-energy-regulator-to-order-grid-operators-to-expedite-ai-data-center-applications-says-projects-should-bring-their-own-power-or-cut-usage-during-high-demand
   - 来源：https://www.itpro.com/infrastructure/data-centres/ai-data-center-growth-stymied-by-power-constraints
   - 来源：https://www.tomshardware.com/tech-industry/big-tech/project-jupiter-ai-data-center-build-raises-concerns-about-water-usage-in-rural-new-mexico-desert-oracle-calls-water-usage-negligible-for-11-million-gallon-one-time-fill

6. ⭐ **LPO/NPO/CPO 路线争论继续收敛到系统级 trade-off**
   - 要点：IEEE EPS LPO overview 强调 LPO 的低功耗、低延迟和 pluggable 可维护性，同时指出距离、BER、标准、host SerDes 复杂度等短板；Yole 把 CPO photonics packaging 作为 AI infrastructure 长线主题。
   - 为什么重要：未来 1.6T/3.2T 光链路不会只有一种答案。LPO 适合保留模块可维护性，NPO/On-board optics 是工程折中，CPO 追求最高密度和能效；最终由功耗、可维护、测试和供应链良率共同决定。
   - 来源：https://eps.ieee.org/wp-content/uploads/2026/03/Linear-Pluggable-Optics_V2-UPDATED.pdf
   - 来源：https://www.yolegroup.com/press-release/co-packaged-optics-powering-the-next-wave-of-ai-infrastructures/

7. ⭐ **OCP ESUN、UALink、UEC 继续构成开放 AI fabric 的三层变量**
   - 要点：ESUN 聚焦 Ethernet for Scale-Up Networking；OCP APAC Summit 2026 征稿主题把 ESUN、SUE-T、UALink 和 UEC 放进 AI cluster 轨道；UEC 继续服务 scale-out transport，UALink 服务 accelerator fabric。
   - 为什么重要：开放 AI fabric 不会只由单个协议决定。Scale-up 的 memory/accelerator semantics、Ethernet 生态复用、scale-out congestion control 和物理层 224G/448G 会共同塑造下一代 XPU cluster。
   - 来源：https://www.opencompute.org/blog/introducing-esun-advancing-ethernet-for-scale-up-ai-infrastructure-at-ocp
   - 来源：https://www.opencompute.org/summit/2026-ocp-apac-summit/call-for-presentations
   - 来源：https://ualinkconsortium.org/specification/
   - 来源：https://ultraethernet.org/wp-content/uploads/sites/20/2026/01/UE-Specification-1.0.2-1.pdf

8. ⭐ **国内光模块/光芯片关注点从 800G 出货扩展到 1.6T、CW 光源、硅光和 CPO/NPO**
   - 要点：近期国内报告和报道继续关注中际旭创、新易盛、天孚通信、华工科技、光迅科技、源杰科技、长光华芯等链条；其中研报类数据属于机构预测，需结合公司公告和量产节点验证。
   - 为什么重要：中国供应链在模块组装、光引擎、无源器件、光芯片和测试产能上仍是 800G/1.6T 周期的重要变量；但高端 EML/CW、硅光工艺和 CPO 封装仍需要持续验证。
   - 来源：https://www.fxbaogao.com/detail/5484843
   - 来源：https://www.21jingji.com/article/20260503/herald/cbdd6cc2ee8be8fa2cac353b5f2dd4ea.html
   - 来源：https://finance.ifeng.com/c/8trirKfTWLs

## 本周关键技术进展（3篇深读）

### 1. 224G 到 448G SerDes：从 lane speed 升级变成系统工程重构

- 背景：224G PAM4 已经成为 1.6T optics、AI switch ASIC、scale-up retimer 和 UALink/ESUN/Ethernet 物理层的共同基线。448G 的推进则被 AI 网络端口密度、3.2T 模块和 204.8T/更高容量交换芯片牵引。
- 本周信号：OIF CEI-448G-VSR/LR 项目启动；Ethernet Alliance/OIF TEF 资料把 448G 可行性落实到 DAC TX、ADC RX、AFE、校准、收敛算法和先进工艺；400G/lane panel 继续强调 FEC、breakout 和 HDC form factor。
- 对设计团队的影响：SerDes 设计需要更早引入 package/channel co-design，RX ADC mismatch、timing skew、DSP convergence、FFE/DFE adaptation 和 on-die instrumentation 重要性上升。对系统团队，448G 的 reach 定义会直接影响 cable/backplane、retimer 插入点和 opto-electrical split。
- 风险：项目启动不等于量产成熟。448G 还需要仪器、compliance、connector、FEC latency 和跨厂互操作验证闭环。
- 来源：https://www.oiforum.com/wp-content/uploads/OIF_EEI_Panel_OFC26.pdf
- 来源：https://ethernetalliance.org/wp-content/uploads/2025/12/OIF_TEF_Panel2_2512.pdf
- 来源：https://ethernetalliance.org/wp-content/uploads/2025/12/All_TEF_Panel3_2512.pdf
- 来源：https://socionextus.com/wp-content/uploads/2026/02/Socionext-Whitepaper_Package-Analysis-for-224G-448Gbps-High%E2%80%91Speed-SerDes-1.pdf

### 2. CPO/LPO/NPO 与 silicon photonics：路线之争转向可制造和可维护

- 背景：AI cluster 的 bandwidth density 继续提升，可插拔模块到 switch ASIC 的电走线功耗和 SI margin 越来越紧。CPO 提供极致能效和密度，LPO 保留 pluggable 维修性并降低 DSP 功耗，NPO/on-board optics 作为过渡路线降低电通道长度。
- 本周信号：IEEE EPS LPO overview 把 LPO 的优劣写得很清楚；Yole 把 CPO photonics packaging 定位为 AI infrastructure 长线市场；Corning 的 AI photonics 叙事说明上游材料/光纤/连接产业正在进入 CPO/SiPh 产能周期；SuperX 展示 1.6T module 与 AIDC full-stack 方案，显示 optics 正被整站方案吸收。
- 对产业链的影响：CPO 不是“模块厂消失”，而是价值链重新分配。光引擎、external laser source、PIC foundry、InP laser、fiber attach、thermal design、ATE/DFT、现场维护方案会共同决定落地速度。
- 风险：LPO 对 host SerDes 和系统级误码容忍提出更高要求；CPO 的现场维修、良率分摊和供应链责任边界仍需标准化。
- 来源：https://eps.ieee.org/wp-content/uploads/2026/03/Linear-Pluggable-Optics_V2-UPDATED.pdf
- 来源：https://www.yolegroup.com/press-release/co-packaged-optics-powering-the-next-wave-of-ai-infrastructures/
- 来源：https://www.investors.com/research/ibd-stock-of-the-day/corning-stock-artificial-intelligence-data-centers-photonics/
- 来源：https://www.prnewswire.com/news-releases/superx-to-introduce-1-6t-optical-modules-and-showcase-full-stack-aidc-solutions-at-interop-tokyo-2026--302792216.html

### 3. AI factory 基础设施：power、cooling、network 和 finance 变成同一个约束系统

- 背景：AI server 从 HGX 级节点走到 NVL72/NVL144/NVL576 级 rack/pod，单柜功率、冷却、光/铜布线、供电、施工和审批全部耦合。互连功耗已经不能只用 pJ/bit 评价，还要映射到 rack thermal budget、CDU 容量和配电架构。
- 本周信号：NVIDIA Vera Rubin full production 表示 rack-scale 代际进入执行；LITEON 展示 800 VDC 和 Rubin NVL72 power/cooling；FERC/ITPro/Tom's Hardware 多条新闻显示电网、自备电源和水资源是 AI data center 建设的现实瓶颈。
- 对工程的影响：高密机柜会推动 800 VDC/HVDC、direct liquid cooling、closed-loop cooling、on-site power、busbar 和 modular data center。光模块、AEC、retimer 和 switch ASIC 的功耗优化会直接影响可部署 GPU 密度。
- 风险：政策和地方审批会导致项目节奏不均；自备电源和闭环冷却降低一类约束，但可能增加资本开支、维护复杂度和供应链依赖。
- 来源：https://nvidianews.nvidia.com/news/vera-rubin-full-production-agentic-ai-factory
- 来源：https://www.liteon.com/en/news/press-center/content/liteon-nvidia-mgx-computex-2026
- 来源：https://www.itpro.com/infrastructure/data-centres/ai-data-center-growth-stymied-by-power-constraints
- 来源：https://news.mit.edu/2026/nuclear-inspired-cooling-system-ferveret-could-make-data-centers-more-sustainable-0610

## 厂商动态汇总

| 厂商/组织 | 本周/近期动作 | 影响方向 | 链接 |
|---|---|---|---|
| OIF | CEI-448G-VSR/LR 项目在 2026 年 2 月启动；EEI/COI 继续讨论 AI compute optics | 448G electrical、compute optics、CPO/COI 标准化 | https://www.oiforum.com/wp-content/uploads/OIF_EEI_Panel_OFC26.pdf |
| Ethernet Alliance | TEF panel 资料系统化讨论 448G SerDes、400G signaling for AI networks | ADC/DAC SerDes、FEC、HDC、breakout | https://ethernetalliance.org/wp-content/uploads/2025/12/OIF_TEF_Panel2_2512.pdf |
| NVIDIA | Vera Rubin ramping into full production；NVL72/NVL144/NVL576 继续定义 rack-scale AI | NVLink 6、direct optical、液冷、AI rack | https://nvidianews.nvidia.com/news/vera-rubin-full-production-agentic-ai-factory |
| LITEON | COMPUTEX 2026 展示 800 VDC 和 Vera Rubin NVL72 AI factory 方案 | 高压直流、整柜电源、液冷 | https://www.liteon.com/en/news/press-center/content/liteon-nvidia-mgx-computex-2026 |
| Corning | AI data center photonics 成为长期增长叙事，关注 silicon photonics/CPO | 光纤、玻璃、连接、SiPh/CPO 材料链 | https://www.investors.com/research/ibd-stock-of-the-day/corning-stock-artificial-intelligence-data-centers-photonics/ |
| SuperX | Interop Tokyo 2026 展示 1.6T optical module 和 full-stack AIDC | 光模块进入整站集成方案 | https://www.prnewswire.com/news-releases/superx-to-introduce-1-6t-optical-modules-and-showcase-full-stack-aidc-solutions-at-interop-tokyo-2026--302792216.html |
| Vertiv | 市场继续关注其 AI data center power/liquid cooling 增长 | 冷却、供电、NVIDIA 生态 | https://www.investors.com/research/ibd-stock-of-the-day/vertiv-stock-buy-points-ai-data-centers-explosive-growth/ |
| OCP ESUN | 继续推进 Ethernet scale-up networking 工作流，APAC Summit 主题包含 ESUN/UALink/UEC | 开放 AI fabric、XPU/switch 互操作 | https://www.opencompute.org/blog/introducing-esun-advancing-ethernet-for-scale-up-ai-infrastructure-at-ocp |
| 国内光模块/光芯片链 | 机构报告继续关注 1.6T、CPO/NPO、CW 光源、硅光、EML/VCSEL | 中国供应链、光引擎、光芯片国产化 | https://www.fxbaogao.com/detail/5484843 |

## 论文与技术资料速读

1. 🔥 **arXiv:2606.19674 / Design Considerations for Phase Modulation in Testable Photonic Systems and Co-packaged Optics**
   - 重点：面向复杂 SiPh PIC/CPO 的可测试性，比较 thermal phase modulation 和 carrier-based electrical modulation 在 extinction ratio、tuning efficiency、power、bandwidth 上的取舍。
   - 链接：https://arxiv.org/abs/2606.19674

2. ⭐ **arXiv:2606.08885 / Silicon Photonics Testing: Design for Testability, Fault Detection**
   - 重点：提出 SiPh integrated circuits 的 DFT 和 fault detection 架构，对 CPO/NPO 量产测试有参考价值。
   - 链接：https://arxiv.org/abs/2606.08885

3. ⭐ **arXiv:2605.28971 / Micro-Transfer Printing of Lithium Niobate on 200 mm Silicon Photonics**
   - 重点：TFLN on SiPh 的 wafer-scale heterogeneous integration，服务高速低能耗 photonic interconnect。
   - 链接：https://arxiv.org/abs/2605.28971

4. ⭐ **arXiv:2602.12521 / Photonic Rails in ML Datacenters with Opus**
   - 重点：用 optical circuit switches 重构 ML datacenter rail fabric，适合评估 optics 从链路级进入拓扑级的收益和代价。
   - 链接：https://arxiv.org/abs/2602.12521

5. 📌 **OIF Energy Efficient Photonic Interconnects for AI Compute Scale-up**
   - 重点：比较 448G electrical-optical link approach 与 slow-wide electrical interface，对 COI、UCIe-like interface、CPO/optical engine 切分有指导意义。
   - 链接：https://www.oiforum.com/wp-content/uploads/OIF-EEI-COI-WP-01.0.pdf

## 趋势观察

1. **448G 的首要瓶颈会是系统 margin，而不是单个 PHY 指标。**
   - 依据：OIF 和 TEF 资料同时强调 ADC/DAC、AFE、校准、通道和封装。工程上需要把 package model、board loss、connector launch、compliance fixture 和 DSP adaptation 放在同一套验证流里。
   - 链接：https://ethernetalliance.org/wp-content/uploads/2025/12/OIF_TEF_Panel2_2512.pdf

2. **Rubin/NVL 时代会把 optical interconnect 从网络层推近 GPU fabric 核心路径。**
   - 依据：NVIDIA 已公开 NVL72/NVL144/NVL576 多层 scale-up domain；rack-to-rack 和 pod-scale 的互连距离会让 direct optical、CPO/NPO、AEC/ACC 混合部署更现实。
   - 链接：https://nvidianews.nvidia.com/news/nvidia-vera-rubin-platform

3. **CPO 与 LPO 的路线选择将由“谁承担复杂度”决定。**
   - 依据：LPO 去掉模块 DSP 但把误码和均衡压力推给 host；CPO 缩短电链路但把维护、封装和良率问题推给系统/封装生态。
   - 链接：https://eps.ieee.org/wp-content/uploads/2026/03/Linear-Pluggable-Optics_V2-UPDATED.pdf

4. **AI data center capex 越大，项目上线越依赖电力和冷却。**
   - 依据：FERC 加速并网、Bloom Energy 报告自备电源比例上升、Oracle 项目水资源争议和 Vertiv/LITEON 的高密供冷方案，都说明基础设施是 AI 算力交付的硬约束。
   - 链接：https://www.itpro.com/infrastructure/data-centres/ai-data-center-growth-stymied-by-power-constraints

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| OCP Open Systems for AI Workshop | 2026-06-25 | 高密 AI 基础设施供电、热管理、开放系统 | https://www.opencompute.org/events/upcoming-events/ai-events |
| IEEE 802.3 7 月 plenary 资料 | 2026-07-13 至 2026-07-17 | 1.6T/3.2T Ethernet、200G/400G lane、FEC/test methodology | https://www.ieee802.org/3/interims/index.html |
| OIF CEI-448G / COI 工作项 | 持续关注 | VSR/LR reach、compute optics interface、EEI | https://www.oiforum.com/technical-work/current-work/ |
| UALink 规格和成员生态 | 持续关注 | UALink 2.0、retimer/PHY/switch IP、与 ESUN 的边界 | https://ualinkconsortium.org/news/ |
| OCP APAC Summit 2026 | 2026-08-11 至 2026-08-12 | ESUN、SUE-T、UALink、UEC、AI cluster 经验 | https://www.opencompute.org/summit/2026-ocp-apac-summit/call-for-presentations |
| OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | AI Breakout、FTS、开放机柜、网络和光互连 | https://www.opencompute.org/summit/global-summit |

## 📱 分享卡片

1. 🔥 **448G SerDes 已经进入 OIF 项目化阶段。** 真正难点会是 ADC/DAC、advanced AFE、package/channel、FEC 与测试一致性，而不是单纯把 224G 翻倍。https://www.oiforum.com/wp-content/uploads/OIF_EEI_Panel_OFC26.pdf

2. 🔥 **Rubin full production 意味着 2026 下半年 rack-scale AI 进入执行期。** NVL72 的 72 GPU/36 CPU/NVLink 6 会继续推高 direct optical、液冷和高压供电需求。https://nvidianews.nvidia.com/news/vera-rubin-full-production-agentic-ai-factory

3. ⭐ **LPO、NPO、CPO 不是谁完全替代谁，而是谁承担复杂度。** LPO 把压力推给 host SerDes，CPO 把压力推给封装、测试和维护生态。https://eps.ieee.org/wp-content/uploads/2026/03/Linear-Pluggable-Optics_V2-UPDATED.pdf

4. 🔥 **AI data center 现在是电网工程。** 并网、自备电源、水资源和闭环冷却会直接影响 GPU rack 与 1.6T optics 的出货节奏。https://www.itpro.com/infrastructure/data-centres/ai-data-center-growth-stymied-by-power-constraints

5. ⭐ **中国光模块链条的关键词从 800G 出货扩展到 1.6T、CW 光源、硅光和 CPO/NPO。** 机构观点需要等待公司公告和量产验证，但方向值得持续跟踪。https://www.fxbaogao.com/detail/5484843

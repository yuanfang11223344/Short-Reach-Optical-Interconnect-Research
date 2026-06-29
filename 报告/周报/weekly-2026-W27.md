# 芯片互连与AI基础设施 每周综述 2026-W27

> 覆盖周期：2026-06-29 至 2026-07-05。本周周报在周一生成，先纳入 6 月 29 日日报，再以标准、官方产品、论文和产业链资料补充六个深度方向。后续日报将继续记录本周增量。

## 本周最重要的 8 件事

1. 🔥 **IEEE P802.3dj Draft 3.1 进入 ballot comment 收敛**
   - 要点：200G/lane electrical/optical PMD、FEC 和管理条款的 received comments 已公开。
   - 为什么重要：224G SerDes 的竞争从单颗 PHY 指标转向 package/channel model、retimer、FEC 与测试相关性的系统工程；规范评论是识别量产风险最直接的窗口。
   - 来源：https://www.ieee802.org/3/dj/comments/index.html

2. 🔥 **OIF CEI-448G-VSR/LR 已项目化**
   - 要点：CEI-448G framework 之后，VSR 与 LR 项目开始定义 448G electrical interface 的实际 reach 和应用边界。
   - 为什么重要：448G PAM4 将显著压缩 symbol UI 与模拟裕量，ADC/DAC、equalization、clocking、package、connector 和 compliance test 都需要代际升级。
   - 来源：https://www.oiforum.com/technical-work/current-work/

3. 🔥 **Spectrum-X Ethernet Photonics 把 CPO 纳入量产 AI 网络平台**
   - 要点：NVIDIA 官方将其列入 Vera Rubin 系统并称已进入 production。
   - 为什么重要：CPO 不再只是 optical engine demo，而是与 switch ASIC、network software、ELS、运维和供应链共同交付；这会改变 pluggable module 与交换平台的价值分配。
   - 来源：https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Vera-Rubin-Ramps-Into-Full-Production-to-Power-Agentic-AI-Factories-Worldwide/default.aspx

4. 🔥 **OpenLight 3.2T DR8 PIC 将路线推进至 400G/lane**
   - 要点：3.2T DR8 silicon photonics PIC 样片与 1.6T LRO/LPO variants 同时出现。
   - 为什么重要：400G/lane 能否产品化取决于 EAM、driver/TIA、DSP、封装损耗、thermal drift 与测试吞吐共同闭环，不是单器件速率展示。
   - 来源：https://www.ofcconference.org/news-media/exhibitor-news/openlight-introduces-3-2t-dr8-silicon-photonics-pic-s-as-well-as-1-6t-dr8-lro-and-lpo-variants/

5. 🔥 **224G multiprotocol retimer 把 UALink、ESUN 与 Ethernet 放到共同 PHY 底座**
   - 要点：Credo Blue Heron 面向多种 AI scale-up/scale-out protocol。
   - 为什么重要：物理层复用后，产业竞争将更多集中在 latency、memory semantics、congestion control、RAS、telemetry 和软件生态，而 retimer 成为协议切换与 channel closure 的关键节点。
   - 来源：https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx

6. ⭐ **Vera Rubin 的交付单元上移到 POD 与 facility**
   - 要点：NVL72、BlueField-4 storage、Spectrum-6 Ethernet racks 与液冷/供电 blueprint 共同进入系统叙事。
   - 为什么重要：AI 服务器厂商的验证边界从节点扩展到 rack、network、storage、power 和 cooling，传统部件采购将更多转向平台认证。
   - 来源：https://developer.nvidia.com/blog/inside-the-nvidia-rubin-platform-six-new-chips-one-ai-supercomputer/
   - 补充：https://ir.supermicro.com/news/news-details/2026/Supermicro-Delivers-NVIDIA-Vera-Rubin-NVL4-End-to-End-DCBBS-Blueprint-with-Native-FP64-Performance-for-Converged-HPC-and-AI-Infrastructure/default.aspx

7. 🔥 **FERC 直接介入 large-load 并网规则**
   - 要点：六个区域电网运营方被要求解释或改革 data center 等大负载接入机制。
   - 为什么重要：电网接入周期开始主导 AI cluster 的建设节奏，推动 HVDC、microgrid、load flexibility 和分阶段扩容成为架构变量。
   - 来源：https://www.ferc.gov/news-events/news/ferc-launches-aggressive-targeted-action-speed-large-load-integration

8. ⭐ **AI rack 供电研究从 48V 延伸到 facility-level DC 与中压变换**
   - 要点：arXiv:2606.25095 系统梳理高变比 DC/DC、LVDC 与 medium-voltage solid-state transformer。
   - 为什么重要：当 rack power density、负载瞬态和铜损同时上升，供电拓扑将像网络拓扑一样影响计算平台性能、可用性和成本。
   - 来源：https://arxiv.org/abs/2606.25095

## 本周关键技术进展（3篇深读）

### 1. 224G 规范收敛与 448G 项目启动形成代际重叠

**背景现状**

224G PAM4 正从 IP demonstration 进入 200G/lane Ethernet 的规范和量产验证阶段。此时链路是否闭合不再只由 transmitter/receiver 决定，而由 die、package、PCB、connector、cable、retimer、FEC 和 test fixture 的联合模型决定。

**本周新进展**

P802.3dj Draft 3.1 comments 已公开，OIF CEI-224G-LR/MR 通过 liaison 与 IEEE 对齐；与此同时 CEI-448G-VSR/LR 已项目化。来源：https://www.ieee802.org/3/dj/comments/index.html ，https://ieee802.org/3/dj/public/26_05/index.html ，https://www.oiforum.com/technical-work/current-work/

**对产业链的影响**

SerDes IP 厂商需要同时维护 224G 产品化和 448G architecture exploration；封装、连接器和测试厂商会更早参与 reference model。Retimer 的价值也从“补损耗”上移到 telemetry、lane repair、protocol adaptation 和 RAS。

**未来 1-2 年推演**

224G 将进入更密集的 interoperability 和 compliance 阶段，448G 则先在 VSR/LR channel assumptions、modulation/DSP power 与 package feasibility 上分化。短期内 448G 不会取代 224G，而会反向约束 224G 平台的可复用 clocking、ADC/DAC 和 DSP 架构。

### 2. CPO 从器件展示走向交换平台，但 NPO/OBO 仍有窗口

**背景现状**

Pluggable optics 在 800G/1.6T 仍具成熟供应链和可维护性优势，但 switch radix 与 SerDes I/O power 推动 optics 向 ASIC 靠近。CPO 的难点集中在 laser serviceability、fiber attach、thermal coupling、yield 和现场维修。

**本周新进展**

NVIDIA 将 Spectrum-X Ethernet Photonics 纳入 Vera Rubin 量产平台；Coherent 展示 6.4T socketed CPO，Lightmatter L20 同时覆盖 NPO/OBO，OpenLight 则提供 3.2T DR8 PIC 与 1.6T LRO/LPO variants。来源：https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Vera-Rubin-Ramps-Into-Full-Production-to-Power-Agentic-AI-Factories-Worldwide/default.aspx ，https://www.coherent.com/news/press-releases/coherent-co-packaged-optics-cpo-technologies-ofc-2026 ，https://www.ofcconference.org/news-media/exhibitor-news/lightmatter-expands-photonic-interconnect-roadmap-with-passage-l20-unified-optical-engine/ ，https://www.ofcconference.org/news-media/exhibitor-news/openlight-introduces-3-2t-dr8-silicon-photonics-pic-s-as-well-as-1-6t-dr8-lro-and-lpo-variants/

**对产业链的影响**

交换 ASIC 厂商将获得更强的平台整合权；传统模块厂商不会立刻退出，而会向 optical engine、ELS、fiber attach、NPO/LPO 和测试服务迁移。Foundry、advanced packaging 与 photonic EDA 的协同会决定设计迭代速度。

**未来 1-2 年推演**

CPO 将先在封闭生态、高 radix spine 和功耗敏感场景放量；pluggable 1.6T 与 NPO/OBO 将继续承担通用部署。真正的转折点不是单次 demo，而是多来源 optical engine、可更换 laser、标准化 fiber connector 与 field failure data 的形成。

### 3. AI 基础设施从 rack 共设计扩展到电网共设计

**背景现状**

高密度 AI rack 同时带来稳态功率、快速负载瞬态、冷却水温和并网容量问题。传统 48V rack 与低压 AC distribution 在铜损、转换级数和设备体积方面承压。

**本周新进展**

FERC 对 large-load integration 启动 targeted action；arXiv:2606.25095 提出 facility-level DC 与中压 power conversion 的研究框架；Delta 和 Huawei 分别把 800VDC、liquid cooling、microgrid 与 grid-interactive AIDC 组合。来源：https://www.ferc.gov/news-events/news/ferc-launches-aggressive-targeted-action-speed-large-load-integration ，https://arxiv.org/abs/2606.25095 ，https://www.deltaww.com/en-US/press/40334 ，https://www.huawei.com/en/news/2026/5/global-aidc-industry-summit

**对产业链的影响**

服务器 ODM、电源厂商、液冷厂商、园区开发商和电网运营方的接口会提前冻结；UPS、busbar、DC/DC、CDU 和 controls 需要围绕共同的 transient/RAS 模型验证。

**未来 1-2 年推演**

800VDC 和 medium-voltage conversion 会先在新建 AI factory 试点，存量数据中心仍以渐进改造为主。可调度 workload、储能和 microgrid 将与 distributed training scheduler 发生更直接的耦合。

## 厂商动态汇总

| 厂商 | 本周动作/状态 | 影响方向 | 链接 |
|---|---|---|---|
| Broadcom | 持续跟踪 51.2T/102.4T switch 与 CPO 平台；本周未发现可核实新增 | switch ASIC/CPO | https://www.broadcom.com/products/ethernet-connectivity/switching/strataxgs |
| Marvell | 持续跟踪 1.6T DSP、optical engine 与 scale-up silicon；本周未发现可核实新增 | DSP/optical connectivity | https://www.marvell.com/products/optical-dsp.html |
| Credo | Blue Heron 224G multiprotocol retimer 支持 UALink/ESUN/Ethernet | retimer/scale-up PHY | https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx |
| Synopsys | 持续跟踪 224G/448G SerDes IP 与 photonic design flow；本周未发现可核实新增 | SerDes IP/EDA | https://www.synopsys.com/designware-ip/interface-ip/serdes-ip.html |
| Cadence | 持续跟踪高速 PHY、signal integrity 与 photonics flow；本周未发现可核实新增 | EDA/system analysis | https://www.cadence.com/en_US/home/tools/system-analysis.html |
| NVIDIA | Vera Rubin 量产爬坡，Spectrum-X Ethernet Photonics 进入 production | rack-scale/CPO | https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Vera-Rubin-Ramps-Into-Full-Production-to-Power-Agentic-AI-Factories-Worldwide/default.aspx |
| Intel | 持续跟踪 optical I/O 与 silicon photonics；本周未发现可核实新增 | optical I/O/SiPh | https://www.intel.com/content/www/us/en/architecture-and-technology/silicon-photonics/silicon-photonics-overview.html |
| OpenLight | 3.2T DR8 PIC 与 1.6T LRO/LPO variants | heterogeneous SiPh | https://www.ofcconference.org/news-media/exhibitor-news/openlight-introduces-3-2t-dr8-silicon-photonics-pic-s-as-well-as-1-6t-dr8-lro-and-lpo-variants/ |
| Coherent | 6.4T socketed CPO、ELS、VCSEL CPO 和 400G modulator | CPO/optical engine | https://www.coherent.com/news/press-releases/coherent-co-packaged-optics-cpo-technologies-ofc-2026 |
| Huawei（国内） | grid-interactive AIDC 策略整合供电、液冷与 O&M | AIDC infrastructure | https://www.huawei.com/en/news/2026/5/global-aidc-industry-summit |
| HYC（国内） | MCF 与 CPO passive interconnect 方案 | fiber attach/high-density connector | https://www.ofcconference.org/news-media/exhibitor-news/hyc-showcases-multi-core-fiber-and-cpo-interconnect-solutions-at-ofc-2026/ |
| 中际旭创/新易盛/光迅（国内） | 本周未找到足够一手新增，继续跟踪 1.6T 量产、3.2T 验证和 CPO/NPO 路线 | optical module | https://www.nepconasia.com/zh-cn/news-center/zhxx/2026/6/1.html |

## 趋势观察

### 1. 224G 产品化与 448G 预研将长期重叠

P802.3dj Draft 3.1 正在收敛，而 OIF 已启动 CEI-448G-VSR/LR。芯片团队不能把两代视为串行项目：224G 的 reference package、DSP adaptation 和 test correlation 会直接成为 448G 的初始约束。来源：https://www.ieee802.org/3/dj/comments/index.html ，https://www.oiforum.com/technical-work/current-work/

### 2. CPO 的先发优势来自平台闭环，而非单一 photonic device

NVIDIA 的 production 表述与 Coherent/OpenLight/Lightmatter 的多形态 optical engine 共同说明，CPO 的商业门槛是 ASIC、optics、ELS、packaging、network OS 和 field service 的联合成熟。单器件带宽领先并不足以建立系统优势。来源：https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Vera-Rubin-Ramps-Into-Full-Production-to-Power-Agentic-AI-Factories-Worldwide/default.aspx ，https://www.coherent.com/news/press-releases/coherent-co-packaged-optics-cpo-technologies-ofc-2026

### 3. Power availability 正在取代 PUE 成为更前置的指标

FERC 的并网行动和 facility-level DC 研究说明，设施设计目标已从“建成后提高效率”转向“能否及时获得并稳定交付电力”。这会推动 workload scheduling、储能和 microgrid 与训练网络共同规划。来源：https://www.ferc.gov/news-events/news/ferc-launches-aggressive-targeted-action-speed-large-load-integration ，https://arxiv.org/abs/2606.25095

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| RAISE Summit 2026 | 2026-07-08 至 07-09 | AI factory power、cooling、controls 与 services | https://www.vertiv.com/en-emea/about/news-and-events/events/2026/vertiv-at-raise-summit-2026--building-the-physical-foundation-of-ai/ |
| IEEE 802 July Plenary | 2026-07-12 起 | P802.3dj Draft 3.1 comments、200G/lane 与 1.6TbE | https://802world.org/plenary/schedule/ |
| OIF CEI-448G 项目 | 持续跟踪 | VSR/LR reach、channel model、package 与 compliance | https://www.oiforum.com/technical-work/current-work/ |
| UALink/ESUN/UEC | 持续跟踪 | 224G PHY 共平台后的 link layer、congestion 与 RAS 差异 | https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx |

## 📱 分享卡片

1. 🔥 **224G 在收敛，448G 已启动**：SerDes 团队即将进入两代并行，package、DSP 和 test architecture 需要提前复用。https://www.oiforum.com/technical-work/current-work/
2. 🔥 **CPO 的拐点是平台化量产**：Spectrum-X Ethernet Photonics 已被纳入 Vera Rubin AI factory，而不是停留在单点 demo。https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Vera-Rubin-Ramps-Into-Full-Production-to-Power-Agentic-AI-Factories-Worldwide/default.aspx
3. 🔥 **3.2T 的真正难题是 400G/lane 全链路**：PIC、driver/TIA、DSP、封装和测试缺一不可。https://www.ofcconference.org/news-media/exhibitor-news/openlight-introduces-3-2t-dr8-silicon-photonics-pic-s-as-well-as-1-6t-dr8-lro-and-lpo-variants/
4. ⭐ **多协议 retimer 正成为 AI fabric 的共同底座**：UALink、ESUN 与 Ethernet 的差异会更多上移到协议和软件层。https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx
5. 🔥 **AI 数据中心首先是电力项目**：并网、HVDC、液冷和 workload flexibility 已经进入同一架构问题。https://www.ferc.gov/news-events/news/ferc-launches-aggressive-targeted-action-speed-large-load-integration

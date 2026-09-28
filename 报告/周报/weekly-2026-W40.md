# 芯片互连与AI基础设施 每周综述 2026-W40

> 生成时间：2026-09-28 10:00（Asia/Shanghai）。周一例行周报；已先生成 `2026-09-28.md`，并纳入其中 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-09-28，后续日报继续作为 W40 周报滚动素材。

## 本周最重要的 5-8 件事

### 🔥 ECOC 后的核心结论：AI interconnect 正从单点器件参数转向可部署闭环

- 要点：OIF 的 ECOC 2026 互操作覆盖 CEI-448G/224G、CMIS、Co-Packaging、EEI 与 coherent optics；Ethernet Alliance 的 1.6T demo 则把 224G per lane optics、112G copper coexistence 与 AI lossless link 放在 multi-vendor 场景。https://www.oiforum.com/oif-brings-industry-wide-interoperability-to-life-at-ecoc-2026-accelerating-scalable-efficient-networks-for-the-ai-era/  https://ethernetalliance.org/blog/2026/09/09/1-6t-ethernet-moves-closer-to-reality-in-ethernet-alliances-ecoc-2026-demo/
- 为什么重要：1.6T/3.2T optics 的真实门槛不是“单模块能否发光”，而是 host ASIC、SerDes、FEC、CMIS、connector、thermal telemetry、test equipment 和 network workload 能否一起稳定工作。

### 🔥 400G/lane 与 448G per lane 把 SerDes、modulation 和 optical front-end 绑定得更紧

- 要点：Marvell 展示 2nm 400G/lane optical PAM4 与 1.6T coherent-lite/ZR demo；Nokia 展示 448G per lane transmission preview；arXiv:2609.24570 比较 PAM4/PAM6/PAM8 与 MLSE 在 net 400G 条件下的性能边界。https://www.marvell.com/company/newsroom/marvell-industry-first-2nm-optical-technology-ai-data-center-infrastructure-ecoc-2026.html  https://www.nokia.com/events/nokia-at-ecoc/  https://arxiv.org/abs/2609.24570
- 为什么重要：下一代 electrical/optical I/O 已经不能只看 lane rate。信道 bandwidth limitation、FEC limit、DSP/MLSE 复杂度、modulator/driver 带宽和封装寄生都在同一预算内竞争。

### 🔥 CPX/CPO/NPO 的关注点开始转向 serviceability

- 要点：Ciena 展示 Open CPX compliant Vesta 200 6.4T CPX optical engine；Lumentum 展示面向 OCI MSA 的 DWDM ELSFP laser module；Furukawa/Lightera Snap-Beam detachable PIC connector 获 ECOC Fibre Infrastructure Innovation Award。https://www.ciena.com/about/newsroom/press-releases/ciena-highlights-high-performance-ai-networking-at-ecoc-2026  https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx  https://lightera.com/n/furukawa-electric-and-lighteras-snap-beam-connector-for-co-packaged-optics-wins-ecoc-fibre-infrastructure-innovation-award-2026/
- 为什么重要：当光引擎靠近 switch/accelerator package，外置光源、detachable connector、清洁维护、液冷耦合、现场更换和故障定位会决定 CPO/NPO 是否能越过实验室 demo 阶段。

### 🔥 Testing/validation 成为 AI supernode 上线的独立赛道

- 要点：VIAVI 在 ECOC 2026 展示 end-to-end data center testing portfolio，覆盖 scale-up、scale-out、scale-across、1.6T L0-L3、AI workload testing 与 UET testing。https://www.prnewswire.com/news-releases/viavi-to-showcase-end-to-end-data-center-testing-portfolio-enabling-scale-up-scale-out-and-scale-across-to-1-6t-and-beyond-at-ecoc-2026--302870209.html
- 为什么重要：AI 集群的互连问题不只表现为 BER 或 link down，也会表现为 tail latency、collective communication stall、fault-tolerance gap 和 GPU utilization loss。测试仪表必须开始模拟 workload，而不是只测物理层。

### ⭐ 国内 NPO/XPO 与外置光源链条继续补齐

- 要点：Ligent 在 CIOE 2026 展示 NPO/XPO、高功率外置光源、1.6T DR4 与 FAST OCS；GIGALIGHT 讨论 socket-based 1.6T NPO 从样机验证到 CPX 标准化的可制造性问题；光迅科技前期展示 12.8T XPO DR 液冷模块。https://www.ligent.com/about/news/175.html  https://www.gigalight.com/news-events/news-10808.html  https://www.accelink.com/lighting_your_dreams/2101916634963804161.html
- 为什么重要：国内供应链已经不只是 pluggable optics，而是在 high-power ELS、NPO/XPO、OCS、液冷光模块和封装连接上快速扩展；但客户规模部署、良率和独立测试仍需谨慎验证。

### ⭐ OCP Global Summit 2026 将成为 ECOC 后的系统级验证窗口

- 要点：OCP Global Summit 2026 将于 10 月 12-15 日在 San Jose 举行，官方主题为 Scaling Innovation for the AI Era；NVIDIA OCP 页面把 keynote 定位为 AI Factories at Scale。https://www.opencompute.org/summit/global-summit  https://www.nvidia.com/en-us/events/ocp-summit/
- 为什么重要：ECOC 证明的是 optical/electrical interface 和产品路线；OCP 更可能把互连放进 rack power、cooling、open hardware management、service workflow 与 AI factory 设计约束中评估。

## 本周关键技术进展 3 篇深读

### 1. 448G/400G lane 时代，modulation 选择必须绑定信道和 FEC

- 背景：AI cluster 从 200G/lane 走向 400G/lane 甚至 448G/lane，electrical I/O 与 optical front-end 的带宽、损耗、DSP 功耗和封装寄生同时收紧。
- 本周证据：Marvell 展示 2nm 400G/lane optical PAM4，Nokia 展示 448G per lane preview，arXiv:2609.24570 则把 PAM4/PAM6/PAM8 和 MLSE 放到 net 400G GPU cluster 场景。https://www.marvell.com/company/newsroom/marvell-industry-first-2nm-optical-technology-ai-data-center-infrastructure-ecoc-2026.html  https://www.nokia.com/events/nokia-at-ecoc/  https://arxiv.org/abs/2609.24570
- 观察指标：公开 demo 是否给出信道条件、FEC 目标、equalizer 复杂度、功耗、thermal budget 和误码统计；只给 lane rate 的宣传不足以判断可部署性。

### 2. CPO/NPO/CPX 的成败将越来越取决于封装与可维护性

- 背景：把 optics 靠近 switch ASIC 或 accelerator package 可以缩短 electrical reach、降低 I/O 功耗，但会把激光源、连接器、热耦合和现场维护推到系统边界。
- 本周证据：Ciena Vesta 200 6.4T CPX、Lumentum DWDM ELSFP、Lightmatter Passage L20 CPX BiDi、Furukawa/Lightera Snap-Beam connector 分别从 optical engine、external laser、fiber count 和 detachable connector 切入。https://www.ciena.com/about/newsroom/press-releases/ciena-highlights-high-performance-ai-networking-at-ecoc-2026  https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx  https://lightmatter.co/press-release/lightmatter-joins-open-cpx-msa-introduces-the-industrys-first-bidirectional-cpx-optical-engine/  https://lightera.com/n/furukawa-electric-and-lighteras-snap-beam-connector-for-co-packaged-optics-wins-ecoc-fibre-infrastructure-innovation-award-2026/
- 观察指标：serviceable laser、detachable fiber attach、module replacement time、cleaning workflow、liquid cooling interference、monitoring interface 和 field failure rate 会比单次 demo 更重要。

### 3. AI optical interconnect 的价值必须绑定 workload 和 operations

- 背景：LLM serving、long-context prefill、MoE training 和 multi-tenant inference 对互连的要求不同；同样的带宽在不同 workload 中可能转化为完全不同的 TTFT、tokens/watt 和 GPU utilization。
- 本周证据：arXiv:2609.01821 研究 high-radix photonic interconnects 对 inference prefill 的影响；arXiv:2608.23145 把多智能体 LLM 用到 million-scale optical link management；VIAVI 的 1.6T testing portfolio 也开始强调 workload testing。https://arxiv.org/abs/2609.01821  https://arxiv.org/abs/2608.23145  https://www.prnewswire.com/news-releases/viavi-to-showcase-end-to-end-data-center-testing-portfolio-enabling-scale-up-scale-out-and-scale-across-to-1-6t-and-beyond-at-ecoc-2026--302870209.html
- 观察指标：报告和产品发布应尽量说明 workload、topology、failure model、latency distribution、telemetry granularity 和 operational loop；没有 workload 假设的 bandwidth-per-watt 结论需要打折。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| OIF | ECOC 2026 展示 CEI-448G/224G、CMIS、Co-Packaging、EEI 等互操作 | 标准互操作、AI-era networking | https://www.oiforum.com/oif-brings-industry-wide-interoperability-to-life-at-ecoc-2026-accelerating-scalable-efficient-networks-for-the-ai-era/ |
| Ethernet Alliance | 1.6T multi-vendor demo，强调 AI demand 与 IEEE P802.3dj | 1.6T Ethernet、224G optics、lossless fabric | https://ethernetalliance.org/blog/2026/09/09/1-6t-ethernet-moves-closer-to-reality-in-ethernet-alliances-ecoc-2026-demo/ |
| Marvell | 2nm optical interconnect demos 与 102.4T CPO platform | 400G/lane、coherent-lite、CPO | https://www.marvell.com/company/newsroom/marvell-industry-first-2nm-optical-technology-ai-data-center-infrastructure-ecoc-2026.html |
| Ciena | Vesta 200 6.4T CPX、CPO、liquid cooling demo | Open CPX、AI scale-up/scale-out | https://www.ciena.com/about/newsroom/press-releases/ciena-highlights-high-performance-ai-networking-at-ecoc-2026 |
| Lumentum | Eight-wavelength DWDM ELSFP laser module for OCI MSA | External laser source、CPO/NPO maintainability | https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx |
| Lightmatter | Passage L20 CPX BiDi optical engine | BiDi、Open CPX、fiber count reduction | https://lightmatter.co/press-release/lightmatter-joins-open-cpx-msa-introduces-the-industrys-first-bidirectional-cpx-optical-engine/ |
| Furukawa/Lightera | Snap-Beam connector 获 ECOC Fibre Infrastructure Innovation Award | PIC connector、CPO serviceability | https://lightera.com/n/furukawa-electric-and-lighteras-snap-beam-connector-for-co-packaged-optics-wins-ecoc-fibre-infrastructure-innovation-award-2026/ |
| Nokia | 1.6T LPO、448G per lane preview、hybrid SiPh+TFLN front-end | LPO、TFLN、3.2T optics path | https://www.nokia.com/events/nokia-at-ecoc/ |
| VIAVI | 1.6T L0-L3、AI workload、UET、CPO/SiPh test portfolio | Test/validation、deployment readiness | https://www.prnewswire.com/news-releases/viavi-to-showcase-end-to-end-data-center-testing-portfolio-enabling-scale-up-scale-out-and-scale-across-to-1-6t-and-beyond-at-ecoc-2026--302870209.html |
| Ligent | NPO/XPO、高功率外置光源、1.6T DR4、FAST OCS | 国内 AI optical interconnect chain | https://www.ligent.com/about/news/175.html |
| GIGALIGHT | Socket-based 1.6T NPO 与 CPX 标准化讨论 | NPO manufacturability、field deployment | https://www.gigalight.com/news-events/news-10808.html |
| OCP | 2026 Global Summit 将于 10 月 12-15 日举行 | Open AI infrastructure、rack/power/cooling | https://www.opencompute.org/summit/global-summit |

## 趋势观察

- **互操作证据比峰值速率更重要。** 1.6T/3.2T optics 和 448G/400G lane 必须和 CMIS、FEC、link training、thermal telemetry、test instruments 一起验证。https://www.oiforum.com/oif-brings-industry-wide-interoperability-to-life-at-ecoc-2026-accelerating-scalable-efficient-networks-for-the-ai-era/
- **CPO/NPO 的短板正在从“能否集成”转到“能否维护”。** External laser、detachable connector、BiDi fiber reduction 和 liquid cooling compatibility 会成为客户评估重点。https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-to-Demonstrate-DWDM-ELSFP-Laser-Module-for-OCI-MSA-Applications-at-ECOC-2026/default.aspx
- **Optical interconnect 需要 workload proof。** Long-context prefill、MoE training、KV cache、collective communication 和 failure recovery 会决定光互连收益是否能体现在 GPU utilization 和 TTFT 上。https://arxiv.org/abs/2609.01821
- **国内供应链正在向 NPO/XPO/ELS/OCS 上游延伸。** 这有助于摆脱单一 pluggable optics 竞争，但公开客户验证和批量良率仍是关键缺口。https://www.ligent.com/about/news/175.html
- **OCP 将把光互连拉回 rack-scale 现实。** 电源、液冷、open rack、hardware management、安全和运维流程，会反向限制 optical I/O 的采用节奏。https://www.opencompute.org/summit/global-summit

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | Open AI infrastructure、rack power、cooling、management | https://www.opencompute.org/summit/global-summit |
| NVIDIA at OCP 2026 | 2026-10-12 至 2026-10-15 | AI Factories at Scale、open infrastructure、networking | https://www.nvidia.com/en-us/events/ocp-summit/ |
| Ciena at OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | Vesta 200 6.4T CPX、scale-across connectivity | https://www.ciena.com/events/open-compute-project |
| Marvell Investor Day 2026 | 2026-10-06 | AI infrastructure portfolio、connectivity/storage roadmap | https://investor.marvell.com/ |
| SC26 | 2026-11-15 至 2026-11-20 | HPC/AI networking、large-scale systems、scientific workflows | https://sc26.supercomputing.org/attendees/ |

## 📱 分享卡片

- W40 主线：ECOC 把 AI optics 推到系统验证阶段，OCP 会把它推到 rack-scale 运维阶段。https://www.opencompute.org/summit/global-summit
- 1.6T/3.2T 不是一个模块问题，而是 SerDes、CMIS、connector、laser source、thermal、test automation 和 workload 的共同问题。https://ethernetalliance.org/blog/2026/09/09/1-6t-ethernet-moves-closer-to-reality-in-ethernet-alliances-ecoc-2026-demo/
- CPO/NPO 进入“可服务性考场”：external laser、detachable connector、BiDi 和 liquid cooling 会决定部署边界。https://lightera.com/n/furukawa-electric-and-lighteras-snap-beam-connector-for-co-packaged-optics-wins-ecoc-fibre-infrastructure-innovation-award-2026/
- 400G/lane 的调制路线还没有定论，PAM4/PAM6/PAM8 要跟信道、FEC 和 equalizer 成本一起看。https://arxiv.org/abs/2609.24570
- 保守判断：当前公开证据仍以 demo、互操作、论文和会议议程为主，暂无足够独立评测支撑“CPO/NPO 已大规模替代 pluggable”的结论。https://www.ecocexhibition.com/

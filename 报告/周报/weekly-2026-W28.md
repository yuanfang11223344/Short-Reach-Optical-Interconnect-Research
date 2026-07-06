# 芯片互连与AI基础设施 每周综述 2026-W28

> 覆盖周期：2026-07-06 至 2026-07-12。本周周报在周一生成，先纳入 7月6日日报，再补充标准、产品、论文、国内厂商与基础设施六个方向。后续日报继续记录本周增量。

## 本周最重要的 8 件事

1. 🔥 **OIF CEI-448G-VSR/LR 进入项目化。** 448G electrical I/O 已分别面向 chip-to-module 与 backplane 定义接口边界。重要性在于 ADC/DAC、DSP、clock、package 和 test 将同时跨代。[OIF](https://www.oiforum.com/technical-work/current-work/)
2. 🔥 **P802.3dj 进入 7月 plenary 前的 200G/lane 规范收敛。** TDECQ、reference equalizer、COM 和 D3.x comments 成为重点，224G SerDes 进入系统一致性验证阶段。[IEEE](https://ieee802.org/3/dj/public/adhoc/optics/index.html)
3. 🔥 **400G/lane optical DSP 进入产品周期。** Broadcom Taurus 用 8:4 架构连接 1.6T 与 3.2T module，意味着 3.2T 不再只是 PIC 演示。[Broadcom](https://investors.broadcom.com/news-releases/news-release-details/broadcom-delivers-industrys-first-400glane-optical-dsp-next)
4. 🔥 **UALink 2.0 把 In-Network Compute 引入开放 scale-up fabric。** reduction、aggregation、synchronization 和 collective 可由网络参与执行，switch ASIC 从 forwarding 上移到 computation-aware fabric。[UALink](https://ualinkconsortium.org/blog/exploring-in-network-compute-how-ualink-is-redefining-ai-scale-up-architecture-1509/)
5. 🔥 **Spectrum-X Ethernet Photonics 将 CPO 纳入 Rubin 平台。** CPO 的首批规模化验证由 switch ASIC、optical engine、network OS、运维和供应链共同完成。[NVIDIA](https://nvidianews.nvidia.com/news/rubin-platform-ai-supercomputer)
6. ⭐ **3.2T photonics 形成多材料路线竞争。** SOH PIC、InP-on-silicon modulator、heterogeneous SiPh 与 socketed CPO 同时推进，尚未形成单一路线垄断。[NLM](https://www.ofcconference.org/news-media/exhibitor-news/nlm-photonics-initiates-sampling-of-1-6t-and-3-2t-silicon-organic-hybrid-pics/)
7. ⭐ **国内厂商路线从 1.6T 扩展到 3.2T、6.4T NPO、12.8T XPO 与 OCS。** 这反映传统 module 厂商正向 optical engine 和系统互连扩展，但当前仍应区分研发规划与量产。[巨潮资讯](https://static.cninfo.com.cn/finalpage/2026-03-31/1225056493.PDF)
8. 🔥 **AI data center 供电边界上移到 facility DC 与中压侧。** 高变比 DC/DC、LVDC、medium-voltage SST 和 liquid cooling 需要与 workload transient 联合建模。[arXiv:2606.25095](https://arxiv.org/abs/2606.25095)

## 本周关键技术进展（3篇深读）

### 1. 224G 产品化与 448G 架构预研进入长期重叠

**背景：** P802.3dj 正把 200G/lane Ethernet 从 baseline 推向 ballot 和 compliance；与此同时，OIF 已启动 CEI-448G-VSR/LR。

**新进展：** 近期 P802.3dj 材料集中处理 TDECQ、equalizer 和 COM，OIF Current Work 则明确 448G chip-to-module/backplane 两类项目。来源：https://ieee802.org/3/dj/public/adhoc/optics/index.html ，https://www.oiforum.com/technical-work/current-work/

**产业链影响：** SerDes IP、package、connector、retimer 和测试厂商需要同时服务 224G 量产与 448G channel exploration。可复用的 ADC/DAC、clocking 和 DSP 架构将成为研发效率关键。

**未来1-2年：** 224G 进入 interoperability 和高容量部署，448G 先在 modulation、reach、DSP power 与 package feasibility 上分化，两代不会简单串行替换。

### 2. CPO 从 optical engine 演示走向平台闭环

**背景：** Pluggable 1.6T 仍有成熟供应链和可维护性优势，但 switch I/O power 与 radix 推动 optics 向 ASIC 靠近。

**新进展：** NVIDIA 把 Spectrum-X Ethernet Photonics 纳入 Rubin；Coherent 展示 socketed CPO 与 ELS；NLM 推进 SOH PIC sampling。来源：https://nvidianews.nvidia.com/news/rubin-platform-ai-supercomputer ，https://www.coherent.com/news/press-releases/coherent-co-packaged-optics-cpo-technologies-ofc-2026 ，https://www.ofcconference.org/news-media/exhibitor-news/nlm-photonics-initiates-sampling-of-1-6t-and-3-2t-silicon-organic-hybrid-pics/

**产业链影响：** Switch ASIC 厂商获得更强的平台整合权；module 厂商向 optical engine、ELS、fiber attach、NPO/LPO 和测试迁移；foundry 与 advanced packaging 成为核心瓶颈。

**未来1-2年：** CPO 将先在高 radix、封闭生态和功耗敏感场景扩张，pluggable/NPO 继续服务通用部署。可靠性、可更换 laser 与 field failure data 比单次带宽 demo 更关键。

### 3. Scale-up fabric 从“搬数据”转向“参与计算”

**背景：** 大模型训练和推理的 collective communication 已成为 accelerator utilization 的关键约束，仅增加 lane rate 无法解决同步和拥塞问题。

**新进展：** UALink Common 2.0 引入 In-Network Compute，并配套 management、chiplet 与 200G DL/PL specification。来源：https://ualinkconsortium.org/specification/ ，https://ualinkconsortium.org/news/statements-of-support-for-the-ualink-2-0-specification/

**产业链影响：** Switch pipeline 需要支持 reduction/aggregation，endpoint 与 collective library 需要协同；manageability、precision、fault isolation 和 security IP 会成为新验证面。

**未来1-2年：** UALink、NVLink 与其他 scale-up fabric 的竞争将从 raw bandwidth 延伸到 collective efficiency、memory semantics、RAS、telemetry 和软件生态。

## 厂商动态汇总

| 厂商 | 本周动作/状态 | 影响方向 | 链接 |
|---|---|---|---|
| Broadcom | Taurus 400G/lane optical DSP | 1.6T/3.2T DSP | https://investors.broadcom.com/news-releases/news-release-details/broadcom-delivers-industrys-first-400glane-optical-dsp-next |
| Marvell | 持续扩展 1.6T DSP、SerDes、driver/TIA 与 telemetry 平台 | optical connectivity | https://www.marvell.com/company/newsroom/marvell-1-6t-optical-dsp-ai-data-center-connectivity.html |
| Credo | 224G multiprotocol retimer 面向 UALink/ESUN/Ethernet | scale-up PHY | https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx |
| Synopsys | 224G 与 security IP 支持 UALink 2.0 | interface IP | https://ualinkconsortium.org/news/statements-of-support-for-the-ualink-2-0-specification/ |
| Cadence | 持续跟踪 2nm/3D-IC、SerDes 与 chip-package-system analysis | EDA/system signoff | https://www.cadence.com/en_US/home/tools/system-analysis.html |
| NVIDIA | Rubin 与 Spectrum-X Ethernet Photonics 共同推进 | rack-scale/CPO | https://nvidianews.nvidia.com/news/rubin-platform-ai-supercomputer |
| Coherent | 6.4T socketed CPO、ELS、VCSEL 与 InP modulator | optical engine | https://www.coherent.com/news/press-releases/coherent-co-packaged-optics-cpo-technologies-ofc-2026 |
| NLM Photonics | 1.6T/3.2T SOH PIC sampling | high-speed PIC | https://www.ofcconference.org/news-media/exhibitor-news/nlm-photonics-initiates-sampling-of-1-6t-and-3-2t-silicon-organic-hybrid-pics/ |
| 中际旭创（国内） | 规划 3.2T、6.4T NPO、12.8T XPO 与 OCS | module/NPO/XPO | https://static.cninfo.com.cn/finalpage/2026-03-31/1225056493.PDF |
| GIGALIGHT（国内） | 1.6T DR16 NPO linear SiPh engine | NPO/linear optics | https://www.gigalight.com/news-events/news-10133.html |

## 趋势观察

1. **SerDes 代际开始并行而非串行。** 224G 的 test correlation、package model 与 DSP adaptation 将直接成为 448G 的初始设计约束。来源：https://www.oiforum.com/technical-work/current-work/
2. **CPO 的护城河是平台闭环，不是单一 PIC。** NVIDIA、Coherent 与 NLM 的进展分别对应系统、封装/光源和调制材料，量产必须把三层同时闭合。来源：https://nvidianews.nvidia.com/news/rubin-platform-ai-supercomputer
3. **AI 基础设施正在形成“计算-网络-电力”联合调度。** In-Network Compute 优化通信，facility DC 与 grid-aware workload 优化供电，两者最终会在 distributed scheduler 层汇合。来源：https://ualinkconsortium.org/specification/ ，https://arxiv.org/abs/2606.25095

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| Optica Advanced Photonics Congress postdeadline 截止 | 2026-07-07 | silicon photonics 与 late-breaking work | https://www.optica.org/events/congress/advanced_photonics_congress/ |
| IEEE P802.3dj July Session | 2026-07-13 至 07-16 | D3.x comments、200G/lane、1.6TbE | https://ieee802.org/3/dj/public/index.html |
| P802.3dj contingent meetings | 2026-07-21 至 07-23 | plenary 遗留议题 | https://ieee802.org/3/dj/public/index.html |
| UALink 2.0 ecosystem | 持续跟踪 | INC、manageability、chiplet、compliance | https://ualinkconsortium.org/specification/ |

## 📱 分享卡片

1. 🔥 **224G 正在产品化，448G 已项目化：** 两代 SerDes 将长期并行。https://www.oiforum.com/technical-work/current-work/
2. 🔥 **400G/lane DSP 已进入产品周期：** 3.2T 不再只是 photonics demo。https://investors.broadcom.com/news-releases/news-release-details/broadcom-delivers-industrys-first-400glane-optical-dsp-next
3. 🔥 **UALink 2.0 让网络开始参与计算：** collective offload 将改变 switch 与 accelerator 分工。https://ualinkconsortium.org/specification/
4. 🔥 **CPO 的量产门槛是系统闭环：** ASIC、optics、ELS、packaging 与运维必须共同成熟。https://nvidianews.nvidia.com/news/rubin-platform-ai-supercomputer
5. ⭐ **AI data center 的电力设计已上移到中压侧：** 供电拓扑成为计算平台变量。https://arxiv.org/abs/2606.25095

# 芯片互连与AI基础设施周报｜2026-W43

> 周期：2026-10-19—10-25；周一开篇版，截点为 10 月 19 日，不预写本周尚未发生事件。已读取并纳入当日日报全部 🔥 / ⭐ 条目，以 OCP 上周公告作背景展开本周跟踪。以下“本周重要”指本周研究优先级，不表示全部于本周发布。

## 本周最重要的 5-8 件事

### 🔥 1. 开放机架 CPO 进入系统验证

Lightmatter/Flex 的 10 月 12 日公告提供 CPO 交换托盘生产验证平台。本周优先关注验证报告、接口约束及维护边界；尚不能据此确认规模部署。

来源：[原始资料](https://lightmatter.com/press-release/lightmatter-delivers-open-rack-cpo-switch-and-xpu-scale-up-server-through-independent-collaborations-with-flex-and-other-industry-partners/)。

### 🔥 2. PCIe-over-optics 联合展示连接多个供应链环节

10 月 12 日的 Lumentum/Astera/Corning 公告组合交换、VCSEL 与多模光纤。下一项证据应是链路恢复及运行条件，而非演示名称。

来源：[原始资料](https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Astera-Labs-and-Corning-to-Demonstrate-1060-nm-VCSEL-Based-PCIe-over-Optics-for-AI-Rack-Scale-Connectivity-at-the-2026-OCP-Global-Summit/default.aspx)。

### 🔥 3. MGX 扩展开放机架协作基础

NVIDIA 在 10 月 12 日贡献 Vera Rubin 机架与托盘设计。研究应核对具体设计范围和版本，不将系统设计开放扩大解释为芯片 IP 开放。

来源：[原始资料](https://blogs.nvidia.com/blog/ocp-global-summit-vera-rubin-scale-ai-factories/)。

### ⭐ 4. 224G/448G 与电力、冷却协同

立讯 OCP 材料同时展示高速电光互连、液冷和机架架构。国内供应链的跟踪重点是系统接口与可维护性，未经验证的系统收益不予量化。

来源：[原始资料](https://en.luxshare-tech.com/company/resources/news/luxshare-tech-ocp-2026.html)。

### ⭐ 5. 光子平台需要五类接口共同成熟

Lightmatter/Dell/Flex 议程覆盖平台约束及光路测试。本周重点寻找机械、电力、高速信号、热与管理接口资料，避免仅以封装方式判断成熟度。

来源：[原始资料](https://lightmatter.com/event/2026-ocp-global-summit-2/)。

### ⭐ 6. 重放代价应进入链路性能评价

PREFACE 的 8 月研究用仿真解释残余错误与延迟反馈怎样扩大重放范围。将其作为方法参考，不能把模拟收益写成 UALink 产品性能。

来源：[原始资料](https://arxiv.org/abs/2608.17503)。

### ⭐ 7. 集群评估需包含设施和验证

OCP 22 个轨道显示网络、光学、验证和基础设施的交叉。本周可建立跨层验证清单；这是编辑建议，不是新的资本开支统计。

来源：[原始资料](https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/)。

## 本周关键技术进展 3 篇深读

### 深读一：CPO 从封装技术转向平台工程

**背景与问题：** 光引擎进入托盘或封装邻近位置后，传统前面板模块的空间与维护边界会变化。只有光引擎带宽不足以判断系统是否可部署。

**方法与证据：** 本周继续追踪 Lightmatter/Flex 的开放机架生产验证系统；结合官方议程提出的五类接口，检查光纤路径、供电、热环境和管理可见性。公告证明其公开提出并展示了系统形态，不提供独立长期运维结论。

**工程解读：** 验证平台能帮助供应链暴露边界问题，但生产验证不等于批量出货。建议后续比较相同负载下的系统功耗、故障隔离和维修时间；本期不补写这些未披露数值。

来源：[原始资料](https://lightmatter.com/press-release/lightmatter-delivers-open-rack-cpo-switch-and-xpu-scale-up-server-through-independent-collaborations-with-flex-and-other-industry-partners/)。
平台接口依据：

来源：[原始资料](https://lightmatter.com/event/2026-ocp-global-summit-2/)。

### 深读二：PCIe 光化要保留协议语义

**背景与问题：** 光链路延伸物理连接时，协议对时延、错误处理及恢复的约束仍需满足。模块能够发光并不能独立证明完整系统行为。

**方法与证据：** 联合公告把 Scorpio Smart Fabric Switch、1060 nm VCSEL 与 Corning 多模光纤放在同一机架演示中，给出了交换、收发与布线协作样本。

**工程解读：** 后续应逐项核验链路距离、温度范围、错误注入、重训练和设备枚举行为，并区分单链路测试与多设备压力场景。本期没有足够公开材料给出光铜统一条件对比，也不推定商业部署。

来源：[原始资料](https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Astera-Labs-and-Corning-to-Demonstrate-1060-nm-VCSEL-Based-PCIe-over-Optics-for-AI-Rack-Scale-Connectivity-at-the-2026-OCP-Global-Summit/default.aspx)。

### 深读三：FEC 与在途流量为何需要共同控制

**背景与问题：** 残余误码经反馈返回前，发送端仍可能注入后续 flit，导致一次损坏扩展为更多重传。仅加强纠错不一定消除延迟反馈成本。

**方法与证据：** PREFACE（arXiv:2608.17503，2026-08-18）利用纠正符号观测构建两状态 Bayesian filter，联合选择 FEC 强度与 outstanding-flit 上限；作者使用 ns-3 和公开 UALink 重放语义评估。

**适用边界：** 这是相关突发误码条件下的仿真研究。落地需检查观测可获得性、控制器延迟、误码统计稳定性及吞吐限制。本文未独立复现，不转述为已商用能力。

**本周行动：** 将 goodput、尾时延、重传量与链路速率分别记录，避免以原始带宽替代应用效率。

来源：[原始资料](https://arxiv.org/abs/2608.17503)。

## 厂商动态汇总

| 厂商/生态 | 已核实动态 | 本周待核验 | 原始来源 |
|---|---|---|---|
| Lightmatter / Flex | CPO 托盘生产验证系统 | 长期可靠性和维护流程 | [官方资料](https://lightmatter.com/press-release/lightmatter-delivers-open-rack-cpo-switch-and-xpu-scale-up-server-through-independent-collaborations-with-flex-and-other-industry-partners/) |
| Lumentum / Astera / Corning | PCIe-over-optics 联合展示公告 | 多设备和异常恢复行为 | [官方资料](https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Astera-Labs-and-Corning-to-Demonstrate-1060-nm-VCSEL-Based-PCIe-over-Optics-for-AI-Rack-Scale-Connectivity-at-the-2026-OCP-Global-Summit/default.aspx) |
| NVIDIA / ODM 生态 | MGX 机架与托盘设计贡献 | 具体规范与兼容验证 | [官方资料](https://blogs.nvidia.com/blog/ocp-global-summit-vera-rubin-scale-ai-factories/) |
| 立讯技术 | 电光、冷却及机架方案展示 | 通道条件与接口互操作 | [官方资料](https://en.luxshare-tech.com/company/resources/news/luxshare-tech-ocp-2026.html) |

## 趋势观察

1. **平台标准化比单一器件速率更接近系统落地问题。** 五类接口帮助供应商确定职责边界；这是从议程提炼的工程判断，尚不表示最终规范已经完成。

来源：[原始资料](https://lightmatter.com/event/2026-ocp-global-summit-2/)。

2. **光化路线会并存。** CPO 系统与 VCSEL PCIe 展示针对不同集成边界，不能从两份公告推断赢家。评价应回到协议、距离、成本和维护条件。

来源：[原始资料](https://investor.lumentum.com/financial-news-releases/news-details/2026/Lumentum-Astera-Labs-and-Corning-to-Demonstrate-1060-nm-VCSEL-Based-PCIe-over-Optics-for-AI-Rack-Scale-Connectivity-at-the-2026-OCP-Global-Summit/default.aspx)。

3. **算法增益必须保留实验条件。** 直接检测光互连论文 arXiv:2608.28129（2026-08-28）的部分实验为 40 Gb/s、10 km；这与目标高速机架链路不同。需要同时看复杂度与硬件约束。

来源：[原始资料](https://arxiv.org/abs/2608.28129)。

4. **发布日与传播日必须分开。** “19 家企业白皮书”原公告为 8 月 13 日，Q4 规范提交是当时计划；近期讨论不能作为 10 月新发布或规范完成的依据。

来源：[原始资料](https://lightmatter.co/press-release/industry-leaders-formally-launch-cpo-system-architecture-initiative-within-the-open-compute-project/)。

## 下周关注

以下为 10 月 26 日—11 月 1 日的编辑跟踪清单，不是已确认的发布日程。

- 查看 OCP 会后资料是否补充测试方法和可下载规范；没有新增证据则保留当前成熟度判断。

来源：[原始资料](https://www.opencompute.org/news/explore-22-tracks-at-the-2026-ocp-global-summit/)。

- 查看 Open Silicon Photonics 是否发布有版本号的规范提交材料，区别“计划提交”“已提交”和“通过”。

来源：[原始资料](https://lightmatter.co/press-release/industry-leaders-formally-launch-cpo-system-architecture-initiative-within-the-open-compute-project/)。

- 持续跟踪 SC26 官方 program 与集群网络资料，为系统性能研究补充工作负载视角。

来源：[原始资料](https://sc26.supercomputing.org/)。

## 分享卡片

**本周关键词：系统验证。** CPO 托盘、PCIe 光链路和开放机架设计，都在把器件议题扩展到系统集成。读公告时分别标注“展示、验证、规范、部署”，能避免把技术方向误读成商业落地。

来源：[原始资料](https://lightmatter.com/press-release/lightmatter-delivers-open-rack-cpo-switch-and-xpu-scale-up-server-through-independent-collaborations-with-flex-and-other-industry-partners/)。

## 编制与核验说明

检索方向：SerDes、光互连、AI 机架、基础设施、论文、国内外厂商及会议。去重原始 URL：10 个。检索核验日期为 2026-10-19（Asia/Shanghai）；未确认当天新增的高相关论文，研究回看明确保留原日期。公告、展示与计划均不作量产或独立评测证据。

# 芯片互连与AI基础设施周报｜2026-W44

> 周期：2026-10-26—11-01｜周初版，核验日期 2026-10-26（Asia/Shanghai）。本周尚未结束，本文是本周重点跟踪基线，包含明确注明日期的近期回顾，不预写未来成果。已读取并纳入 10 月 26 日日报全部 🔥/⭐ 条目。7 件重点、3 篇技术深读、11 个去重来源 URL。

## 本周最重要的 7 件事

### 1. 🔥 Oracle AI World 进入本周发布窗口

官方活动时间为 10 月 25—28 日 Las Vegas。跟踪优先级应放在正式发布的集群互连、存储、推理架构及服务可用性。议程或合作方名单只说明参与范围，不能证明具体硬件部署。本周新增判断将以官方技术资料为准。

来源：[原始来源](https://www.oracle.com/ai-world/)

### 2. 🔥 DSX POD 把系统集成前移

10 月 21 日技术文章提出将更多 AI 工厂集成工作放到受控制造环境。它改变的是交付与验证流程：网络、电力、冷却和软件更早一起测试。对运营方的意义是重新划分工厂验收与现场验收责任；参考设计本身并不能消除电网接入和场地准备限制。

来源：[原始来源](https://developer.nvidia.com/blog/achieve-productive-ai-capacity-faster-and-more-predictably-with-nvidia-dsx-pod)

### 3. ⭐ USFP 提醒业界重新评估面板与电接口

10 月 12 日 Cisco/NVIDIA 公告把可插拔光互连扩展放在 AI 连接能力背景下。接口形态更新需要连接器、模块和系统生态协同。本周值得跟踪规范与互操作材料，而非仅重复容量口号。暂无足够独立系统测试可证明某一形态对所有拓扑都最优。

来源：[原始来源](https://blogs.cisco.com/news/cisco-and-nvidia-announce-usfp-expanding-the-path-to-ai-connectivity)

### 4. ⭐ 光模块液冷从散热附件变为系统接口问题

10 月 7 日 Stäubli/CoolIT 公告展示 Mini QD 与 CP-OSFP 冷板的组合，强调维护能力。液冷进入网络模块后，维修流程和流体连接可靠性会影响可用性。应把模块更换、故障隔离与冷却回路维护放入同一验收方案。该信息为厂商方案说明。

来源：[原始来源](https://www.staubli.com/us/en/news/global/2026/coolit-ciena-optic-liquid-cooling-press-release.html)

### 5. ⭐ 自由空间互连提出通道扩展路径

10 月 22 日 arXiv:2610.30757 报告九通道原理验证，100 Tbps 来自扩展模型。其价值在于探索可重构空间通道和串扰优化，不能解读为 100 Tbps 产品发布。下面的深读列出研究边界和后续验证问题。

来源：[原始来源](https://arxiv.org/abs/2610.30757)

### 6. ⭐ 光 KV Cache 网络把交换延迟纳入推理调度

arXiv:2610.18444 的 10 月 18 日修订版利用 prefill 提前预约光路。研究把网络重配置与应用执行阶段关联，是对“只追求更快交换硬件”的有益补充；收益仍需真实负载下的尾延迟、并发冲突和成本假设支持。

来源：[原始来源](https://arxiv.org/abs/2610.18444)

### 7. 📌 机架交付与设施能效需分别验收

Lenovo 10 月 12 日页面给出 Vera Rubin NVL72 全球出货的厂商表述；NVIDIA 10 月 21 日 DSX 公告给出最高节电幅度与采用计划。两者分别属于供应状态和效率主张，不能合并成某客户已达到目标能效的证据。后续应索取配置、负载、计量边界和生产验收结果。

来源：[原始来源](https://lenovopress.lenovo.com/lp2549-lenovo-brings-the-full-nvidia-vera-rubin-platform-to-ai-cloud-providers)

来源：[原始来源](https://nvidianews.nvidia.com/news/european-ecosystem-builds-worlds-most-efficient-ai-factories-with-nvidia-dsx/)

## 本周关键技术进展 3 篇深读

以下为本周精选研究，原始提交日期均早于本周；不是本周新发表清单。三篇均为预印本，暂无独立评测。

### 深读一：Reconfigurable Free-Space Optical Interconnects

**研究问题：** 空间光通道数量增长会放大串扰和光束控制难题，单纯堆叠通道不能保证有效吞吐。

**方法与证据：** arXiv:2610.30757（10 月 22 日）采用 piston-motion micromirror array，同时优化九个通道；作者报告平均最坏串扰 -21.7 dB，并研究通道间距、同时照明及输出数量。超过一万通道、100 Tbps 是模型推演，需与九通道实验分开呈现。

**工程解读：** 该结果为可重构空间光互连提供原理验证。要判断机架级适用性，仍应关注对准稳定性、温度扰动、校准开销及封装后的误码；这些是本报告提出的验证问题，并非论文已经证明的缺陷或优势。

**下一步证据：** 更大通道阵列的实测、完整链路预算、重配置过程中的误码及可靠性测试，比单独扩大理论容量更关键。

来源：[原始来源](https://arxiv.org/abs/2610.30757)

### 深读二：An Optical KV Cache Network for Disaggregated LLM Serving

**研究问题：** 分离式 prefill/decode 需要转移 KV Cache，网络拥塞会增加 TTFT；机械 OCS 的重配置延迟又难以直接匹配请求级流量。

**方法与证据：** arXiv:2610.18444（10 月 13 日提交、18 日修订）在 prefill 尚在计算时预留电路，并用 WDM 连接 GPU 与 OCS。作者以真实服务轨迹及 H100 prefill 测量驱动集群仿真，报告能够容忍 384 端口 OCS 的 50 ms 重配置；其成本模型给出相对 2:1 packet fabric 的 0.55—0.78 倍成本。

**边界：** 测得 prefill 时间不等于整套集群实测，成本比较也依赖模型假设。不能据此直接推导生产部署的节省比例。

**工程解读与复现重点：** 分别检查长上下文、短 prefill 和突发到达负载，观察预约冲突、GPU 空闲与 TTFT 高分位数。只有平均吞吐相近不足以证明在线服务质量达标。

来源：[原始来源](https://arxiv.org/abs/2610.18444)

### 深读三：Capturing Electrical Windows Through Reconfigurable Optical Networks

**研究问题：** 跨地域调度若仅依据电价和可再生能源窗口安排训练，会忽略 checkpoint 不能及时传到目标站点的约束。

**方法与证据：** arXiv:2610.13061（10 月 9 日）联合计算放置、电力与光网络调度，以估计传输延迟生成候选方案，再检查共享链路容量并修正不可行计划。作者在五个 AIDC、相同完成工作量和网络资源的基准下，相对静态光网络报告实时购电成本下降 12.50%、本地可再生能源利用率提高 2.724 个百分点。

**边界：** 这是限定基准与基线的结果，不是跨区域商业运营实测，也不是设施总成本下降 12.50%。

**工程解读与复现重点：** 需检查 checkpoint 大小、网络争用、预测误差及迁移频率。网络带宽不足时，便宜电价不一定能转化为可执行的算力迁移；评估应同时展示完成工作量与服务约束。

来源：[原始来源](https://arxiv.org/abs/2610.13061)

## 厂商动态汇总

| 厂商/生态 | 公开进展 | 证据性质与下一步 |
|---|---|---|
| Cisco / NVIDIA | USFP 可插拔光互连形态 | 公告；跟进接口规范和互操作验证。[来源](https://blogs.cisco.com/news/cisco-and-nvidia-announce-usfp-expanding-the-path-to-ai-connectivity) |
| CoolIT / Stäubli / Ciena | 光模块 Direct-to-Plug 液冷 | 厂商方案；跟进维护与可靠性测试。[来源](https://www.staubli.com/us/en/news/global/2026/coolit-ciena-optic-liquid-cooling-press-release.html) |
| Lenovo | Vera Rubin NVL72 整机架方案 | 厂商页面称全球出货；客户规模未独立核实。[来源](https://lenovopress.lenovo.com/lp2549-lenovo-brings-the-full-nvidia-vera-rubin-platform-to-ai-cloud-providers) |
| NVIDIA DSX | 工厂预制集成与设施能效工具 | 技术文章与厂商声明；生产验收仍需现场数据。[来源](https://developer.nvidia.com/blog/achieve-productive-ai-capacity-faster-and-more-predictably-with-nvidia-dsx-pod) |
| 立讯 | OCP 高速铜互连、XPO 与液冷 I/O 展示 | 展示计划回顾；不推断量产或客户采用。[来源](https://en.luxshare-tech.com/company/resources/news/luxshare-tech-ocp-2026.html) |

## 趋势观察

1. **互连收益越来越依赖系统约束。** USFP 与模块液冷分别涉及电接口和热接口，不能只按端口标称容量排序。此为本报告对两项公告的综合分析。[USFP](https://blogs.cisco.com/news/cisco-and-nvidia-announce-usfp-expanding-the-path-to-ai-connectivity)、[液冷](https://www.staubli.com/us/en/news/global/2026/coolit-ciena-optic-liquid-cooling-press-release.html)。
2. **调度可改变光网络的适用范围。** KV Cache 预约利用计算阶段隐藏重配置，跨站训练调度则把传输延迟纳入用电计划；两者都提示需要应用、网络联合评估，但目前证据强度仍以论文模型为主。[KV Cache](https://arxiv.org/abs/2610.18444)、[跨站调度](https://arxiv.org/abs/2610.13061)。
3. **交付速度与运行效率是两类指标。** DSX POD 讨论集成流程，DSX 能效公告讨论运营；项目应分别设立交付验收与运行期计量，不能互相替代。[交付](https://developer.nvidia.com/blog/achieve-productive-ai-capacity-faster-and-more-predictably-with-nvidia-dsx-pod)、[能效](https://nvidianews.nvidia.com/news/european-ecosystem-builds-worlds-most-efficient-ai-factories-with-nvidia-dsx/)。

## 下周关注

> 下周指 11 月 2—8 日；下面是研究跟踪计划，不是已确认的发布日程。

- 复核 Oracle AI World 会后技术资料，区分正式产品、预览服务和未来计划，检查有无可验证的集群网络规格。[活动入口](https://www.oracle.com/ai-world/)
- 跟进三篇论文是否更新正文、代码或评估材料；优先看规模实验、尾延迟及成本敏感性，而非只比较峰值指标。[自由空间](https://arxiv.org/abs/2610.30757)、[KV Cache](https://arxiv.org/abs/2610.18444)、[跨站调度](https://arxiv.org/abs/2610.13061)
- 提前整理 SC26 系统与网络议题。官方会期 11 月 15—20 日，展览 17—19 日；10 月 26 日教程资料截止采用 AoE，并不承诺资料立即公开。[官方日程](https://sc26.supercomputing.org/all-dates-deadlines/)

## 分享卡片

> **W44 周初观察：带宽、热管理、调度和交付正在成为同一个系统问题。**
> - 可插拔光模块液冷：关注维护与可靠性。[来源](https://www.staubli.com/us/en/news/global/2026/coolit-ciena-optic-liquid-cooling-press-release.html)
> - 光互连研究：区分原理实验、仿真与容量外推。[论文](https://arxiv.org/abs/2610.30757)
> - 基础设施：分别验收交付时间和持续运行效率。[来源](https://developer.nvidia.com/blog/achieve-productive-ai-capacity-faster-and-more-predictably-with-nvidia-dsx-pod)
> - 本周发布窗口：Oracle AI World，等待正式技术证据。[来源](https://www.oracle.com/ai-world/)

---
编制说明：本周现有日报仅 10 月 26 日，已纳入全部 🔥/⭐ 条目；近期历史事件均按原日期回顾。全文未把会前议程、厂商采用计划、研究外推写成已验证部署。

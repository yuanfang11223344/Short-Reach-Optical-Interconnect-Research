# 芯片互连与AI基础设施周报｜2026-W45

> 周初综述补报；周范围 11 月 2–8 日，实际核验 11 月 3 日。以已补齐的 11 月 2 日日报 🔥/⭐ 条目为基础，补充近期研究。不是整周事后总结，不纳入周一上午之后的并购公告。

## 本周最重要的 5-8 件事

### 1. ⭐ 224G 电接口：标准项目仍需与正式 IA 区分

OIF 当前工作目录列有 CEI-224G-Linear 与协议无关链路训练项目，覆盖线性光接口以及训练、诊断和故障处理。这里跟踪的是在研项目，不是新发布的定稿规范。工程观察：评估 LPO/NPO 时，应同时核查主机侧电接口和失锁后的恢复能力。

来源：[原始来源](https://www.oiforum.com/technical-work/current-work/)

### 2. 🔥 ACP 光互连议程进入会后材料跟踪

11 月 1 日 workshop 官方议程覆盖 OCI-MSA 实施路径、微环 WDM、异质集成与光源。补报仅确认公开议程，未取得现场测试数据，不能据此认定产品通过互通验证。后续优先核对演示配置、接口版本与链路预算。

来源：[原始来源](https://www.acpconf.com/news/next-generation-ai-optical-interconnects)

### 3. ⭐ 鸿海展示 DSX POD 预集成路径

10 月 30 日官方公告介绍 DSX POD 展示：在工厂预集成 Vera Rubin 机架级基础设施、完成关键验证，运抵后接入已准备好的场地。属于近期展示回看，不能推导客户机房已投运。工程观察：工厂验收和现场复验需分别记录。暂无独立评测。

来源：[原始来源](https://www.honhai.com/en-us/press-center/press-releases/latest-news/2138)

### 4. ⭐ DSX 将供电、冷却和工作负载纳入共同设计

NVIDIA 10 月 21 日公告介绍闭环液冷、干冷器及 MaxLPS、Flex 软件方向，目标是在同等 AI 输出下改善能源利用。属于厂商方案与预期回看；“近零冷却用水”不等于全生命周期零用水，未在本文外推实际节电幅度。暂无独立评测。

来源：[原始来源](https://investor.nvidia.com/news/press-release-details/2026/European-Ecosystem-Builds-Worlds-Most-Efficient-AI-Factories-With-NVIDIA-DSX/default.aspx)

### 5. ⭐ 光学 KV cache 网络：用 prefill 隐藏 OCS 重配置

Seongwon Yoon、Shimeng Yu 的 An Optical KV Cache Network for Disaggregated LLM Serving（arXiv:2610.18444，10 月 13 日提交、18 日修订）提出在 prefill 期间预留光路，使 KV cache 就绪时电路已建立。作者依据实测 prefill 时间和真实服务轨迹进行集群仿真；这不是生产集群实测部署。本次核验摘要，重点关注预测误差和并发预留冲突。暂无独立评测。

来源：[原始来源](https://arxiv.org/abs/2610.18444)

### 6. 🔥 OIF 本周技术会议进入日程窗口

OIF 官方日历列出 Q426 Technical and MA&E Committees Meeting 为 11 月 2–6 日、曼谷。详细材料受会员访问限制，本次没有可核验的表决或规范发布结果。会后跟踪正式 IA 与项目更新。

来源：[原始来源](https://www.oiforum.com/meetings-events/future-quarterly-meetings/)

## 本周关键技术进展 3 篇深读

### 1. 光学 KV cache 网络：调度时间比裸带宽更关键

**背景与问题：** prefill/decode 分离使上下文缓存跨 GPU 搬运；机械 OCS 的重配置时间可能落在首 token 的关键路径。

**方法：** 作者把光路预留提前到 prefill 计算阶段，利用计算与网络控制重叠隐藏等待，每个 GPU 通过 WDM 光链路接入。

**证据边界：** arXiv:2610.18444 是基于真实轨迹和测量输入的仿真研究，本周作为近期论文回看；不能当作量产网络验证。

**工程解读：** 复现应先固定请求长度、突发度和 GPU 配置，再比较 TTFT 尾延迟；若只统计平均吞吐量，可能掩盖光路预约失败的代价。需要额外检查取消请求、重试和热点 decode GPU 的影响。上述是本文提出的验证问题，非作者已完成的实验。


来源：[原始来源](https://arxiv.org/abs/2610.18444)

### 2. 自由空间光互连：二维扩展与封装可行性

**背景与方法：** Jaekwon Lee 等在 Reconfigurable Free-Space Optical Interconnects（arXiv:2610.30757，10 月 22 日）提出用活塞式微镜阵列重构自由空间链路，以二维排布增加通道。

**结果与边界：** 摘要报告九通道同时优化的概念验证；超过一万通道和 100 Tbps 是模型外推，不是已建系统。这里仅依据摘要展开研究问题，未声称完成全文复现。

**工程解读：** 芯片级光束对准、温漂及振动、光源和探测器功耗、控制回路占用需要一起计入。在未给出这些成本前，单纯通道密度不能决定部署优势。下一步应检查阵列面积扩大后的光学误差与故障隔离，区分光学串扰结果和端到端误码率。


来源：[原始来源](https://arxiv.org/abs/2610.30757)

### 3. 跨区域电力窗口：迁移必须算上 checkpoint 传输

**背景与方法：** Capturing Electrical Windows Through Reconfigurable Optical Networks: Transfer-aware Scheduling of Multi-Region AI Data Centers（arXiv:2610.13061，10 月 9 日）联合安排训练位置、checkpoint 搬运和 OCS，反复检查共享链路容量下的传输可行性。

**结果与边界：** 作者在五个 AIDC 的基准场景中比较静态光网络操作，报告购电成本降低 12.50%、本地可再生能源利用率增加 2.724 个百分点；这是论文基准结果，不是电网运营实绩。

**工程解读：** 迁移任务只有在低价或可再生能源窗口结束前恢复训练，才可能获得预期收益。落地还需引入真实带宽竞争、预测误差和恢复开销；不应把局部电价下降直接等同整体成本下降。该论文与 KV cache 研究共同提示：光路控制必须了解业务时间尺度，但两个场景的时延目标不能直接互换。


来源：[原始来源](https://arxiv.org/abs/2610.13061)

## 厂商动态汇总

| 参与方 | 本期证据 | 后续需要核验 |
|---|---|---|
| 鸿海 | DSX POD 展示与工厂预集成方案 | 场地准备、运输后复验、客户验收 |
| NVIDIA | DSX 供电冷却与运行软件公告 | 同等负载下能耗及可靠性 |
| 国内光互连参与者 | ACP 光互连与 AIDC 议程 | 可公开的讲义、器件数据与互通配置 |

来源：[fox](https://www.honhai.com/en-us/press-center/press-releases/latest-news/2138)、[dsx](https://investor.nvidia.com/news/press-release-details/2026/European-Ecosystem-Builds-Worlds-Most-Efficient-AI-Factories-With-NVIDIA-DSX/default.aspx)、[acp](https://www.acpconf.com/news/next-generation-ai-optical-interconnects)、[panel](https://www.acpconf.com/news/467)

## 趋势观察

1. **电光协同从器件延伸到系统。** OIF 项目和 ACP 议程共同指向接口、链路训练和系统集成；这是基于公开议题的分析，尚不能断言某条技术路线获胜。
2. **可重构网络需要业务感知。** 两篇调度研究分别利用 prefill 窗口和跨区域能源窗口；关键是把光路建立时间纳入调度，而不只是提高标称端口速率。
3. **预集成不消除机房工程。** DSX POD 展示强调先准备现场基础设施，快速交付仍受电力、冷却和现场验证约束。

参考：[oif](https://www.oiforum.com/technical-work/current-work/)、[kv](https://arxiv.org/abs/2610.18444)、[energy](https://arxiv.org/abs/2610.13061)、[fox](https://www.honhai.com/en-us/press-center/press-releases/latest-news/2138)

## 下周关注

- 11 月 9–15 日重点跟踪 OIF 11 月 2–6 日会议后的公开文件；不推测会员会议内容。

来源：[原始来源](https://www.oiforum.com/meetings-events/future-quarterly-meetings/)

- SC26 于 11 月 15 日开始，提前梳理网络、系统和部署议程；本周尚未发生的会议不写成已发布成果。

来源：[原始来源](https://sc26.supercomputing.org/all-dates-deadlines/)

- 对 ACP 会后资料，优先找包含测试配置、误码或可靠性条件的材料；如果只有议程，继续保留“议程级证据”的标注。

来源：[原始来源](https://www.acpconf.com/news/next-generation-ai-optical-interconnects)

## 分享卡片

> **W45 周初主线：让光链路的时间、机架的接口、机房的资源互相匹配。**
> 看标准项目是否转为正式文件；看仿真是否走到实测；看工厂预验证是否覆盖现场验收。

参考：[oif](https://www.oiforum.com/technical-work/current-work/)、[kv](https://arxiv.org/abs/2610.18444)、[fox](https://www.honhai.com/en-us/press-center/press-releases/latest-news/2138)

# 芯片互连与 AI 基础设施周报｜2026-W47

> 覆盖 2026-11-16 至 2026-11-22；本周报告在周中补档生成，已纳入 11-16、11-17、11-18 日报的 `🔥` / `⭐` 条目。检索截止 2026-11-18（Asia/Shanghai）。

## 本周最重要的 5 件事

1. 🔥 **200G SerDes 进入 ToR 路线图。** Cisco 将 G302 描述为 51.2T、200G SerDes 的 ToR switching silicon，计划在 2026 年底前向客户出货；这是供货计划而非规模部署。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/cisco-advances-scalability-and-openness-at-ocp-2026.html)
2. ⭐ **USFP 把 400Gb/s-per-lane 推向 pluggable optics 路线。** NVIDIA/Cisco 提出 USFP，首批目标为 OSFP 尺寸内 16 条全双工 lane、最高 12.8Tb/s，并计划推动开放多源规范。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/nvidia-and-cisco-new-pluggable-optics-to-scale-ai-factories.html)
3. **102.4T switch 与 1.6T optics 协同。** Cisco 以 G300、N9000/8000 和 1.6T OSFP 构成 AI network 组合；公开的利用率/完成时间改善为厂商模拟条件下结果。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m02/cisco-announces-new-silicon-one-g300.html)
4. **需求信号来自财务指引而非部署清单。** Cisco 把 FY27 hyperscaler AI-infrastructure revenue 预期上调至 90 亿美元；这是公司判断，不能外推成行业实际 CapEx。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m11/cisco-reports-first-quarter-earnings.html)
5. **光网络控制面成为研究焦点。** Halley 以预测控制处理 AI 数据中心 optical resources 的关联失效和调度；论文结果主要基于仿真与原型实现。[arXiv](https://arxiv.org/abs/2611.04408)

## 本周关键技术进展 3 篇深读

### 1. USFP：把接口密度、散热和可维护性一起纳入规格

USFP 的关键不只是 400Gb/s-per-lane，而是试图在 pluggable 维护模型下提高前面板带宽密度。双方公告中的容量与能效比较来自厂商，应继续追踪 MSA 文本、connector/cable 约束、互操作测试及实际 module power。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/nvidia-and-cisco-new-pluggable-optics-to-scale-ai-factories.html)

### 2. G302：200G SerDes 的 ToR 系统化落点

G302 把 200G SerDes、51.2T capacity、1.6T optics 与 direct-to-chip liquid cooling 放在 ToR 产品语境中。这提示下一阶段验证应从单颗 ASIC 延展到光学、电源、热设计与 rack cabling；“年底前出货”仍是计划状态。[来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/cisco-advances-scalability-and-openness-at-ocp-2026.html)

### 3. Halley：将光资源失效域纳入 AI job 保障

Halley 提出 LightReserve、FoldFit、ThermaLead 与 TriageGuard，针对 shared laser、optical switch 与 microring 等层次进行预判和回退。论文里的收益有明确故障窗口及模拟假设，应把它读作可靠性控制面研究，而非生产 SLA 承诺。[arXiv](https://arxiv.org/abs/2611.04408)

## 厂商动态汇总

| 主体 | 本周应关注的公开信息 | 证据边界 |
|---|---|---|
| Cisco | G300 已向客户出货；G302 计划在年底前开始出货 | 厂商公告，未列出客户与部署规模 [来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/cisco-advances-scalability-and-openness-at-ocp-2026.html) |
| NVIDIA / Cisco | 规划 USFP 的开放多源硬件生态 | 规划中的规范与生态，非既有标准 [来源](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2026/m10/nvidia-and-cisco-new-pluggable-optics-to-scale-ai-factories.html) |
| LightCounting | 将 1.6T/3.2T、LPO/LRO/CPO/NPO 纳入 cloud optics 预测框架 | 分析师预测，并非实销数据 [来源](https://www.lightcounting.com/report/july-2026-cloud-data-center-optics-385) |

## 趋势观察

- **lane rate 与系统工程耦合更紧：** 200G/400G-per-lane 把 connector、package、module、thermal、serviceability 从外围约束变成规格核心。
- **开放生态尚需验证：** “将建立 MSA/多源生态”不应简写为“标准已定”；需要关注规范、样品、互操作和供应链。
- **可靠性控制从被动恢复走向预测：** optical resource 的共享失效域正在成为 AI workload availability 的研究变量。

## 下周关注

1. USFP 是否发布公开 MSA、接口定义或合作伙伴样品时间表。
2. G302 的实际出货与系统厂商集成信息是否出现。
3. 1.6T optics 的功耗、热设计、可插拔可靠性和现场互操作证据。
4. optical AI DCN 论文是否给出实测或可复现实验，而非仅仿真。

## 分享卡片

📌 **从 200G SerDes 到 400G/lane optics，竞争不再只在单个器件：谁能把开放接口、散热供电、可维护性与可靠性控制一起交付，谁才更接近可扩展的 AI fabric。**

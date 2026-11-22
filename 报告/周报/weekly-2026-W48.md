# 芯片互连与 AI 基础设施周报｜2026-W48

> 覆盖 2026-11-16 至 2026-11-22；由本周日报抽取 `🔥` / `⭐` 条目并结合公开一手资料复核，检索截止 2026-11-22（Asia/Shanghai）。会议、厂商公告、市场研究和预印本分别标注，不将其混作已部署事实。

## 本周最重要的 6 件事

1. 🔥 **光学互连成为规模化 AI 的系统议题。** PECC 的议程将 scale-up、scale-out、scale-across 与 optical switching 放在同一框架中；这更像架构讨论的共同语言，而不是单一的推荐方案。[来源](https://www.optica.org/events/industry_events/2026/pecc_summit_optica_apc_photonic_enabled_cloud_computing_summit/schedule/)
2. ⭐ **CPO 互操作参考架构启动协作。** Lightmatter 向 OCP 发起共享参考架构倡议；现阶段应关注随后公开的规范、验证方法和参与者交付物。[来源](https://www.ofcconference.org/news-media/exhibitor-news/lightmatter-announces-reference-architecture-initiative-with-industry-leaders-in-the-open-compute-pr/)
3. ⭐ **UALink 的公开材料延伸至 In-Network Compute。** Consortium 将 Common 2.0 定位为降低分布式训练/推理通信开销的机制，仍需区分规格发布与可互操作系统可得性。[来源](https://ualinkconsortium.org/specification/)
4. ⭐ **784-Gb/s/λ 片间研究展示多维复用潜力。** 11 月 20 日日报收录的 Photonics Research early posting 属于研究演示，不能替代可插拔或量产器件规格。[来源](https://opg.optica.org/prj/upcoming_pdf.cfm?id=603843)
5. 🔥 **网络需求信号与供给约束并存。** Dell'Oro 的 3Q26 摘要称 optical transport 市场同比增长 24%、相关北美云服务商厂商收入同比增长 75%；这是机构统计/判断，非运营商或设备商逐项目部署清单。[来源](https://www.delloro.com/newsroom/optical-transport-market-growth-3q26/)
6. ⭐ **高芯数布线进入 AI/HPC 工程讨论。** STL 的 SC26 展示包含高密度光纤和连接器方案，说明机房布线密度仍是系统设计变量；展会资料未披露客户或部署规模。[来源](https://stl.tech/sc26/)

## 本周关键技术进展 3 篇深读

### 1. CPO：从单器件性能转到可互操作系统边界

本周的 CPO 线索包括 Lightmatter 的 OCP 参考架构倡议、NewPhotonics 的 heaterless MRM 展示与 OIF 的多厂商展示计划。共同点是封装、热管理、控制/管理与光电接口需要联动；不同材料的证据强度不同：倡议和展会发布说明路线与参与方，尚不能证明客户导入或规模量产。[Lightmatter](https://www.ofcconference.org/news-media/exhibitor-news/lightmatter-announces-reference-architecture-initiative-with-industry-leaders-in-the-open-compute-pr/) / [NewPhotonics](https://www.ofcconference.org/news-media/exhibitor-news/newphotonics-introduces-syncra-self-calibrating-heaterless-mrm-solution-to-drive-next-generation-hig/) / [OIF](https://www.ofcconference.org/news-media/exhibitor-news/oif-demonstrates-industry-wide-interoperability-at-scale-at-ofc-2026-advancing-energy-efficiency-p/)

### 2. OCS：低延迟叙事必须落实到路径、控制与重构约束

OCP 的 OCS 白皮书梳理了 robotic、MEMS、liquid-crystal、piezo 与 silicon-photonics 等技术，并以 radix、insertion loss、switching time 和 scalability 作为比较维度。它的启示是：评估 OCS 不能只看单次切换或光学损耗，必须同时检查流量调度、故障隔离、重构时间和与 packet fabric 的协同。[来源](https://www.opencompute.org/documents/ocp-ocs-white-paper-april-2026-final-pdf/)

### 3. 片上多维互连：研究带宽不是模块路线图

本周两篇研究线索分别是 784-Gb/s/λ 多维 inter-chip communication early posting，以及 coherent-lite 的 WDM/MDM/self-homodyne on-chip interconnect 预印本。前者强调 silicon photonic multiplexer、transceiver 与 processor 的协同，后者强调电带宽与能耗预算；二者都值得追踪封装、误码、热稳定与制造容差，但不应外推为商业模块的标准参数。[784-Gb/s/λ](https://opg.optica.org/prj/upcoming_pdf.cfm?id=603843) / [coherent-lite](https://arxiv.org/abs/2611.19254)

## 厂商动态汇总

| 主体 | 本周公开信息 | 证据边界 |
|---|---|---|
| Lightmatter / OCP | 提出 CPO 共享参考架构协作 | 倡议启动，不等于已发布统一规范或部署 [来源](https://www.ofcconference.org/news-media/exhibitor-news/lightmatter-announces-reference-architecture-initiative-with-industry-leaders-in-the-open-compute-pr/) |
| NewPhotonics | 宣传面向 CPO 的 self-calibrating heaterless MRM 技术 | 厂商展会公告，未给出第三方系统验证或量产信息 [来源](https://www.ofcconference.org/news-media/exhibitor-news/newphotonics-introduces-syncra-self-calibrating-heaterless-mrm-solution-to-drive-next-generation-hig/) |
| STL | SC26 展示高密度光纤、连接器和机柜级方案 | 展示材料，未说明客户与部署规模 [来源](https://stl.tech/sc26/) |
| OIF 成员生态 | 列出 CEI-448G/224G、CMIS、co-packaging 与 EEI 的互操作展示方向 | 活动公告；需追踪规范版本、测试条件与结果 [来源](https://www.ofcconference.org/news-media/exhibitor-news/oif-demonstrates-industry-wide-interoperability-at-scale-at-ofc-2026-advancing-energy-efficiency-p/) |

## 趋势观察

- **互连选择正在系统化：** scale-up、scale-out 与 scale-across 的层次划分，会影响电互连、pluggable optics、NPO/CPO 与 OCS 的取舍。
- **开放不等于可部署：** 倡议、路线图和会议 demo 是必要信号，但规格文本、互操作数据、可维护性和供给才是下一个验证层。
- **基础设施约束前移：** high-density cabling、热管理、电力与控制面的设计，已与 lane rate 同样影响 AI fabric 的可扩展性。

## 下周关注

1. CPO 参考架构是否公开接口、可靠性或可维护性要求。
2. UALink 是否发布更明确的测试、生态或实现状态材料。
3. OIF/行业组织是否披露 CEI-448G 与相关管理接口的互操作细节。
4. OCS 方案是否给出端到端调度、故障恢复与实际工作负载证据。

## 分享卡片

📌 **本周结论：** AI 互连的竞争已从“单个端口多快”进入“系统能否互操作、散热、维护并稳定扩展”。看路线图时，应把规格、演示、研究和部署证据严格分层。

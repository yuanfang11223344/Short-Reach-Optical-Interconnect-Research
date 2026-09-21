# 芯片互连与AI基础设施 每周综述 2026-W39

> 生成时间：2026-09-21 10:00（Asia/Shanghai）。周一例行周报；已先生成 `2026-09-21.md`，并纳入其中 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-09-21，后续日报继续作为 W39 周报滚动素材。

## 本周最重要的 5-8 件事

### 🔥 ECOC Exhibition 2026 今日开展，224G/448G、1.6T/3.2T optics 与 CPO/NPO 进入现场证据窗口

- 要点：ECOC Exhibition 日期为 2026-09-21 至 2026-09-23，Conference 为 2026-09-20 至 2026-09-24；OIF @ ECOC 2026 聚焦 448G/224G Common Electrical I/O、CMIS、Co-Packaging、Energy Efficient Interfaces 等 live demo。https://www.ecocexhibition.com/  https://www.oiforum.com/meetings-events/oif-ecoc-2026/
- 为什么重要：AI data center interconnect 正从单点器件指标转向 multi-vendor interoperability。真正有价值的现场证据包括 host ASIC、module、optical engine、cable/fiber、FEC、BER、link training、management state、thermal telemetry 和 test equipment 组合。

### 🔥 400G per lane 之后，copper、LPO、CPO 的边界变成系统工程问题

- 要点：Astera Labs 的 400G-per-lane 文章把 retimer、active electrical cable、linear pluggable optics 与 co-packaged optics 放在同一系统取舍框架中。https://www.asteralabs.com/resources/blog/the-400g-per-lane-inflection-point-where-copper-and-optical-meet-in-ai-infrastructure/
- 为什么重要：短距互连不会一夜从 copper 切到 optics。rack 内、rack 间、switch-to-module、package-to-package 的距离、功耗、可维护性和供应链成熟度不同，决定了不同形态将长期共存。

### 🔥 AI Infra Summit 收官后，Data Movement 成为 AI supernode 的共同语言

- 要点：AI Infra Summit 的 Data Movement 生态覆盖 Astera Labs、Ayar Labs、Lightmatter、Marvell、Micron、Nokia、Samsung、Samtec、SK hynix 等。https://www.ai-infra-summit.com/data-movement
- 为什么重要：超节点瓶颈不再只是 GPU fabric；HBM/CXL/SSD tiering、KV cache reuse、PCIe/CXL、Ethernet、optical I/O、storage locality 与 telemetry 会共同决定 tokens-per-watt 和 job completion time。

### 🔥 Marvell 把 Photonic Fabric、PCIe 6.0、CXL 和 telemetry 打包成 AI data center connectivity portfolio

- 要点：Marvell 公告称其在 AI Infra Summit 展示 end-to-end AI data center connectivity portfolio，包括 Photonic Fabric、RELIANT telemetry、Teralynx T100、PCIe 6.0 switch 和 CXL memory solutions。https://investor.marvell.com/news-events/press-releases/detail/1032/marvell-to-showcase-end-to-end-ai-data-center-connectivity-portfolio-at-ai-infra-summit-2026
- 为什么重要：供应商正在把 scale-up、scale-out、resource pooling、custom silicon 与可观测性组合销售。评估互连芯片时，需要同时看 telemetry、failure isolation、resource scheduling 和软件栈，而不是只看带宽。

### ⭐ Connectorized microLED optical I/O 把 optical link 的部署问题推到可维护性层面

- 要点：Avicena 2026-09-17 新闻页显示其将在 ECOC 2026 展示 connectorized LightBundle microLED optical interconnect for AI infrastructure。https://avicena.tech/press-releases/
- 为什么重要：microLED optical I/O 的产业化挑战不只在器件效率，也在 connector repeatability、multicore fiber attach、BER monitoring、thermal envelope 和 field service。当前仍是公开展示与评估套件线索，暂无独立评测。

### ⭐ AI infrastructure 的供电标准化开始直接影响互连边界

- 要点：Open Compute Project 官网近期把 Google、Microsoft、NVIDIA 协作推动 800 VDC open standardized power architecture 放到 next-era AI data center 议题中。https://www.opencompute.org/
- 为什么重要：更高 radix、更短 electrical reach、CPO/NPO 或 OCS 的收益最终要回到 rack power、connector safety、liquid cooling、service workflow 和并网约束。

## 本周关键技术进展 3 篇深读

### 1. Multi-vendor interoperability 正成为 224G/448G 时代的真实门槛

- 背景：1.6T/3.2T optics、224G/448G electrical I/O、CMIS/C-CMIS、CPO/NPO、FEC 与 test equipment 需要跨厂商共同工作，单一器件规格不足以证明可采购性。
- 本周信号：OIF @ ECOC 2026 把 448G/224G CEI、CMIS、Co-Packaging、EEI 作为现场演示重点；ECOC 展会聚集 optical module、TFLN、silicon photonics、coherent 和 data center optics 供应链。https://www.oiforum.com/meetings-events/oif-ecoc-2026/
- 观察指标：公开 demo 是否说明 host、module、cable/fiber、link training、error counters、management state、thermal profile 和测试设备；如果只展示眼图或带宽宣传，仍不能视为部署成熟。

### 2. Optical I/O 的价值正在从“更高速率”转向“更可维护的系统接口”

- 背景：CPO、NPO、LPO、microLED optical I/O、silicon photonics 和 TFLN 都在争取 AI data center 的短距高带宽链路，但部署难点集中在封装、散热、维护和供应链。
- 本周信号：Avicena 强调 connectorized LightBundle eKit，OpenLight 继续推进 3.2T DR8 PIC 与 1.6T/3.2T PASIC，Lightmatter 把 optical link 放进 open silicon photonics for AI systems 架构叙事。https://avicena.tech/press-releases/  https://openlightphotonics.com/applications/datacom-telecom  https://lightmatter.co/
- 推演：未来周报应优先记录可插拔/可重连边界、现场更换流程、fiber management、laser safety、thermal coupling 和监控接口，而不仅是 Tbps 数字。

### 3. Photonic-CXL 与 KV cache 论文把互连问题推向 LLM serving 内存层级

- 背景：长上下文、多轮对话和 agentic serving 增加 KV cache 复用需求，GPU HBM 不足以经济地保存所有状态，CXL memory pooling 与 photonic fabric 因而进入系统研究。
- 本周信号：arXiv:2607.27187 提出 Photonic-CXL Memory Appliance，通过 passive fiber shuffle 构造 16 hosts / 32 TB shared memory；arXiv:2609.01821 则从 inference prefill 角度建模 high-radix photonic interconnect。https://arxiv.org/abs/2607.27187  https://arxiv.org/abs/2609.01821
- 推演：互连价值越来越需要绑定 workload：prefill/decode、KV reuse、batching、multi-tenancy、tail latency、TTFT 和 power。没有 workload 假设的 “bandwidth wins” 结论会越来越不可靠。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| ECOC 2026 | Exhibition 今日开展，Conference 本周进行 | Optical communication、datacenter optics、silicon photonics | https://www.ecocexhibition.com/ |
| OIF | ECOC live demo 覆盖 448G/224G CEI、CMIS、CPO、EEI | Multi-vendor electrical/optical interoperability | https://www.oiforum.com/meetings-events/oif-ecoc-2026/ |
| Astera Labs | 讨论 400G/lane 下 copper、LPO、CPO 的边界 | Retimer、AEC、LPO、CPO 分层架构 | https://www.asteralabs.com/resources/blog/the-400g-per-lane-inflection-point-where-copper-and-optical-meet-in-ai-infrastructure/ |
| Avicena | 展示 connectorized LightBundle microLED optical interconnect | Optical I/O、serviceability、evaluation kit | https://avicena.tech/press-releases/ |
| OpenLight | 推进 3.2T DR8 PIC、1.6T DR8 LRO/LPO、PASIC | Silicon photonics、terabit optics | https://openlightphotonics.com/applications/datacom-telecom |
| Lightmatter | 强调 photonic interconnect、OCP workstream 与 optical link | Optical fabric、silicon photonics architecture | https://lightmatter.co/ |
| Marvell | AI Infra Summit 展示 connectivity portfolio | Photonic Fabric、PCIe 6.0、CXL、telemetry | https://investor.marvell.com/news-events/press-releases/detail/1032/marvell-to-showcase-end-to-end-ai-data-center-connectivity-portfolio-at-ai-infra-summit-2026 |
| SK hynix | AI Memory、HBM、CXL tiered memory、Indiana fab 等动态 | Memory hierarchy、KV cache、AI serving | https://news.skhynix.com/en/ |
| OCP | 推动 800 VDC 等 AI infrastructure 标准化议题 | Rack power、open hardware、serviceability | https://www.opencompute.org/ |

## 趋势观察

- **AI interconnect 的证据标准正在提高。** 224G/448G、1.6T/3.2T、CPO/NPO 如果没有公开互操作、管理面、测试设备和运维证据，只能算方向或 demo。https://www.oiforum.com/
- **Optics 与 copper 会继续共存。** 400G/lane 之后，铜缆、retimer、AEC、LPO、CPO 的边界由距离、功耗、可维护性和供应链决定。https://www.asteralabs.com/resources/blog/the-400g-per-lane-inflection-point-where-copper-and-optical-meet-in-ai-infrastructure/
- **Memory hierarchy 正在重塑 fabric 需求。** HBM、CXL memory、SSD-backed KV cache、photonic memory appliance 和 storage locality 会改变集体通信和推理调度的瓶颈位置。https://arxiv.org/abs/2607.27187
- **Power architecture 会成为互连约束。** 800 VDC、液冷、rack safety、connector design 和 grid stability 会反向限制高 radix fabric、CPO/NPO 和 OCS 的部署节奏。https://www.opencompute.org/
- **公开客户量产证据仍不足。** CPO/NPO、microLED optical I/O、Photonic Fabric 都在加速展示和标准化，但不能把展会演示直接写成 hyperscale production rollout。https://avicena.tech/press-releases/

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| ECOC 2026 Conference | 2026-09-20 至 2026-09-24 | Coherent optics、silicon photonics、datacenter interconnect | https://ecoc2026.org/ECOC2026 |
| ECOC Exhibition 2026 | 2026-09-21 至 2026-09-23 | OIF interop、1.6T/3.2T optics、CPO/NPO、TFLN | https://www.ecocexhibition.com/ |
| OIF @ ECOC 2026 | 2026-09-21 至 2026-09-23 | 448G/224G CEI、CMIS、Co-Packaging、EEI | https://www.oiforum.com/meetings-events/oif-ecoc-2026/ |
| OCP Global Summit 2026 | 2026-10-12 至 2026-10-15 | 800 VDC、open rack、power/cooling、hardware management | https://www.opencompute.org/summit/global-summit |
| SC26 | 2026-11-15 至 2026-11-20 | HPC/AI networking、collective communication、large-scale systems | https://sc26.supercomputing.org/ |

## 📱 分享卡片

- W39 主线：ECOC 今日开展，AI interconnect 的重点从路线图进入现场互操作证据。https://www.oiforum.com/meetings-events/oif-ecoc-2026/
- 400G/lane 之后，copper、LPO、CPO 的分工由距离、功耗、维护和供应链共同决定。https://www.asteralabs.com/resources/blog/the-400g-per-lane-inflection-point-where-copper-and-optical-meet-in-ai-infrastructure/
- Connectorized microLED optical I/O 的关键不是只看速率，而是可重连、可维护、BER monitoring 和 thermal envelope。https://avicena.tech/press-releases/
- Photonic-CXL 与 high-radix photonic interconnect 论文提示：LLM serving 的互连价值必须绑定 KV cache、TTFT 和 workload 假设。https://arxiv.org/abs/2607.27187
- 本周保守判断：标准化和 demo 正在加速，但公开客户集群规模替代证据仍不足。https://www.oiforum.com/

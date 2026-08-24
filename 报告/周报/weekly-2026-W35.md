# 芯片互连与AI基础设施 每周综述 2026-W35

> 生成时间：2026-08-24 10:00（Asia/Shanghai）。周一例行周报；已先生成 `2026-08-24.md`，并纳入其中 `🔥` 与 `⭐` 条目。本周当前覆盖 2026-08-24，后续日报继续作为 W35 周报滚动素材。

## 本周最重要的 5-8 件事

### 🔥 NVIDIA Hot Chips 2026 把 Vera/Rubin/NVLink/Spectrum-X 推成 rack-scale AI factory 平台
- 要点：NVIDIA 今日在 Hot Chips 2026 展示 Vera CPU 与 Rubin GPU，官方页面同时列出 BlueField-4、Spectrum-X Multiplane Network Architecture、LPU Accelerator 和 Vera Rubin NVL72。Vera Rubin NVL72 描述为 72 Rubin GPUs、36 Vera CPUs、ConnectX-9 SuperNICs、BlueField-4 DPUs，并以第六代 NVLink/NVLink Switch scale up、Quantum-X800 InfiniBand 与 Spectrum-X Ethernet scale out。[来源](https://www.nvidia.com/en-us/events/hot-chips-conference/)
- 为什么重要：AI 服务器竞争正在从单卡算力转为 rack-scale platform，包括 CPU/GPU/DPU/NIC/switch、通信库、telemetry 和部署服务。

### 🔥 Hot Interconnects 2026 给本周留下 AI fabric 技术清单
- 要点：HotI program 覆盖 high-radix photonic interconnect、Petabit-class MoE switching、MRC transport、Omnistat/Cassini telemetry、NVSHMEM、long-haul RDMA、UALink/UCIe tutorials 和 GPU communication libraries。[来源](https://hoti.org/2026/program.html)
- 为什么重要：互连瓶颈已从 SerDes eye/BER 扩展为网络拓扑、可靠传输、通信库、dispatch overhead 和跨站点调度的联合问题。

### 🔥 OIF 把 compute optical interfaces、NPO、EEI 与 1600G DCI 并行推进
- 要点：OIF current work 中 COI 面向 PCIe、NVLink、UALink 等 low-latency photonic interfaces；12.8T NPO 项目纳入 200G/lane、液冷、laser source、power supply、optical connector；1600ZR/1600ZR+/1600CL 面向 hyperscaler DCI 和 data center campus。[来源](https://www.oiforum.com/technical-work/current-work/)
- 为什么重要：光互连的标准化边界正从 Ethernet front-panel optics 同时向 accelerator scale-up 和 AI campus scale-across 延伸。

### 🔥 Synopsys 3D PCIe 6.0 PHY 验证提示高速 I/O 进入封装共设计
- 要点：Synopsys 披露 3D PCIe 6.0 PHY 8-lane test chip，在 face-to-face 3D stack 中验证 64 GT/s、PAM4、最高 128 GB/s 8-lane link。[来源](https://www.synopsys.com/blogs/chip-design/3d-pcie-6-0-phy-8-lane-test-chip.html)
- 为什么重要：AI accelerator、CXL memory fabric、DPU/SmartNIC 和 data center switch 的 I/O 已无法只靠板级通道优化，3DIC、TSV、power/signal integrity 和 IP 验证要一起设计。

### ⭐ CoreWeave Q2 把 Vera Rubin 验证、电力和 AI cloud backlog 绑定
- 要点：CoreWeave Q2 2026 revenue 为 2.575B 美元，revenue backlog 约 104B 美元；active power 增加近 500MW 至 1.5GW，total contracted power 约 3.7GW，并完成 Vera Rubin NVL72 bring-up and validation。[来源](https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Second-Quarter-2026-Results/default.aspx)
- 为什么重要：AI cluster 交付速度由 GPU、网络、供电、液冷、站点和客户合约共同约束，互连技术评估必须进入设施工程层。

### ⭐ Marvell/Google 8-K 显示 hyperscaler custom silicon 正深入 I/O 与 memory fabric
- 要点：Marvell 披露与 Google 的 expanded partnership 覆盖 TPU ecosystem，包括 AI inference accelerators、storage controllers、network interface controllers、memory interface controllers 和 near-memory compute。[来源](https://investor.marvell.com/sec-filings/all-sec-filings/content/0001193125-26-356217/d412696d8k.htm)
- 为什么重要：custom AI silicon 不只是 accelerator die，而是把 NIC、memory interface、storage/data movement 和 near-memory compute 纳入平台级 I/O 设计。

## 本周关键技术进展 3 篇深读

### 1. AI fabric 的性能指标正在从“峰值带宽”转向“可运行的系统带宽”
- 背景：224G/448G SerDes、1.6T/3.2T optics 和 51.2T/102.4T switch ASIC 仍然重要，但训练和推理的实际瓶颈常出现在 all-to-all、prefill、expert routing、通信库和尾延迟。
- 本周信号：HotI 2026 把 high-radix photonic interconnect、Petabit-class MoE switching、MRC transport、NVSHMEM、dispatch overhead 和 telemetry 放在同一 program。[来源](https://hoti.org/2026/program.html)
- 推演：后续报告应更关注 workload-driven validation：同一条 224G/1.6T 链路在 NCCL/RCCL、UET/RoCE、MRC、job scheduler、telemetry 组合下能否提供稳定 iteration time。

### 2. 光互连正在同时进入 scale-up、scale-out、scale-across 三层
- 背景：过去光模块主要服务 scale-out Ethernet 和 DCI；CPO/NPO 讨论更多停留在封装和光源层。
- 本周信号：OIF COI 面向 PCIe/NVLink/UALink，12.8T NPO 明确 200G/lane、液冷和 external laser，HotOptics/HotI 继续讨论 optical scale-up/out/across，Marvell 1.6T DSP portfolio 覆盖 pluggable、coherent-lite、gearbox 和 telemetry。[来源](https://www.oiforum.com/technical-work/current-work/)
- 推演：产业链会分成多条并行路径：front-panel 1.6T/3.2T 继续放量，NPO/CPO 做 near-package/power density，OCS/photonic fabric 解决重构和 radix，ZR/ZR+/CL 支撑 AI campus 与跨站点训练。

### 3. 封装内高速 I/O 与数据中心设施正在同向收敛
- 背景：AI supernode 的瓶颈同时出现在 GPU-GPU、CPU-GPU、host-device、NIC/DPU、光模块、rack power 和 liquid cooling。
- 本周信号：Synopsys 3D PCIe 6.0 PHY 验证把 64 GT/s PCIe 放进 3D stack；NVIDIA Vera Rubin NVL72 把 CPU/GPU/NIC/DPU/switch 合成 rack-scale platform；CoreWeave 将 Vera Rubin validation 和 1.5GW active power 放在同一季度披露。[来源](https://www.synopsys.com/blogs/chip-design/3d-pcie-6-0-phy-8-lane-test-chip.html)
- 推演：下一代 AI 基础设施的设计边界会跨越 chiplet/package、board、rack、row、campus。报告后续应把 PCIe/CXL/UCIe/UALink、NVLink/Ethernet、CPO/NPO、液冷和供电一起跟踪。

## 厂商动态汇总

| 厂商/组织 | 本周动作 | 影响方向 | 链接 |
|---|---|---|---|
| NVIDIA | Hot Chips 2026 展示 Vera CPU、Rubin GPU、BlueField-4、Spectrum-X、LPU 和 Vera Rubin NVL72 | AI factory platform、scale-up/out fabric | https://www.nvidia.com/en-us/events/hot-chips-conference/ |
| Hot Interconnects | 2026 program 聚焦 gigawatt/gigascale AI networking、photonic interconnect、transport、communication libraries | AI fabric research、system validation | https://hoti.org/2026/program.html |
| OIF | COI、NPO、EEI、CEI-224G/448G、1600ZR/CL 并行推进 | standards、CPO/NPO、DCI | https://www.oiforum.com/technical-work/current-work/ |
| Synopsys | 3D PCIe 6.0 PHY 8-lane test chip at 64 GT/s | 3DIC、PCIe/CXL、AI accelerator I/O | https://www.synopsys.com/blogs/chip-design/3d-pcie-6-0-phy-8-lane-test-chip.html |
| CoreWeave | Q2 revenue 2.575B 美元，active power 1.5GW，Vera Rubin NVL72 bring-up | AI cloud、power/cooling、supernode validation | https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Second-Quarter-2026-Results/default.aspx |
| Marvell | Google expanded partnership 进入 TPU ecosystem；1.6T DSP portfolio 覆盖多层 AI connectivity | custom silicon、NIC/memory interface、optical DSP | https://investor.marvell.com/sec-filings/all-sec-filings/content/0001193125-26-356217/d412696d8k.htm |
| Keysight | 224G/1.6T optical validation 和 AI infrastructure test 继续推进 | test workflow、manufacturing readiness | https://www.businesswire.com/news/home/20260313711497/en/Keysight-Introduces-New-224G-Test-Solutions-to-Enable-1.6T-Optical-Network-Validation |
| Lumentum / Coherent | FY2026 Q4 财报显示 datacenter optics 仍是核心观察项 | lasers、transceivers、OCS/CPO/NPO | https://www.coherent.com/news/press-releases/fourth-quarter-and-fiscal-year-2026-results |

## 趋势观察

- **AI 互连会按 workload 分层，而不是只按物理距离分层。** MoE training、inference prefill、long-context agent、federated AI 和 multi-tenant cloud 对网络的瓶颈不同，SerDes/optics/transport/telemetry 需要按 workload 做组合验证。[来源](https://hoti.org/2026/program.html)
- **CPO/NPO 的量产障碍更像系统工程问题。** OIF NPO 项目把液冷、光源、供电和连接器写入同一接口，说明 serviceability、thermal interface、laser redundancy 与管理面会和光学指标一样关键。[来源](https://www.oiforum.com/technical-work/current-work/)
- **Hyperscaler custom silicon 会继续吞并 I/O 和 memory subsystem。** Marvell/Google 8-K 中的 NIC、memory interface controller、near-memory compute 说明 TPU/accelerator ecosystem 的外延正在扩大。[来源](https://investor.marvell.com/sec-filings/all-sec-filings/content/0001193125-26-356217/d412696d8k.htm)
- **供电与液冷会决定互连技术进入生产的节奏。** CoreWeave 和 Vertiv 公开材料显示 AI factory 交付需要 power、cooling、rack integration、network 和 lifecycle services 一体化。[来源](https://www.vertiv.com/en-us/insights/topics/data-center-innovation/)

## 下周关注

| 事件 | 日期 | 关注点 | 链接 |
|---|---|---|---|
| Hot Chips 2026 后续材料 | 2026-08-24 至 2026-08-25 | Vera/Rubin/NVLink/Spectrum-X/BlueField-4 技术细节是否公开 | https://www.nvidia.com/en-us/events/hot-chips-conference/ |
| HotI 2026 paper/slides | 会后持续 | MRC、NVSHMEM、MoE switching、photonic prefill、UALink/UCIe tutorials | https://hoti.org/2026/program.html |
| OIF 224G/448G 与 NPO/COI 项目 | 持续跟踪 | CEI-448G、EEI、12.8T NPO、compute optical interfaces | https://www.oiforum.com/technical-work/current-work/ |
| Marvell FY2027 Q2 results | 2026-08-27 | Google custom silicon、1.6T optics、data center revenue mix | https://investor.marvell.com/news-events/press-releases |
| Keysight AI Data Center Summit | 2026-09-14 | 224G/1.6T、AI workload emulation、end-to-end validation | https://www.keysight.com/us/en/cmp/keysight-ai-data-center-summit.html |
| AI Infra Summit 2026 | 2026-09-15 至 2026-09-17 | UEC/UALink、data movement、AI data centers、physical infrastructure | https://www.ai-infra-summit.com/ |

## 📱 分享卡片

- 本周主线：NVIDIA Hot Chips 把 AI infrastructure 从芯片发布推向 rack-scale platform 发布。https://www.nvidia.com/en-us/events/hot-chips-conference/
- HotI 2026 留下的技术清单很清楚：photonic interconnect、MoE switching、MRC transport、NVSHMEM、telemetry 和 UALink/UCIe 会一起决定 AI fabric。https://hoti.org/2026/program.html
- OIF COI/NPO/EEI 显示光互连正在同时进入 accelerator scale-up、near-package optics 和 campus DCI。https://www.oiforum.com/technical-work/current-work/
- Synopsys 3D PCIe 6.0 PHY 说明 64 GT/s I/O 正从板级通道优化走向 3DIC/封装共设计。https://www.synopsys.com/blogs/chip-design/3d-pcie-6-0-phy-8-lane-test-chip.html
- CoreWeave 的 1.5GW active power 和 Vera Rubin NVL72 validation 提醒：未来互连报告必须同时看电力、液冷、网络和 supernode。https://investors.coreweave.com/news/news-details/2026/CoreWeave-Reports-Strong-Second-Quarter-2026-Results/default.aspx

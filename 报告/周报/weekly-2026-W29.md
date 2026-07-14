# 芯片互连与AI基础设施 每周综述 2026-W29

## 本周最重要的 5-8 件事

1. 🔥 224G SerDes 的工程重心从单 PHY 性能转向系统互通。OIF OFC 2026 demo 把 224G VSR multi-vendor interop、212.5Gbps PRBS31Q PAM4、1.6T retimed connectivity 和热设计放入同一套验证。来源：https://www.oiforum.com/wp-content/uploads/CEI-Rolling-Deck.pdf
2. 🔥 448G CEI 已进入框架定义。OIF `Next Generation CEI-448G Framework` 明确 448Gbps/lane 需要新的 specifications 与 technologies，为 3.2T/6.4T optical module host side 铺路。来源：https://www.oiforum.com/wp-content/uploads/OIF-FD-CEI-448G-01.0.pdf
3. 🔥 1.6T optical DSP 平台化加速。Marvell、Credo、Broadcom 均围绕 200G/lane PAM4 DSP、1.6T retimed optics、linear-receive 或 coherent 1.6T ZR/ZR+ 发布/展示产品组合。来源：https://www.marvell.com/company/newsroom/marvell-1-6t-optical-dsp-ai-data-center-connectivity.html
4. 🔥 CPO/OCI 正从研究议题转向平台产品。GlobalFoundries SCALE 以 OCI MSA-capable CPO 光引擎切入 foundry silicon photonics 平台层。来源：https://gf.com/news-and-events/news/globalfoundries-accelerates-adoption-of-co-packaged-optics-for-advanced-ai-data-centers-with-scale-optical-module-solution/
5. 🔥 开放 scale-up fabric 开始落到器件。Credo Blue Heron 224G retimer 直接支持 UALink、ESUN 和 Ethernet，UALink 白皮书把开放 rack-scale interconnect 定位在 PCIe/CXL 与 Ethernet/InfiniBand 之间。来源：https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx
6. 🔥 AI data center 的关键约束继续转向电力和冷却。Gartner 预测 2026 年全球数据中心用电 565TWh，Meta 加拿大 AI 园区绑定 closed-loop cooling 与 932MW 发电项目。来源：https://www.tomshardware.com/tech-industry/artificial-intelligence/ai-servers-will-consume-more-power-than-conventional-data-center-hardware-by-2027-gartner-forecasts
7. ⭐ 国内光模块厂商继续推进 NPO/XPO。中际旭创提到 6.4T NPO、12.8T XPO 研发送测，光迅科技披露 1.6T 批量交付能力并展示 3.2T 硅光单模 NPO。来源：https://static.cninfo.com.cn/finalpage/2026-04-24/1225185699.PDF

## 本周关键技术进展

### 1. 224G/448G electrical I/O：从速率竞赛进入互通与热设计

OIF OFC 2026 CEI demo 的重点不是单一 224G lane，而是多厂商互通、VSR channel、module compliance board 和 heatsink 组合。对 SerDes 设计工程师来说，这意味着 TX/RX equalization、package loss、connector/cable、board material、retimer placement 和 thermal budget 必须在同一套验证计划里收敛。CEI-448G framework 进一步把下一代 448Gbps/lane 的应用空间提前框定，说明 3.2T/6.4T 模块不会只靠 optical lane 提升，host electrical side 也要同步换代。来源：https://www.oiforum.com/wp-content/uploads/CEI-Rolling-Deck.pdf

### 2. 1.6T optical DSP：retimed、linear-receive 与 coherent 三条路线并行

Marvell 的 1.6T optical DSP portfolio 强调 end-to-end AI connectivity，Credo Cardinal 把 retimed 1.6T optics 与 linear-receive implementations 同时纳入产品族，Broadcom Sian3 则继续强调 3nm 200G/lane PAM4 DSP PHY 的功耗优势。短距 AI fabric 侧会围绕 pluggable power、latency、DSP complexity 和 LPO/LRO 可运维性展开权衡；DCI/metro 侧则由 Marvell 1.6T ZR/ZR+ coherent DSP 推动 coherent pluggable 升级。来源：https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Cardinal-A-LowPower-1-6T-Optical-DSP-Family-Engineered-for-MassiveScale-AI-Fabrics/default.aspx

### 3. AI data center power：网络能效成为机房级约束的一部分

Gartner 预测 AI-optimized server 用电快速增长，并在 2027 年超过传统服务器；Meta 加拿大项目显示 hyperscale AI 园区已需要本地发电、闭环冷却和大规模土建同步规划。互连侧的 pJ/bit 降低不再只是芯片指标，而会进入机柜 power envelope、液冷 capacity 和供电审批的总账。来源：https://apnews.com/article/922a7d15ab730ec53b934269fc00a0fa

## 厂商动态汇总

| 厂商/组织 | 本周关注点 | 工程含义 | 来源 |
|---|---|---|---|
| OIF | 224G CEI OFC 互通与 448G framework | 224G 量产看互通，448G 提前定义接口边界 | https://www.oiforum.com/wp-content/uploads/OIF-FD-CEI-448G-01.0.pdf |
| GlobalFoundries | SCALE OCI MSA-capable CPO 平台 | CPO 光引擎进入 foundry 平台化 | https://gf.com/news-and-events/news/globalfoundries-accelerates-adoption-of-co-packaged-optics-for-advanced-ai-data-centers-with-scale-optical-module-solution/ |
| Marvell | 1.6T optical DSP、224G LR SerDes、1.6T ZR/ZR+ | 覆盖短距 AI fabric 与 DCI coherent | https://www.marvell.com/blogs/224g-long-range-serdes-scale-up-scale-inside.html |
| Credo | Blue Heron 224G retimer、Cardinal 1.6T DSP | UALink/ESUN/Ethernet scale-up 器件化 | https://credosemi.com/products/retimers-macsec/ |
| Broadcom | Sian3 3nm 200G/lane PAM4 DSP PHY | 800G/1.6T pluggable DSP 功耗竞争 | https://investors.broadcom.com/news-releases/news-release-details/broadcom-extends-200glane-dsp-phy-leadership-next-generation-ai |
| NVIDIA | NVLink/NVLink Switch/NVLink Fusion | proprietary scale-up fabric 继续外扩生态 | https://www.nvidia.com/en-us/data-center/nvlink/ |
| 中际旭创 | 800G/1.6T 出货需求，6.4T NPO/12.8T XPO 研发送测 | 国内头部模块厂进入下一代形态储备 | https://static.cninfo.com.cn/finalpage/2026-04-24/1225185699.PDF |
| 光迅科技 | 1.6T 批量交付能力，3.2T 硅光单模 NPO | 国内硅光/NPO 产品化节奏加快 | https://vip.stock.finance.sina.com.cn/corp/view/vCB_AllBulletinDetail.php?id=12321776&stockid=002281 |
| 澜起科技 | PCIe 6.x/CXL 3.x Retimer 送样 | CXL/PCIe scale-up/scale-inside 互连国产化 | https://www.montage-tech.com/cn/Press_Releases/20250122 |

## 趋势观察

- 🔥 224G 是 1.6T 量产门槛，448G 是 3.2T/6.4T 的定义窗口。OIF 同时展示 224G 互通和 448G framework，说明产业链正在用一代做产品、一代做规范的节奏推进。来源：https://www.oiforum.com/wp-content/uploads/CEI-Rolling-Deck.pdf
- 🔥 CPO 不会单独替代 pluggable，而会和 NPO/XPO/OCS 分场景共存。GF SCALE、国内 6.4T NPO/12.8T XPO 展示、OFC 2026 1.6T pluggable roadmap 共同指向多形态并行。来源：https://connectorsupplier.com/ofc-2026-high-speed-networking-in-the-ai-era/
- ⭐ AI 基础设施的竞争正在从芯片 BOM 扩大到 power-to-bit。数据中心用电、closed-loop cooling、behind-the-meter power 与 SerDes/optical pJ/bit 形成同一条效率链。来源：https://www.coresite.com/blog/data-center-outlook-2026-power-and-cooling-challenges-and-solutions-are-top-of-mind

## 下周关注

- 关注 OCP Global Summit 2026 public registration 打开后是否释放 AI rack、power shelf、liquid cooling、open accelerator fabric 议程。来源：https://www.opencompute.org/summit/global-summit
- 关注 Hot Chips 2026 program 中 data center SoC、chiplet coherency、memory bandwidth 和 AI fabric 报告，尤其是 Arm AGI、Fujitsu MONAKA、Intel Diamond Rapids 等。来源：https://hotchips.org/program/conference/
- 继续跟踪 OIF/IEEE 802.3dj/PCI-SIG optical workgroup 对 224G/448G host electrical interface 与 optical attach 的规范进展。来源：https://www.oiforum.com/
- 继续跟踪国内厂商 6.4T NPO、12.8T XPO 从展示/送测到客户验证的节奏。来源：https://www.cls.cn/detail/2377226

## 📱 分享卡片

- 本周核心信号：224G 正在做产品互通，448G 正在做规范框架；1.6T 到 3.2T 的换代已经开始排队。https://www.oiforum.com/wp-content/uploads/OIF-FD-CEI-448G-01.0.pdf
- CPO 平台化、NPO/XPO 展示、1.6T pluggable roadmap 同时推进，AI 光互连不会只有一种封装形态。https://gf.com/news-and-events/news/globalfoundries-accelerates-adoption-of-co-packaged-optics-for-advanced-ai-data-centers-with-scale-optical-module-solution/
- UALink/ESUN/UEC 的协议讨论正在落到 224G Retimer 和 PHY IP 上，开放 scale-up fabric 的胜负在链路 margin。https://investors.credosemi.com/news-events/news/news-details/2026/Credo-Introduces-Industrys-First-224G-Multiprotocol-AI-Scale-Up-Retimer-Supporting-UALink-ESUN-and-Ethernet/default.aspx
- AI data center 正在变成电力工程，互连能效最终会进入机房供电和冷却总预算。https://www.tomshardware.com/tech-industry/artificial-intelligence/ai-servers-will-consume-more-power-than-conventional-data-center-hardware-by-2027-gartner-forecasts

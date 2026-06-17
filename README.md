# 短距光互连研究资料库

本仓库用于版本化维护“芯片互连与AI基础设施”相关研究报告、日报/周报、同步规则和维护说明。

## 关注范围

重点关注：

- 短距光互连：CPO 共封装光学、silicon photonics 硅光子、NPO 近封装光学、optical engine 光引擎、VCSEL/EML/CWL 路线。
- SerDes 与高速电互连：224G/448G PAM4、ADC/DSP-based transceiver、Retimer/Redriver、PCIe/CXL/UALink/ESUN/UEC 链路。
- 光模块产业：800G、1.6T、3.2T、LPO、OSFP、QSFP-DD、硅光子光模块。
- AI 服务器与超节点：NVIDIA NVL 系统、UALink、ESUN、scale-up / scale-out fabric。
- 计算中心基础设施：液冷、浸没式散热、HVDC、机柜功率密度、分布式训练网络架构。

不关注：

- 消费电子、手机芯片、汽车芯片、IoT 设备、比特币挖矿。

## 仓库目录

| 路径 | 用途 |
|---|---|
| `reports/daily/` | 日报归档，文件名为 `YYYY-MM-DD.md`。 |
| `reports/weekly/` | 周报归档，文件名为 `weekly-YYYY-WXX.md`。 |
| `docs/REPORT_SYNC_RULES.md` | 报告跨位置同步规则、命名规则和校验命令。 |
| `MAINTENANCE.md` | 仓库维护规则、报告生成规则和 Git 同步规则。 |

## 当前本地路径

| 目标 | 路径 |
|---|---|
| 专题 Git 工作区 | `/Users/ganxuanzhi/学习/Short-Reach-Optical-Interconnect-Research` |
| Obsidian 输出目录 | `/Users/ganxuanzhi/Documents/Obsidian Vault/芯片互连资讯/output` |
| Obsidian 管理说明 | `/Users/ganxuanzhi/Documents/Obsidian Vault/芯片互连资讯/管理说明.md` |
| Learning_repo 镜像目录 | `/Users/ganxuanzhi/学习/Learning_repo/芯片互连资讯` |

## 核心维护规则

每次由 Codex 生成本专题日报或周报，都必须同步到三处：

1. Obsidian 输出目录。
2. Learning_repo 学习库镜像目录。
3. 本专题 Git 仓库的 `reports/daily/` 或 `reports/weekly/`。

本专题报告和维护规则更新，属于本仓库的正常维护范围，应在同步后提交并推送到远端仓库。破坏性操作、历史改写、force push、删除分支、覆盖无关文件等操作仍必须先获得用户明确确认。


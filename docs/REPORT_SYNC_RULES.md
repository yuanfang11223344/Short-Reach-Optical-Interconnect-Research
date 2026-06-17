# Report Sync Rules

## Canonical Topic

Topic name: `芯片互连与AI基础设施`

The report workflow covers short-reach optical interconnect, high-speed SerDes, optical modules, AI rack-scale systems, and compute facility infrastructure.

## Active Storage Targets

| Role | Path | Notes |
|---|---|---|
| Obsidian reading copy | `/Users/ganxuanzhi/Documents/Obsidian Vault/芯片互连资讯/output` | Main notebook output for daily reading and search. |
| Learning repo mirror | `/Users/ganxuanzhi/学习/Learning_repo/芯片互连资讯` | Mirror inside the user's existing learning knowledge repo. |
| Research Git repo | `/Users/ganxuanzhi/学习/Short-Reach-Optical-Interconnect-Research/reports` | Version-controlled research archive for this specific topic. |

## File Naming

Daily:

```text
YYYY-MM-DD.md
```

Weekly:

```text
weekly-YYYY-WXX.md
```

`YYYY-WXX` uses ISO week numbering.

## Directory Mapping

| Report type | Obsidian | Learning repo | Research Git repo |
|---|---|---|---|
| Daily | `output/YYYY-MM-DD.md` | `YYYY-MM-DD.md` | `reports/daily/YYYY-MM-DD.md` |
| Weekly | `output/weekly-YYYY-WXX.md` | `weekly-YYYY-WXX.md` | `reports/weekly/weekly-YYYY-WXX.md` |

## Sync Invariant

For the same report date/week, all three Markdown copies must contain the same report body. If a typo or source correction is made after publication, update all three copies in the same maintenance turn.

## Execution Report Format

After each generation or sync run, report:

- Mode: daily or weekly.
- Search/source directions used.
- Number of selected events/items.
- Number of unique source links.
- Saved paths.
- Git commit hash and pushed branch for the research repository.

## Manual Verification Commands

```bash
test -f "/Users/ganxuanzhi/Documents/Obsidian Vault/芯片互连资讯/output/YYYY-MM-DD.md"
test -f "/Users/ganxuanzhi/学习/Learning_repo/芯片互连资讯/YYYY-MM-DD.md"
test -f "/Users/ganxuanzhi/学习/Short-Reach-Optical-Interconnect-Research/reports/daily/YYYY-MM-DD.md"
rg -o "https?://[^ )]+" "/Users/ganxuanzhi/Documents/Obsidian Vault/芯片互连资讯/output/YYYY-MM-DD.md" | sort -u | wc -l
git -C "/Users/ganxuanzhi/学习/Short-Reach-Optical-Interconnect-Research" status --short
```

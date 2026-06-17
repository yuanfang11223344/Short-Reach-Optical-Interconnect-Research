# Maintenance Rules

## Purpose

This file defines how Codex should maintain the short-reach optical interconnect research workflow across the Git repository, local folders, and Obsidian notes.

## Trigger Rule

When generating a "芯片互连与AI基础设施" report:

- If the trigger date is Monday and the current week report does not exist, generate a weekly report.
- Otherwise generate a daily report.
- If the user explicitly asks for daily or weekly mode, follow the explicit request.

## Required Save Targets

Daily report path pattern:

- Obsidian: `/Users/ganxuanzhi/Documents/Obsidian Vault/芯片互连资讯/output/YYYY-MM-DD.md`
- Learning repo mirror: `/Users/ganxuanzhi/学习/Learning_repo/芯片互连资讯/YYYY-MM-DD.md`
- Git research repo: `/Users/ganxuanzhi/学习/Short-Reach-Optical-Interconnect-Research/reports/daily/YYYY-MM-DD.md`

Weekly report path pattern:

- Obsidian: `/Users/ganxuanzhi/Documents/Obsidian Vault/芯片互连资讯/output/weekly-YYYY-WXX.md`
- Learning repo mirror: `/Users/ganxuanzhi/学习/Learning_repo/芯片互连资讯/weekly-YYYY-WXX.md`
- Git research repo: `/Users/ganxuanzhi/学习/Short-Reach-Optical-Interconnect-Research/reports/weekly/weekly-YYYY-WXX.md`

## Source Quality Order

When ranking and filtering information, use this authority order:

1. Standards bodies, conference papers, and official programs: OFC, ISSCC, DesignCon, ECOC, IEEE, OIF, OCP, UALink, UEC.
2. Company official announcements and product pages.
3. Reputable technology media and industry analysis.
4. Analyst blogs and social posts, only as trend context.

Do not invent technical specifications. If a metric is not present in a primary source, mark it as an analyst estimate or omit it.

## Report Quality Checklist

Before saving a report:

- Every item has a source URL.
- Papers include conference name, arXiv number, or official program reference when available.
- Daily reports include SerDes, optics/modules, AI servers, infrastructure, papers, vendors, events, and share cards.
- Weekly reports extract high-signal `🔥` and `⭐` items from daily reports and add deep-dive searches.
- Domestic and international vendors are both represented when relevant.
- Chinese is used for prose; technical terms may remain in English.

## Sync Checklist

After generating a report:

1. Save the canonical Markdown file to Obsidian output.
2. Copy the same content to the Learning repo mirror.
3. Copy the same content to this Git research repository.
4. Confirm all three files exist.
5. Count unique source links and report the count in the execution summary.
6. Commit and push the Git research repository so the report is maintained in the remote repository.
7. Include the commit hash and pushed branch in the execution summary.

## Git Rules

- Repository remote: `https://github.com/yuanfang11223344/Short-Reach-Optical-Interconnect-Research.git`
- Default local worktree: `/Users/ganxuanzhi/学习/Short-Reach-Optical-Interconnect-Research`
- Commit/push policy: generated reports and maintenance-rule updates for this topic are committed and pushed to this repository as part of the sync workflow.
- Confirmation-required operations: destructive commands, history rewrites, branch deletion, reset, force push, or overwriting upstream/local files outside the generated report and maintenance-rule scope.
- Upstream overwrite policy: check and report upstream state only; do not pull, reset, or overwrite without confirmation.
- Ignore `.DS_Store`, temporary downloads, browser caches, and generated scratch files.

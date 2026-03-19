---
name: web:report
description: Generate performance reports
argument-hint: "<workspace-name> [--period weekly|monthly|quarterly]"
---
<objective>
Generate a shareable content performance report.

Workspace: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/report-template.md
@./.claude/webos/references/BENCHMARKS.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // REPORT >>`
2. Load workspace: PERFORMANCE.md, CALENDAR.md, CHANNELS.md, SEO-STRATEGY.md, ROADMAP.md
3. Pull metrics for the reporting period
4. Generate report with sections:
   - Executive summary (3 bullets)
   - KPI dashboard (vs targets and benchmarks)
   - Channel breakdown
   - Top performing content
   - SEO progress
   - Content output vs plan
   - Key learnings
   - Next period priorities
5. Save to reports/
6. Offer: "Share via Slack? Export as markdown?"
</process>

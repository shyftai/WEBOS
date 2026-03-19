# Slack Notifications

## Configuration

Notifications are sent via Slack MCP server when available. Set up by connecting Slack MCP in Claude Code.

## Alert types

| Alert | Channel | Trigger |
|-------|---------|---------|
| Content due | #content | Content due date is today |
| Content overdue | #content | Past due date |
| Performance alert | #content-metrics | Traffic drop >20% or spike >50% |
| SEO alert | #seo | Keyword ranking drop >5 positions |
| Newsletter sent | #content | Newsletter published |
| Content published | #content | Any content published |
| Competitor alert | #content-intel | Competitor publishes new content |
| Trending topic | #content-intel | Relevant topic trending |

## Severity levels

| Level | When | Action |
|-------|------|--------|
| 🔴 Critical | Content errors live, major traffic drop | Immediate attention |
| 🟡 Warning | Overdue content, moderate drops | Address today |
| 🟢 Info | Published, performance updates | FYI |

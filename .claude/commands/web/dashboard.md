---
name: web:dashboard
description: Full workspace performance overview
argument-hint: "<workspace-name>"
---
<objective>
Complete performance dashboard. All metrics, all channels, all content.

Workspace: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< WEB:OS // DASHBOARD >>`
2. Load workspace: PERFORMANCE.md, CALENDAR.md, CHANNELS.md, SEO-STRATEGY.md, ROADMAP.md, LEARNINGS.md
3. Pull metrics from connected tools (Search Console, social APIs, newsletter platform)
4. Display comprehensive dashboard:

```
  ┌─ DASHBOARD ─── {workspace} ────────────────────┐
  │                                                  │
  │  TRAFFIC                                        │
  │  Organic: {n} sessions ({trend})                │
  │  Social: {n} sessions ({trend})                 │
  │  Newsletter: {n} clicks ({trend})               │
  │  Total: {n} ({trend})                           │
  │                                                  │
  │  CONTENT                                        │
  │  Published this month: {n} / {target}           │
  │  In pipeline: {n} drafts, {n} briefs            │
  │  Overdue: {n}                                   │
  │                                                  │
  │  SEO                                            │
  │  Keywords ranking: {n} ({+/-n})                 │
  │  Top 10 keywords: {n} ({+/-n})                  │
  │  Avg position: {n} ({trend})                    │
  │                                                  │
  │  SOCIAL                                         │
  │  Followers: {n} ({+/-n})                        │
  │  Avg engagement: {n}% ({trend})                 │
  │  Best post: {title} ({metric})                  │
  │                                                  │
  │  NEWSLETTER                                     │
  │  Subscribers: {n} ({+/-n})                      │
  │  Avg open rate: {n}%                            │
  │  Avg CTR: {n}%                                  │
  │                                                  │
  │  ROADMAP TO-DOS                                 │
  │  • {top 3 to-dos}                               │
  │                                                  │
  └──────────────────────────────────────────────────┘
```

5. Flag anomalies and opportunities
6. Suggest actions based on data
</process>

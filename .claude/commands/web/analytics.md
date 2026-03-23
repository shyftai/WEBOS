---
name: web:analytics
description: Pull and analyze web traffic and content metrics
argument-hint: "<workspace-name> [--period 7d|30d|90d]"
---
<objective>
Pull metrics from connected tools and analyze web content performance.

Workspace: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< WEB:OS // ANALYTICS >>`
2. Load workspace: PERFORMANCE.md, SEO-STRATEGY.md, SITE-ARCHITECTURE.md, CALENDAR.md
3. Pull data from available tools:
   - Search Console → organic traffic, keywords, CTR, position
   - Google Analytics → sessions, engagement, conversions
   - Ahrefs/SEMrush → rankings, backlinks, DR
   - PageSpeed → Core Web Vitals

4. Analyze:
   - **Trends:** What's going up/down vs previous period
   - **Top performers:** Best content by each metric
   - **Underperformers:** Content below benchmark
   - **SEO progress:** Ranking changes, new keywords, lost positions
   - **Conversion:** Which pages drive the most leads/conversions
   - **Alerts:** Significant drops or spikes

5. Display:
```
  ┌─ ANALYTICS ─── {period} ───────────────────────┐
  │                                                  │
  │  ORGANIC TRAFFIC                                │
  │  Sessions:    {n} ({trend} vs prior period)      │
  │  Visitors:    {n} ({trend})                      │
  │  Pages/session: {n}    Bounce: {n}%              │
  │  Conversions: {n}      CVR: {n}%                 │
  │                                                  │
  │  SEO SNAPSHOT                                   │
  │  Keywords top 10: {n} ({+/-n})                   │
  │  Keywords top 3:  {n} ({+/-n})                   │
  │  Avg position:    {n} ({+/-n})                   │
  │  Domain rating:   {n}                            │
  │                                                  │
  │  BY PAGE TYPE                                   │
  │  Blog:      {sessions} ({trend}) | Top: {title}  │
  │  Landing:   {sessions} ({trend}) | CVR: {rate}   │
  │  Docs:      {sessions} ({trend}) | Top: {title}  │
  │                                                  │
  │  BY PILLAR                                      │
  │  {Pillar 1}: {n} pages, {sessions}, {cvr}%       │
  │  {Pillar 2}: {n} pages, {sessions}, {cvr}%       │
  │                                                  │
  │  INSIGHTS                                       │
  │  • {actionable insight}                          │
  │  • {actionable insight}                          │
  │                                                  │
  └──────────────────────────────────────────────────┘
```

6. Update PERFORMANCE.md with latest data
7. Update LEARNINGS.md with any new insights
8. Add action items to ROADMAP.md
</process>

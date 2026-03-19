---
name: web:analytics
description: Pull and analyze content metrics
argument-hint: "<workspace-name> [--period 7d|30d|90d] [--channel all|blog|social|newsletter]"
---
<objective>
Pull metrics from connected tools and analyze content performance.

Workspace: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< WEB:OS // ANALYTICS >>`
2. Load workspace: PERFORMANCE.md, CHANNELS.md, SEO-STRATEGY.md, CALENDAR.md
3. Pull data from available tools:
   - Search Console → organic traffic, keywords, CTR, position
   - Google Analytics → sessions, engagement, conversions
   - Social APIs → followers, engagement, reach
   - Newsletter platform → subscribers, opens, clicks
   - Ahrefs/SEMrush → rankings, backlinks, DR

4. Analyze:
   - **Trends:** What's going up/down vs previous period
   - **Top performers:** Best content by each metric
   - **Underperformers:** Content below benchmark
   - **Opportunities:** Where to double down
   - **Alerts:** Significant drops or spikes

5. Display:
```
  ┌─ ANALYTICS ─── {period} ───────────────────────┐
  │                                                  │
  │  OVERVIEW                                       │
  │  Total reach: {n} ({trend})                     │
  │  Total engagement: {n} ({trend})                │
  │  New subscribers: {n} ({trend})                 │
  │  Content published: {n}                         │
  │                                                  │
  │  BY CHANNEL                                     │
  │  Blog: {sessions} ({trend}) | Top: {title}      │
  │  LinkedIn: {impressions} ({trend}) | Top: {post} │
  │  Newsletter: {opens} ({trend}) | Open: {rate}    │
  │  Twitter: {impressions} ({trend}) | Top: {post}  │
  │                                                  │
  │  BY PILLAR                                      │
  │  {Pillar 1}: {n} pieces, {avg engagement}        │
  │  {Pillar 2}: {n} pieces, {avg engagement}        │
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

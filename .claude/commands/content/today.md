---
name: content:today
description: Daily content briefing — what needs attention
argument-hint: "<workspace-name>"
---
<objective>
Daily action briefing. What's due, what's performing, what needs attention. Start every day here.

Workspace: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< CONTENT:OS // TODAY >>`
2. Load workspace context: CALENDAR.md, PERFORMANCE.md, LEARNINGS.md, ROADMAP.md, CHANNELS.md
3. Check all sources and build the briefing:

## Urgency tiers

### 🔴 DO NOW
- Content due today that isn't published
- Trending topics with time-sensitive opportunity
- Engagement spikes that need responses (comments, mentions)
- Content with errors live on site

### 🟡 TODAY
- Content in review that needs approval
- Scheduled posts to verify
- Social engagement to respond to
- Newsletter draft due this week
- Performance alerts (traffic drops, ranking changes)

### 🟢 THIS WEEK
- Upcoming content calendar items
- Keyword opportunities from search console
- Competitor content moves
- Roadmap to-dos
- Content to repurpose

4. Display:
```
  ┌─ TODAY ── {date} ──────────────────────────────┐
  │                                                 │
  │  🔴 DO NOW                                     │
  │  • {urgent item}                                │
  │                                                 │
  │  🟡 TODAY                                      │
  │  • {item}                                       │
  │                                                 │
  │  🟢 THIS WEEK                                  │
  │  • {item}                                       │
  │                                                 │
  │  📊 Quick stats (vs last week)                  │
  │  Traffic: {n} ({+/-n%})                         │
  │  Engagement: {n} ({+/-n%})                      │
  │  Subscribers: {n} ({+/-n%})                     │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

5. Role-aware emphasis:
   - **Content Creator:** Focus on drafts due, briefs to pick up
   - **Social Media Manager:** Focus on posting schedule, engagement
   - **SEO Specialist:** Focus on ranking changes, technical issues
   - **Head of Content:** Focus on pipeline, team blockers, KPIs
</process>

---
name: content:trends
description: Discover trending topics and content opportunities
argument-hint: "<workspace-name> [--source industry|social|search|news]"
---
<objective>
Find what's trending in your space. Surface content opportunities before competitors.

Workspace: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< CONTENT:OS // TRENDS >>`
2. Load workspace: PILLARS.md, AUDIENCE.md, COMPETITORS.md, SEO-STRATEGY.md, LEARNINGS.md
3. Scan available sources:
   - **Exa:** trending content in the industry
   - **Search Console:** rising queries
   - **Social:** trending hashtags, viral content in the niche
   - **Firecrawl:** competitor new content
   - **News:** industry news and events

4. Filter by relevance to content pillars and audience
5. Score each trend:
   - Relevance to pillars (high/medium/low)
   - Time sensitivity (urgent/this week/evergreen)
   - Competition (saturated/moderate/open)
   - Audience interest signal

6. Display:
```
  ┌─ TRENDING ─── {date} ──────────────────────────┐
  │                                                  │
  │  🔥 HOT NOW (time-sensitive)                    │
  │  1. {trend} — {why it matters} — {pillar}        │
  │  2. {trend} — {why it matters} — {pillar}        │
  │                                                  │
  │  📈 RISING (this week)                           │
  │  1. {trend} — {signal source} — {pillar}         │
  │                                                  │
  │  🌱 EMERGING (next 2-4 weeks)                    │
  │  1. {trend} — {early signal} — {pillar}          │
  │                                                  │
  │  >> Create brief for any of these?               │
  └──────────────────────────────────────────────────┘
```

7. Offer to create content briefs for selected trends
8. Add to ROADMAP.md ideas backlog
</process>

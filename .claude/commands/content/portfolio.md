---
name: content:portfolio
description: Multi-brand content dashboard (agency mode)
argument-hint: "[--view overview|brand-detail]"
---
<objective>
Multi-brand dashboard for agencies managing content across multiple workspaces.
</objective>

<process>
1. Display mode header: `<< CONTENT:OS // PORTFOLIO >>`
2. Scan all workspace folders
3. For each workspace, pull:
   - Publishing cadence (on track / behind / ahead)
   - Key metrics (traffic, engagement, subscribers)
   - Content pipeline status
   - Overdue items
   - Top performing content this period

4. Display:
```
  ┌─ PORTFOLIO ────────────────────────────────────┐
  │                                                 │
  │  {Brand 1}                                     │
  │  Status: 🟢 On track                           │
  │  Published: 12/15 this month                    │
  │  Traffic: 45K (+12%)                            │
  │  Action: 2 briefs need approval                 │
  │                                                 │
  │  {Brand 2}                                     │
  │  Status: 🟡 Behind schedule                     │
  │  Published: 4/10 this month                     │
  │  Traffic: 12K (-5%)                             │
  │  Action: 6 items overdue                        │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

5. Cross-brand learnings and patterns
6. Aggregate metrics
</process>

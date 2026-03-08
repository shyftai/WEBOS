---
name: content:competitor
description: Monitor competitor content strategy
argument-hint: "<workspace-name> [--competitor name-or-url]"
---
<objective>
Analyze competitor content strategy. Find gaps and opportunities.

Workspace: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< CONTENT:OS // COMPETITOR INTEL >>`
2. Load workspace: COMPETITORS.md, PILLARS.md, SEO-STRATEGY.md, LEARNINGS.md
3. Modes:
   - **Setup:** add a new competitor to monitor
   - **Scan:** check for new competitor content
   - **Deep dive:** full competitor content analysis

4. For scan/deep dive:
   - Crawl competitor site for new content (Firecrawl)
   - Check their social channels
   - Analyze their SEO strategy (Ahrefs/SEMrush)
   - Compare content calendar/frequency
   - Identify content gaps (topics they cover that we don't, and vice versa)

5. Display:
```
  ┌─ COMPETITOR INTEL ─── {competitor} ────────────┐
  │                                                 │
  │  NEW CONTENT                                   │
  │  • {title} — {date} — {channel}                │
  │                                                 │
  │  CONTENT GAPS (they have, we don't)            │
  │  • {topic} — {their URL} — opportunity: {high}  │
  │                                                 │
  │  OUR ADVANTAGES (we have, they don't)          │
  │  • {topic} — double down                        │
  │                                                 │
  │  SEO OVERLAP                                   │
  │  • {keyword} — them: #{n}, us: #{n}             │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

6. Update COMPETITORS.md with findings
7. Add content gap opportunities to ROADMAP.md
</process>

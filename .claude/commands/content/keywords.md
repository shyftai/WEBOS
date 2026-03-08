---
name: content:keywords
description: Keyword research and clustering
argument-hint: "<workspace-name> <seed-topic-or-keyword>"
---
<objective>
Research keywords, cluster them by intent, and identify content opportunities.

Workspace and topic: $ARGUMENTS
</objective>

<execution_context>
@./.claude/contentos/references/seo-playbook.md
</execution_context>

<process>
1. Display mode header: `<< CONTENT:OS // KEYWORDS >>`
2. Load workspace: SEO-STRATEGY.md, PILLARS.md, COMPETITORS.md, LEARNINGS.md
3. Research keywords using available tools:
   - Ahrefs/SEMrush API for volume and difficulty
   - Exa for related content and long-tail variations
   - Search Console for existing ranking keywords
   - Competitor analysis for gap keywords

4. Cluster keywords by:
   - **Search intent:** Informational, navigational, transactional, commercial
   - **Topic cluster:** Group related keywords under pillar topics
   - **Difficulty tier:** Easy wins, medium effort, long-term plays

5. Display results:
```
  ┌─ KEYWORD RESEARCH ─── "{topic}" ───────────────┐
  │                                                  │
  │  EASY WINS (difficulty <30, volume >100)         │
  │  • {keyword} — {volume}/mo, KD {n}              │
  │  • {keyword} — {volume}/mo, KD {n}              │
  │                                                  │
  │  MEDIUM EFFORT (difficulty 30-60)                │
  │  • {keyword} — {volume}/mo, KD {n}              │
  │                                                  │
  │  LONG-TERM (difficulty >60)                      │
  │  • {keyword} — {volume}/mo, KD {n}              │
  │                                                  │
  │  CONTENT OPPORTUNITIES                           │
  │  1. {keyword cluster} → {content type}           │
  │  2. {keyword cluster} → {content type}           │
  │                                                  │
  └──────────────────────────────────────────────────┘
```

6. Ask: "Add these to SEO-STRATEGY.md? (y/n)"
7. Generate content briefs for top opportunities if requested
8. Update ROADMAP.md with keyword-driven content ideas
</process>

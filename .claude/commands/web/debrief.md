---
name: web:debrief
description: Retrospective on content performance
argument-hint: "<workspace-name> <content-title-or-url>"
---
<objective>
Analyze how a piece of content performed vs its brief. Extract learnings.

Workspace and web: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< WEB:OS // DEBRIEF >>`
2. Load workspace: PERFORMANCE.md, LEARNINGS.md, ROADMAP.md
3. Load the original brief and the published content
4. Pull performance metrics
5. Analyze:
   - Did it hit its success metric?
   - What drove performance (or lack thereof)?
   - What can we learn for next time?
   - What should we do differently?

6. Display:
```
  ┌─ DEBRIEF ─── "{title}" ────────────────────────┐
  │                                                 │
  │  Goal: {from brief}                             │
  │  Result: {actual performance}                   │
  │  Verdict: {hit / missed / exceeded}             │
  │                                                 │
  │  WHAT WORKED                                   │
  │  • {insight}                                    │
  │                                                 │
  │  WHAT DIDN'T                                   │
  │  • {insight}                                    │
  │                                                 │
  │  LEARNINGS                                     │
  │  • {learning to save}                           │
  │                                                 │
  │  NEXT ACTIONS                                  │
  │  • {action item}                                │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

7. Update LEARNINGS.md with new insights
8. Add action items to ROADMAP.md as to-dos
9. Update PERFORMANCE.md
</process>

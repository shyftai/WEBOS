---
name: web:review
description: Quality check content before publishing
argument-hint: "<workspace-name> <content-file>"
---
<objective>
Run content through quality gates before publishing. Catch issues before they go live.

Workspace and web: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/writing-skill.md
@./.claude/webos/references/seo-playbook.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // REVIEW >>`
2. Load workspace: BRAND.md, TOV.md, AUDIENCE.md, SEO-STRATEGY.md
3. Load the content to review
4. Run all quality gates:

```
  ┌─ QUALITY REVIEW ───────────────────────────────┐
  │                                                 │
  │  [x] Brief check — matches original brief       │
  │  [x] Brand check — matches voice guidelines     │
  │  [ ] Audience check — ISSUE: too technical      │
  │  [x] SEO check — keyword, meta, headings OK     │
  │  [x] Readability — Grade 8, avg 16 words/sent   │
  │  [x] Source check — all claims cited             │
  │  [x] Channel check — formatted correctly        │
  │                                                 │
  │  Score: 6/7 — 1 issue to fix                    │
  │                                                 │
  │  ISSUES                                        │
  │  1. Audience: paragraph 3 uses jargon the       │
  │     target audience won't understand.           │
  │     Suggestion: {rewrite suggestion}            │
  │                                                 │
  └─────────────────────────────────────────────────┘

  >> Fix issues? (y/n)
```

5. Check execution mode from workspace.config.md:
   - **Interactive:** Present with approval gate above. Wait for user to confirm fixes.
   - **Auto:** Auto-approve fixes, apply them, show `⚡ Auto-approved: fixes applied`, log in logs/decisions.md
6. If issues found, suggest fixes
7. Re-run gates after fixes
8. When all gates pass: move to content/approved/
</process>

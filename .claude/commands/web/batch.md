---
name: web:batch
description: Batch content creation at scale
argument-hint: "<workspace-name> [--type social|blog-outlines|newsletters] [--count N]"
---
<objective>
Create content in batches. Multiple pieces at once for efficiency.

Workspace: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/writing-skill.md
@./.claude/webos/references/channel-specs.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // BATCH >>`
2. Load workspace: BRAND.md, TOV.md, AUDIENCE.md, PILLARS.md, CALENDAR.md, LEARNINGS.md
3. Ask what to batch:
   - Social posts (week/month of content)
   - Blog outlines (from keyword clusters)
   - Newsletter editions (month ahead)
   - Repurposed variants (one piece → many channels)

4. Scale mode (if count >25):
```
  {n} pieces to create. How do you want to run this?

  >> Claude Code — runs here, review in real time
     Best for: <25 pieces, interactive review

  >> API — runs via Anthropic API, faster at scale
     Best for: 25-100+ pieces, batch processing
     Requires: ANTHROPIC_API_KEY in .env
```

5. Generate all pieces following brand, TOV, and channel specs
6. Present for review in batches
7. Save approved pieces
8. Update CALENDAR.md with scheduling
</process>

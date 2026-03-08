---
name: content:repurpose
description: Transform content across channels
argument-hint: "<workspace-name> <content-file> [--channels linkedin,twitter,newsletter]"
---
<objective>
Take one piece of content and transform it for multiple channels. One piece, many formats.

Workspace and content: $ARGUMENTS
</objective>

<execution_context>
@./.claude/contentos/references/channel-specs.md
@./.claude/contentos/references/writing-skill.md
</execution_context>

<process>
1. Display mode header: `<< CONTENT:OS // REPURPOSE >>`
2. Load workspace: BRAND.md, TOV.md, CHANNELS.md, LEARNINGS.md
3. Load the source content
4. Ask which channels to repurpose for (or use --channels flag):
   - LinkedIn post / carousel / article
   - Twitter/X thread / single tweet
   - Newsletter section / feature
   - Instagram caption / carousel
   - YouTube script / shorts script
   - Community post (Reddit, Discord)
   - Slide deck key points

5. For each target channel:
   a. Load channel specs (character limits, format, best practices)
   b. Extract the core message and key points
   c. Rewrite for the channel's format and audience behavior
   d. Adjust tone per channel (from TOV.md channel adjustments)
   e. Add platform-specific elements (hashtags, emojis, hooks)

6. Display all versions for review:
```
  ── ORIGINAL (Blog) ──────────────────────────────
  {title and first paragraph}

  ── LINKEDIN ─────────────────────────────────────
  {full LinkedIn post}

  ── TWITTER THREAD ───────────────────────────────
  1/ {tweet 1}
  2/ {tweet 2}
  ...

  ── NEWSLETTER ───────────────────────────────────
  {newsletter version}

  >> Approve all / Edit / Select specific
```

7. Save approved versions to content/approved/
8. Add to CALENDAR.md for scheduling
</process>

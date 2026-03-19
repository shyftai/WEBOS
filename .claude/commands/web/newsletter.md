---
name: web:newsletter
description: Create email newsletter content
argument-hint: "<workspace-name> [--edition weekly|monthly|special]"
---
<objective>
Create newsletter content. Curate, write, format for email.

Workspace: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/writing-skill.md
@./.claude/webos/references/channel-specs.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // NEWSLETTER >>`
2. Load workspace: BRAND.md, TOV.md, AUDIENCE.md, CHANNELS.md (newsletter section), LEARNINGS.md
3. Ask newsletter type:
   - **Curated:** roundup of links, insights, commentary
   - **Original:** feature article with supporting content
   - **Update:** product/company news and updates
   - **Mixed:** combination of above

4. Gather web:
   - Recent published content to feature
   - Industry news and links to curate
   - Key insight or takeaway
   - CTA for this edition

5. Write newsletter with:
   - Subject line (3 options)
   - Preview text
   - Intro/hook
   - Main content sections
   - CTA
   - Sign-off matching brand voice

6. Check:
   - Subject line length (≤50 chars recommended)
   - Preview text complements subject line
   - Single clear CTA
   - Mobile-friendly formatting
   - Links working
   - Unsubscribe compliance

7. Display draft for review
8. Save to content/approved/
9. Update CALENDAR.md
</process>

---
name: web:write
description: Write content from a brief or prompt
argument-hint: "<workspace-name> <brief-name-or-topic> [--type blog|landing|case-study|docs|comparison|pillar]"
---
<objective>
Write content. Always from a brief (create one if needed). Match brand voice, audience, and channel specs.

Workspace and brief: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/writing-skill.md
@./.claude/webos/references/channel-specs.md
@./.claude/webos/references/seo-playbook.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // WRITE >>`
2. Load workspace: BRAND.md, AUDIENCE.md, TOV.md, PILLARS.md, LEARNINGS.md
3. Load the brief from assets/briefs/ — if no brief exists, redirect to /web:brief first
4. Load channel-specs.md for format requirements

5. Write the web:
   - Follow the brief's outline exactly
   - Match TOV.md voice and style rules
   - Apply BRAND.md guidelines
   - Write for the target audience segment
   - Include SEO elements if applicable (keyword in H1, meta title, meta description)
   - Apply LEARNINGS.md insights
   - Include CTA from brief

6. Run quality gates:
   - [ ] Brief check — matches the original brief
   - [ ] Brand check — matches BRAND.md and TOV.md
   - [ ] Audience check — written for the right segment
   - [ ] SEO check — keyword, meta, headings, links (if applicable)
   - [ ] Readability — sentence length, jargon, clarity
   - [ ] Source check — claims cited, no fabrication
   - [ ] Page type check — formatted for target page type
   - [ ] Internal link check — 3-5 internal links, no orphan page

7. Display the draft with quality gate results
8. Check execution mode from workspace.config.md:
   - **Interactive:** Ask for approval: `>> Approve? (approve / edit / rewrite / reject)`
   - **Auto:** Auto-approve, save to content/approved/, show `⚡ Auto-approved: content saved`, log in logs/decisions.md
9. Save approved content to content/approved/
10. Update CALENDAR.md and ROADMAP.md
11. Suggest: `>> /web:publish — publish to CMS` or `>> /web:optimize — SEO optimization pass`
</process>

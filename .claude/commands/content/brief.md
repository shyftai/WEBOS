---
name: content:brief
description: Create a content brief for any piece
argument-hint: "<workspace-name> <topic-or-title> [--channel blog|social|newsletter]"
---
<objective>
Create a structured content brief. Every piece of content starts here. No writing without a brief.

Workspace and topic: $ARGUMENTS
</objective>

<execution_context>
@./.claude/contentos/references/writing-skill.md
@./.claude/contentos/references/seo-playbook.md
@./.claude/contentos/references/content-frameworks.md
</execution_context>

<process>
1. Display mode header: `<< CONTENT:OS // BRIEF >>`
2. Load workspace: BRAND.md, AUDIENCE.md, PILLARS.md, TOV.md, CHANNELS.md, SEO-STRATEGY.md, LEARNINGS.md

3. Gather brief inputs (ask if not provided):
   - **Topic/title:** What is this about?
   - **Channel:** Where will this live? (blog, LinkedIn, newsletter, etc.)
   - **Content type:** Article, how-to, case study, listicle, opinion, thread, carousel, etc.
   - **Target audience:** Which audience segment?
   - **Content pillar:** Which pillar does this map to?
   - **Goal:** What should this content achieve? (traffic, engagement, leads, authority)
   - **Success metric:** How will we measure success? (views, shares, ranking, conversions)

4. If blog/long-form:
   - **Target keyword:** Primary keyword to rank for
   - **Search intent:** Informational / navigational / transactional
   - **Word count:** Recommended based on SERP analysis
   - **Competing content:** Top 3 ranking pages for this keyword

5. Generate the brief:
```
  ┌─ CONTENT BRIEF ────────────────────────────────┐
  │                                                 │
  │  Title: {working title}                         │
  │  Channel: {channel}                             │
  │  Type: {content type}                           │
  │  Pillar: {content pillar}                       │
  │  Audience: {segment}                            │
  │                                                 │
  │  GOAL                                          │
  │  {what this piece should achieve}               │
  │                                                 │
  │  SUCCESS METRIC                                │
  │  {how we measure success}                       │
  │                                                 │
  │  KEY MESSAGES                                  │
  │  1. {main point}                                │
  │  2. {supporting point}                          │
  │  3. {supporting point}                          │
  │                                                 │
  │  OUTLINE                                       │
  │  H1: {title}                                    │
  │    H2: {section}                                │
  │    H2: {section}                                │
  │    H2: {section}                                │
  │                                                 │
  │  SEO (if applicable)                           │
  │  Keyword: {primary} ({volume}, {difficulty})    │
  │  Secondary: {list}                              │
  │  Intent: {type}                                 │
  │  Word count: {n}                                │
  │                                                 │
  │  CTA                                           │
  │  {what the reader should do next}               │
  │                                                 │
  │  REFERENCES                                    │
  │  • {sources to reference}                       │
  │                                                 │
  │  BRAND NOTES                                   │
  │  {any brand-specific considerations}            │
  │                                                 │
  └─────────────────────────────────────────────────┘

  >> Approve brief? (y/n/edit)
```

6. Check execution mode from workspace.config.md:
   - **Interactive:** Present with approval gate above. On approval, save to assets/briefs/
   - **Auto:** Auto-approve, save to assets/briefs/, show `⚡ Auto-approved: brief saved`, log in logs/decisions.md
7. Save approved brief to assets/briefs/
8. Add to CALENDAR.md and ROADMAP.md
9. Display next step: `>> /content:write {workspace} {brief-name}`
</process>

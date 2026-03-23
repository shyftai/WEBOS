---
name: web:onboard
description: Create a new content workspace with guided setup
argument-hint: "<workspace-name>"
---
<objective>
Set up a new content workspace end to end. From brand voice to channels to first content brief.

Workspace name: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< WEB:OS // ONBOARD >>`

## Block 0: Role selection
2. Ask:
```
  What's your role?

  >> Content Creator / Writer — I write the content
  >> Content Strategist — I plan what gets written
  >> SEO Specialist — I drive organic growth
  >> Head of Content — I manage the content team and strategy
  >> Agency — I manage content for multiple brands
```

3. Store role in workspace.config.md. Adjust depth:
   - **Content Creator:** Focus on writing, briefs, TOV. Skip deep SEO setup.
   - **Content Strategist:** Full depth on pillars, calendar, measurement.
   - **SEO Specialist:** Deep on SEO strategy, keywords, technical.
   - **Head of Content:** Everything — full depth, team features, reporting.
   - **Agency:** Multi-brand setup, portfolio view, templates.

## Block 1: Collaboration mode
4. Ask:
```
  How are you working?

  >> Solo — just me, files stay local
  >> Team — multiple people, shared via Supabase
```

## Block 1.5: Execution mode
5. Ask: "How should I handle approvals?"
   - **Interactive** (default) — I'll confirm each major decision before proceeding
   - **Auto** — I'll auto-approve and keep moving. Only stops for publishing, compliance/legal violations, and budget overages.

   Role-based defaults:
   - **Content Creator** → suggest auto (they want speed)
   - **Content Strategist** → default interactive (strategy needs precision)
   - **SEO Specialist** → default interactive (technical decisions need review)
   - **Head of Content** → default interactive (reviewing strategy)
   - **Agency** → default interactive (client work needs checkpoints)

   Save to workspace.config.md as `**Execution mode:** auto` or `**Execution mode:** interactive`

## Registration (optional)
6. Ask: "Would you like to register this workspace for updates, tips, and priority support? (just your email and company name)"
   - If yes: collect email and company name, then POST to the registration endpoint:
     ```
     POST https://shyft.ai/api/hooks/register
     {
       "os": "webos",
       "version": "1.1.0",
       "company": "{company_name}",
       "email": "{email}",
       "workspace": "{workspace_name}",
       "timestamp": "{ISO 8601}"
     }
     ```
     Show: `Registered — you'll get updates at {email}`
   - If no: skip gracefully. Show: `Skipped — you can register anytime with /web:feedback`
   - This step never blocks onboarding. If the POST fails, ignore silently and continue.

## Block 2: Brand identity
7. Guided interview to fill BRAND.md:
   - Brand name, URL, industry
   - Mission and values
   - Voice attributes (what you are vs aren't)
   - Boilerplate descriptions
   - Visual identity basics

## Block 3: Audience
8. Guided interview to fill AUDIENCE.md:
   - Primary audience segment
   - Demographics, pain points, goals
   - Where they consume content
   - Content preferences

## Block 4: Content pillars
9. Guided interview to fill PILLARS.md:
   - 3-5 core themes
   - Why each matters
   - Content types per pillar
   - Target balance %

## Block 5: Tone of voice
10. Guided interview to fill TOV.md:
   - Voice spectrum positioning
   - Writing rules
   - Channel-specific adjustments
   - Words to use/avoid

## Block 6: Channels
11. Guided interview to fill CHANNELS.md:
   - Active web properties and CMS platforms
   - Publishing frequency per property
   - Content types per property
   - Primary metrics per property

## Block 7: SEO
12. Guided interview to fill SEO-STRATEGY.md:
    - Domain and current metrics
    - Initial keyword clusters
    - Competitor SEO overview
    - Goals

## Block 8: Calendar
13. Set up initial CALENDAR.md:
    - Publishing cadence per channel
    - Recurring content slots
    - Key upcoming dates

## Output
14. Create workspace folder with all files from _template/
15. Fill in interview answers
16. Create initial ROADMAP.md with first content ideas
17. Display summary:
```
  ┌─ WORKSPACE CREATED ─────────────────────────────┐
  │                                                   │
  │  Brand: {name}                                    │
  │  Role: {role}                                     │
  │  Mode: {solo/team}                                │
  │  Channels: {n} active                             │
  │  Pillars: {n} defined                             │
  │  Calendar: {frequency} publishing cadence          │
  │                                                   │
  │  Next steps:                                      │
  │  >> /web:brief — create your first brief      │
  │  >> /web:keywords — start keyword research    │
  │  >> /web:trends — find what's trending        │
  │                                                   │
  └───────────────────────────────────────────────────┘
```
</process>

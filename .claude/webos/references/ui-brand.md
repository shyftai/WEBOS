<ui_patterns>

Visual patterns for user-facing WEB:OS output. All commands @-reference this file.

## Brand Color

WEB:OS brand color is **teal/emerald** (ANSI 43).
- Use `\033[38;5;43m` to set teal text, `\033[0m` to reset
- Apply teal to: the WEB:OS block-letter banner, mode headers (`<< WEB:OS // MODE >>`), section titles in dashboards
- Use white/default for: body text, data values, box borders
- If terminal doesn't support color, display everything in plain white
- Never use orange, green, or red as brand colors — those are reserved for status indicators

## Startup Banner

Display once when WEB:OS loads. Render the block letters in teal.

```
 ██████╗ ██████╗ ███╗   ██╗████████╗███████╗███╗   ██╗████████╗
██╔════╝██╔═══██╗████╗  ██║╚══██╔══╝██╔════╝████╗  ██║╚══██╔══╝
██║     ██║   ██║██╔██╗ ██║   ██║   █████╗  ██╔██╗ ██║   ██║
██║     ██║   ██║██║╚██╗██║   ██║   ██╔══╝  ██║╚██╗██║   ██║
╚██████╗╚██████╔╝██║ ╚████║   ██║   ███████╗██║ ╚████║   ██║
 ╚═════╝ ╚═════╝ ╚═╝  ╚═══╝   ╚═╝   ╚══════╝╚═╝  ╚═══╝   ╚═╝
       ██╗  ██████╗ ███████╗
       ╚═╝ ██╔═══██╗██╔════╝
           ██║   ██║███████╗
       ██╗ ██║   ██║╚════██║
       ╚═╝ ╚██████╔╝███████║
            ╚═════╝ ╚══════╝
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  C O N T E N T : O S
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## Mode Headers

Use for workflow transitions. WEB:OS uses angle brackets.

```
<< WEB:OS // {MODE NAME} >>
```

**Mode names (uppercase, rendered in teal):**
- `ONBOARDING`
- `RESEARCH`
- `BRIEF`
- `WRITE`
- `REVIEW`
- `PUBLISH`
- `REPURPOSE`
- `BATCH`
- `SEO AUDIT`
- `KEYWORDS`
- `OPTIMIZE`
- `CLUSTER`
- `CALENDAR`
- `SOCIAL`
- `COMMUNITY`
- `TRENDS`
- `COMPETITOR`
- `ANALYTICS`
- `REPORT`
- `DEBRIEF`
- `NEWSLETTER`
- `DASHBOARD`
- `PORTFOLIO`
- `SWARM`
- `COMPLIANCE`
- `FEEDBACK`

---

## System Flow Diagram

Show below the banner on startup. Includes swarm and calendar.

```
  ┌──────────────────────────────────────────────────┐
  │  BRAND ─── AUDIENCE ─── PILLARS ─── TOV         │
  │                  │                               │
  │              STRATEGY                            │
  │                  │                               │
  │     ┌────────────┼────────────┐                  │
  │     ▼            ▼            ▼                  │
  │   RESEARCH     WRITE       METRICS               │
  │     │            │            │                  │
  │     ▼            ▼            ▼                  │
  │  IDEATE ──── CREATE ──── PUBLISH                 │
  │                  │            │                  │
  │             REPURPOSE    ◈ SWARM                 │
  │                  │       (optional)              │
  │           PERFORMANCE                            │
  │                  │                               │
  │           OPTIMIZE + LEARN                       │
  │                  │                               │
  │             CALENDAR ──── CHANNELS               │
  └──────────────────────────────────────────────────┘
```

---

## Workspace Header

Show after loading a workspace. Always displayed before any task.

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  WORKSPACE: {Name}                                         ┃
┃  PILLARS:   {Active content pillars}                       ┃
┃  STATUS:    {active/paused}         TOOLS: {tool list}     ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛
```

---

## Approval Gates

When human decision is needed. Uses double borders.

**Interactive mode:**
```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  APPROVAL REQUIRED                                         ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

{What is being approved}

>> Approve / Edit / Reject
```

**Auto mode:** Skip the gate — auto-approve and continue. Show a one-line confirmation instead:
```
>> Auto-approved: {what was approved}
```
Log the auto-approval in `logs/decisions.md` with timestamp and what was approved.

**Hard gates (always stop, even in auto mode):**
- `/web:publish` — pushing live content to any platform
- Compliance/legal violations — copyright, licensing, legal claims, disclosures
- Budget overages — spend exceeds workspace budget

Hard gates always use the full approval gate format above, regardless of execution mode.

---

## Credit Check

Before any tool write operation.

```
  ┌ CREDIT CHECK ─────────────────────────────────┐
  │ Tool:   {tool name}                            │
  │ Action: {what will happen}                     │
  │ Cost:   {record count or credit estimate}      │
  │ Rule:   {confirm-before-every-use / auto / ..} │
  └────────────────────────────────────────────────┘
  >> Proceed? (y/n)
```

---

## Quality Gates Display

Run before any content is marked "approved". Compact inline format.

```
  ── QUALITY GATES ──────────────────────────────────
  [x] Brief fit      [x] Brand fit     [x] Audience fit
  [x] SEO fit        [x] Readability   [x] Sources
  [x] Channel fit
  ───────────────────────────────────────────────────
```

If a check fails:
```
  ── QUALITY GATES ──────────────────────────────────
  [x] Brief fit      [x] Brand fit     [x] Audience fit
  [ ] SEO fit        [x] Readability   [x] Sources
  [x] Channel fit
  ───────────────────────────────────────────────────
  !! SEO: Missing target keyword in H1 and meta description
```

---

## Completion Summary

Always at end of a completed workflow.

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

  >> Next: {suggested next command}
     Also: {alternative command}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Status Symbols

```
[x]  Passed / Complete
[ ]  Failed / Missing
[~]  Borderline / Needs review
>>   Action prompt — waiting for human input
!!   Warning or flag
--   Skipped / Not applicable
```

---

## Swarm Display

Spawning indicator:
```
  << WEB:OS // SWARM >>

  Spawning 4 agents...
    [~] Agent 1: pieces 1-10
    [~] Agent 2: pieces 11-20
    [~] Agent 3: pieces 21-30
    [~] Agent 4: pieces 31-38
```

Progress updates as agents complete:
```
    [x] Agent 1: pieces 1-10    — 10 drafts, 0 flags
    [x] Agent 2: pieces 11-20   — 9 drafts, 1 flag
    [x] Agent 3: pieces 21-30   — 10 drafts, 0 flags
    [~] Agent 4: pieces 31-38
```

Swarm results summary:
```
  ┌─ SWARM RESULTS ───────────────────────────────┐
  │                                                │
  │  Agents spawned:  4                            │
  │  Pieces created:  38                           │
  │  Ready for review: 35                          │
  │  Flagged:         3 (need manual review)       │
  │  Errors:          0                            │
  │                                                │
  └────────────────────────────────────────────────┘

  >> Options:
     1. Review all 38 pieces one by one
     2. Approve all clean pieces, review flagged only
     3. Export all pieces for offline review
```

---

## Anti-Patterns — What WEB:OS never does

- Never use `GSD >` prefix — that is GSD's brand
- Never use `<< GTM:OS //` prefix — that is GTM:OS's brand
- Never use random emoji (no rockets, sparkles, stars)
- Never vary box widths within the same output
- Never skip the quality gates display on content output
- Never show tool links as bare URLs in paragraphs — always use a tool link box

</ui_patterns>

---
name: content:calendar
description: View and manage content calendar
argument-hint: "<workspace-name> [--view week|month] [--action add|reschedule|remove]"
---
<objective>
View and manage the content calendar. See what's planned, what's due, what's overdue.

Workspace: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< CONTENT:OS // CALENDAR >>`
2. Load workspace: CALENDAR.md, ROADMAP.md, CHANNELS.md
3. Display calendar view:

```
  ┌─ CONTENT CALENDAR ─── {month} ────────────────┐
  │                                                 │
  │  MON    TUE    WED    THU    FRI    SAT   SUN  │
  │  ┌──────┬──────┬──────┬──────┬──────┬─────┬───┐│
  │  │ Blog │      │ LI   │      │ NL   │     │   ││
  │  │ "..." │      │ post │      │ send │     │   ││
  │  ├──────┼──────┼──────┼──────┼──────┼─────┼───┤│
  │  │      │ TW   │ Blog │ LI   │      │     │   ││
  │  │      │ thrd │ "..." │ post │      │     │   ││
  │  └──────┴──────┴──────┴──────┴──────┴─────┴───┘│
  │                                                 │
  │  OVERDUE: {n} items                             │
  │  THIS WEEK: {n} items                           │
  │  PIPELINE: {n} briefs, {n} drafts               │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

4. Actions:
   - **Add:** add content to a date
   - **Reschedule:** move content to different date
   - **Remove:** remove from calendar
   - **View pipeline:** show full content pipeline by status

5. Update CALENDAR.md with changes
</process>

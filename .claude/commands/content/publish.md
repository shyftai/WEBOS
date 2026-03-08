---
name: content:publish
description: Publish or schedule content
argument-hint: "<workspace-name> <content-file> [--schedule datetime]"
---
<objective>
Publish content or schedule it for later. Final checks before going live.

Workspace and content: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< CONTENT:OS // PUBLISH >>`
2. Load workspace: CHANNELS.md, CALENDAR.md, BRAND.md
3. Load the approved content from content/approved/

4. Launch check:
```
  ┌─ LAUNCH CHECK ─────────────────────────────────┐
  │                                                 │
  │  [x] Content approved (quality gates passed)    │
  │  [x] Formatted for target channel               │
  │  [x] Links verified                             │
  │  [x] Images/media ready                         │
  │  [x] Meta title and description set              │
  │  [x] CTA included                               │
  │  [x] Calendar slot confirmed                     │
  │  [ ] Cross-promotion planned                     │
  │                                                 │
  │  Score: 7/8 — ready to publish                   │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

5. If publishing via API (WordPress, Buffer, etc.):
   - Confirm platform and credentials
   - Preview the formatted version
   - Publish or schedule

6. If manual publishing:
   - Provide copy-ready formatted version
   - Include all metadata
   - Checklist for manual steps

7. Update CALENDAR.md (mark as published)
8. Move content from approved/ to published/
9. Suggest: "Set a reminder to check performance in 7 days? /content:debrief"
</process>

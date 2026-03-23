---
name: web:publish
description: Publish or schedule content
argument-hint: "<workspace-name> <content-file> [--schedule datetime]"
---
<objective>
Publish content or schedule it for later. Final checks before going live.

Workspace and web: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< WEB:OS // PUBLISH >>`
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
  │  [ ] Internal links verified                      │
  │                                                 │
  │  Score: 7/8 — ready to publish                   │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

5. **HARD GATE — always stops, even in auto mode.**
   Publishing pushes live content. Always require explicit approval before proceeding.
   Show: `>> Confirm publish? This is a hard gate — auto mode does not skip this. (publish / schedule / cancel)`

6. If publishing via API (WordPress, Webflow, etc.):
   - Confirm platform and credentials
   - Preview the formatted version
   - Publish or schedule

7. If manual publishing:
   - Provide copy-ready formatted version
   - Include all metadata
   - Checklist for manual steps

8. Update CALENDAR.md (mark as published)
9. Move content from approved/ to published/
10. Suggest: "Set a reminder to check performance in 7 days? /web:debrief"
</process>

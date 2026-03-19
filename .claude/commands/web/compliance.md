---
name: web:compliance
description: Configure content compliance and brand safety rules
argument-hint: "[workspace-name]"
---
<objective>
Manage content compliance settings — brand guidelines, legal disclaimers, platform rules, copyright.
</objective>

<process>
1. Display: `<< WEB:OS // COMPLIANCE >>`
2. Load workspace BRAND.md and platform rules from CHANNELS.md
3. Check: disclosure requirements (sponsored content, affiliate links)
4. Check: copyright and attribution standards
5. Check: platform-specific content policies
6. Check: accessibility requirements (alt text, captions)
7. Display compliance status:

```
  ┌─ COMPLIANCE STATUS ─────────────────────────────┐
  │                                                  │
  │  Workspace: {name}                               │
  │                                                  │
  │  Brand Safety                                    │
  │  [x] Brand guidelines loaded (BRAND.md)          │
  │  [x] Tone of voice defined (TOV.md)              │
  │  [ ] Visual identity specs                       │
  │                                                  │
  │  Legal & Disclosure                              │
  │  [x] Sponsored content disclosure rules          │
  │  [ ] Affiliate link disclosure policy            │
  │  [x] Copyright attribution standards             │
  │                                                  │
  │  Platform Policies                               │
  │  [x] Channel-specific content rules              │
  │  [ ] Platform ToS compliance notes               │
  │                                                  │
  │  Accessibility                                   │
  │  [ ] Alt text requirements defined               │
  │  [ ] Caption/subtitle policy                     │
  │  [ ] Reading level target set                    │
  │                                                  │
  │  Score: {n}/{total} checks passing               │
  │                                                  │
  └──────────────────────────────────────────────────┘
```

8. Save compliance settings to workspace config
9. Suggest fixes for any failing checks
</process>

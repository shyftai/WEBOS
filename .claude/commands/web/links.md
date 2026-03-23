---
name: web:links
description: Internal link graph analysis — orphans, depth, coverage
argument-hint: "<workspace-name>"
---
<objective>
Audit internal linking structure — find orphan pages, assess click depth, check cluster coverage, and identify linking opportunities.

Workspace: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/distribution-playbook.md
@./.claude/webos/references/BENCHMARKS.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // LINKS >>`
2. Load workspace: SITE-ARCHITECTURE.md, SEO-STRATEGY.md, PILLARS.md
3. Analyze internal link structure:

   **Orphan pages:** Pages with 0 internal links pointing to them
   **Thin pages:** Pages with <2 internal links
   **Click depth:** How many clicks from homepage to reach each page
   **Cluster coverage:** Do all cluster pages link to their pillar? Does the pillar link to all clusters?
   **Broken internal links:** Links pointing to 404s or redirects
   **Anchor text diversity:** Are we over-using the same anchor text?

4. Present findings:

```
┌─ INTERNAL LINK AUDIT ──────────────────────────────────┐
│                                                         │
│  Total pages:       {n}                                 │
│  Avg links/page:    {n}                                 │
│  Orphan pages:      {n}    ({list if ≤10})              │
│  Thin pages (<2):   {n}                                 │
│  Max click depth:   {n}    (target: ≤3)                 │
│  Broken links:      {n}                                 │
│                                                         │
│  Cluster coverage:                                      │
│  {Pillar 1}: {n}/{n} clusters linked ({pct}%)           │
│  {Pillar 2}: {n}/{n} clusters linked ({pct}%)           │
│                                                         │
│  Status: {HEALTHY / NEEDS WORK / CRITICAL}              │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

5. For each orphan/thin page, suggest specific pages to link from
6. For each broken link, provide the source page and suggested fix
7. Generate a linking action plan:
   - Pages that need new inbound links (prioritized by traffic potential)
   - Existing pages to update with links to recent content
   - Cross-cluster linking opportunities
8. Save audit to `reports/links-{date}.md`
9. Update SITE-ARCHITECTURE.md with current link metrics
</process>

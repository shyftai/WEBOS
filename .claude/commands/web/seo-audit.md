---
name: web:seo-audit
description: Audit a page or site for SEO issues
argument-hint: "<workspace-name> <url-or-page> [--depth full|quick]"
---
<objective>
SEO audit — find what's working, what's broken, and what to fix.

Workspace and target: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/seo-playbook.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // SEO AUDIT >>`
2. Load workspace: SEO-STRATEGY.md, PERFORMANCE.md, LEARNINGS.md
3. Determine scope: single page or full site audit

## Single page audit
4. Fetch the page (Firecrawl or direct)
5. Check:
   - Meta title (exists, length ≤60, includes keyword)
   - Meta description (exists, length ≤155, compelling)
   - H1 (single, includes keyword)
   - Heading hierarchy (proper H1 → H2 → H3)
   - Keyword usage (natural, not stuffed)
   - Internal links (count, relevance)
   - External links (count, authority)
   - Image alt text
   - Word count vs competitors
   - Readability score
   - Schema markup
   - Core Web Vitals indicators

## Full site audit
6. Crawl key pages and check:
   - All single-page items above, aggregated
   - Sitemap completeness
   - Orphan pages
   - Thin content pages
   - Duplicate content
   - Broken links
   - Redirect chains
   - Cannibalization (pages competing for same keyword)

7. Display results:
```
  ┌─ SEO AUDIT ─── {url} ─────────────────────────┐
  │                                                 │
  │  Score: {n}/100                                 │
  │                                                 │
  │  🔴 Critical ({n})                              │
  │  • {issue}                                      │
  │                                                 │
  │  🟡 Warnings ({n})                              │
  │  • {issue}                                      │
  │                                                 │
  │  🟢 Passing ({n})                               │
  │  • {item}                                       │
  │                                                 │
  │  RECOMMENDATIONS                                │
  │  1. {fix with estimated impact}                 │
  │  2. {fix with estimated impact}                 │
  │                                                 │
  └─────────────────────────────────────────────────┘
```

8. Save audit to reports/
9. Add fix items to ROADMAP.md as to-dos
10. Update LEARNINGS.md with any SEO insights
</process>

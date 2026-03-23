---
name: web:crawl
description: Check crawl health, sitemap status, and index coverage
argument-hint: "<workspace-name>"
---
<objective>
Audit crawl health — sitemap coverage, index status, crawl errors, and robots.txt configuration.

Workspace: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/seo-playbook.md
@./.claude/webos/references/BENCHMARKS.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // CRAWL >>`
2. Load workspace: SEO-STRATEGY.md, SITE-ARCHITECTURE.md, PERFORMANCE.md
3. Check the following:

   **Sitemap health:**
   - Sitemap exists and is submitted to GSC
   - All intended pages are in the sitemap
   - No 404s, redirects, or noindex pages in sitemap
   - Sitemap is current (last modified date)

   **Index coverage:**
   - Pages submitted vs pages indexed
   - Index bloat check (more indexed than intended?)
   - Crawl coverage ratio
   - Pages excluded and reasons (noindex, canonical, redirect, etc.)

   **Robots.txt:**
   - Not blocking important pages
   - Blocking admin/staging/duplicate pages correctly
   - Sitemap reference present

   **Crawl errors:**
   - 4xx errors (broken pages)
   - 5xx errors (server issues)
   - Redirect chains and loops
   - Soft 404s

4. Present findings:

```
┌─ CRAWL HEALTH ─────────────────────────────────────────┐
│                                                         │
│  Sitemap:     {n} pages submitted                       │
│  Indexed:     {n} pages ({pct}% coverage)               │
│  Excluded:    {n} pages                                 │
│  Errors:      {n} 4xx · {n} 5xx · {n} redirect chains  │
│                                                         │
│  Status: {HEALTHY / NEEDS ATTENTION / CRITICAL}         │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

5. List specific issues with fix recommendations
6. Save audit to `reports/crawl-{date}.md`
7. Update PERFORMANCE.md with crawl metrics
</process>

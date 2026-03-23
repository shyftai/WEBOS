---
name: web:vitals
description: Core Web Vitals audit and recommendations
argument-hint: "<workspace-name> [--url <page-url>] [--site]"
---
<objective>
Audit Core Web Vitals for a specific page or entire site. Identify performance bottlenecks and provide actionable fixes.

Workspace and target: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/BENCHMARKS.md
@./.claude/webos/references/defaults.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // VITALS >>`
2. Load workspace: PERFORMANCE.md, SEO-STRATEGY.md, SITE-ARCHITECTURE.md
3. Determine scope:
   - **Single page:** Audit one URL for LCP, INP, CLS, TTFB, FCP
   - **Site-wide:** Audit homepage + top 10 traffic pages
4. For each page, check:
   - LCP: What's the largest element? Image, text block, video?
   - INP: Any heavy JavaScript blocking interaction?
   - CLS: Layout shifts from images without dimensions, dynamic content, fonts?
   - TTFB: Server response time, CDN coverage
   - FCP: Render-blocking resources, critical CSS
5. Present findings:

```
┌─ CORE WEB VITALS ─────────────────────────────────────┐
│                                                        │
│  Page: {url}                                           │
│                                                        │
│  LCP     {n}s    {PASS/FAIL}   {element causing it}   │
│  INP     {n}ms   {PASS/FAIL}   {interaction tested}   │
│  CLS     {n}     {PASS/FAIL}   {shift source}         │
│  TTFB    {n}s    {PASS/FAIL}                           │
│  FCP     {n}s    {PASS/FAIL}                           │
│                                                        │
└────────────────────────────────────────────────────────┘
```

6. Provide prioritized fix recommendations:
   - Quick wins (image optimization, lazy loading, font-display)
   - Medium effort (critical CSS, code splitting, CDN)
   - Structural (server upgrade, architecture changes)
7. Save findings to `reports/vitals-{date}.md`
8. Update PERFORMANCE.md with latest CWV scores
</process>

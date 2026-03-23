---
name: web:convert
description: CRO analysis — landing page optimization, A/B test design
argument-hint: "<workspace-name> [--url <page-url>] [--test]"
---
<objective>
Analyze a page for conversion optimization opportunities. Design A/B tests. Review conversion funnel.

Workspace and target: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/channel-specs.md
@./.claude/webos/references/BENCHMARKS.md
@./.claude/webos/references/content-frameworks.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // CONVERT >>`
2. Load workspace: PERFORMANCE.md, AUDIENCE.md, BRAND.md, LEARNINGS.md
3. Determine mode:

   **Page audit mode** (default):
   - Analyze the target page against landing page best practices
   - Check: headline clarity, CTA visibility, social proof placement, form friction, page speed
   - Score each element and provide specific improvements

   **A/B test design mode** (--test):
   - Review current page performance data
   - Identify highest-impact test hypothesis
   - Design variant with specific changes
   - Calculate minimum sample size for statistical significance
   - Define success metric and test duration

   **Funnel analysis mode** (--funnel):
   - Map the conversion path (blog → CTA → landing → form → thank you)
   - Identify biggest drop-off points
   - Suggest fixes for each drop-off

4. For page audit, present findings:

```
┌─ CRO AUDIT ────────────────────────────────────────────┐
│                                                         │
│  Page: {url}                                            │
│  Current conversion rate: {n}%                          │
│  Benchmark: {n}% ({page type})                          │
│                                                         │
│  Element          Score    Issue                        │
│  ───────────────────────────────────────────            │
│  Headline         {/10}   {issue or "OK"}               │
│  CTA              {/10}   {issue or "OK"}               │
│  Social proof     {/10}   {issue or "OK"}               │
│  Form friction    {/10}   {issue or "OK"}               │
│  Page speed       {/10}   {issue or "OK"}               │
│  Mobile UX        {/10}   {issue or "OK"}               │
│  Above the fold   {/10}   {issue or "OK"}               │
│                                                         │
│  Overall: {score}/70                                    │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

5. Provide prioritized recommendations:
   - Quick wins (copy changes, CTA color/text, social proof repositioning)
   - Medium effort (page layout changes, form simplification)
   - A/B test candidates (hypotheses with expected impact)

6. For A/B test design:

```
┌─ A/B TEST DESIGN ──────────────────────────────────────┐
│                                                         │
│  Hypothesis: {changing X will improve Y because Z}      │
│                                                         │
│  Control:  {current state}                              │
│  Variant:  {specific change}                            │
│                                                         │
│  Metric:   {primary metric}                             │
│  Sample:   {n} visitors per variant (95% confidence)    │
│  Duration: {n} weeks at current traffic                 │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

7. Save analysis to `reports/cro-{date}.md`
8. Update LEARNINGS.md with any conversion insights

>> Approve recommendations / Design A/B test / Edit
</process>

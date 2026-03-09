---
name: content:optimize
description: Optimize existing content for better performance
argument-hint: "<workspace-name> <url-or-content-file>"
---
<objective>
Optimize existing content for SEO, readability, or engagement. Make what you have work harder.

Workspace and target: $ARGUMENTS
</objective>

<execution_context>
@./.claude/contentos/references/seo-playbook.md
@./.claude/contentos/references/writing-skill.md
</execution_context>

<process>
1. Display mode header: `<< CONTENT:OS // OPTIMIZE >>`
2. Load workspace: SEO-STRATEGY.md, BRAND.md, TOV.md, LEARNINGS.md, PERFORMANCE.md
3. Fetch/load the content
4. Analyze current performance (if metrics available)
5. Identify optimization opportunities:

   **SEO optimizations:**
   - Better meta title/description
   - Improved heading structure
   - Additional keyword coverage
   - Internal linking opportunities
   - Schema markup additions
   - Content freshness updates

   **Readability optimizations:**
   - Simplify complex sentences
   - Break up long paragraphs
   - Add subheadings for scannability
   - Improve intro hook
   - Strengthen CTA

   **Engagement optimizations:**
   - Better opening hook
   - Add data/statistics
   - Include examples/case studies
   - Add visuals/media suggestions
   - Improve shareability

6. Present optimized version with tracked changes
7. Check execution mode from workspace.config.md:
   - **Interactive:** Ask for approval: `>> Approve optimizations? (approve / edit / reject)`
   - **Auto:** Auto-approve, save optimized version, show `⚡ Auto-approved: optimizations applied`, log in logs/decisions.md
8. Save optimized version
9. Update LEARNINGS.md with what was changed and why
</process>

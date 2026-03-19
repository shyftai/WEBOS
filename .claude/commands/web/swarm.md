---
name: web:swarm
description: Run content operations with parallel agents
argument-hint: "<operation> [workspace-name]"
---
<objective>
Execute content operations in parallel using multiple agents. Dramatically speeds up batch work.

Operation and workspace: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/swarm.md
</execution_context>

<process>
1. Display: `<< WEB:OS // SWARM >>`
2. Parse operation from $ARGUMENTS
3. Load workspace context

## Available operations

### /web:swarm write
- Parallel draft writing — multiple pieces from different briefs simultaneously
- Each agent gets: BRAND.md, TOV.md, one brief, relevant pillar from CONTENT-PILLARS.md
- Collect all drafts, present for batch review

### /web:swarm repurpose
- Take one piece of content, repurpose for all platforms in parallel
- Each agent handles one platform (blog → LinkedIn, Twitter, newsletter, etc.)
- Collect all versions, present together

### /web:swarm seo-audit
- Audit multiple pages/posts in parallel
- Each agent audits one URL against SEO checklist
- Compile results into single report

### /web:swarm review
- Batch content review — multiple drafts reviewed simultaneously
- Each agent reviews one piece against quality gates
- Compile pass/fail results

### /web:swarm research
- Research multiple topics in parallel
- Each agent researches one content topic/keyword
- Compile into content brief inputs

4. For each operation:
   a. Split work into agent-sized chunks
   b. Launch parallel agents (max from defaults.md, typically 5)
   c. Each agent works independently with full context
   d. Collect results
   e. Present unified output
5. Log costs in COSTS.md
6. Suggest next action
</process>

---
name: web:cluster
description: Manage topic clusters and internal linking
argument-hint: "<workspace-name> [--cluster topic-name]"
---
<objective>
Build and manage topic clusters. Map pillar pages to cluster content. Optimize internal linking.

Workspace: $ARGUMENTS
</objective>

<execution_context>
@./.claude/webos/references/seo-playbook.md
</execution_context>

<process>
1. Display mode header: `<< WEB:OS // TOPIC CLUSTERS >>`
2. Load workspace: SEO-STRATEGY.md, PILLARS.md, content inventory
3. Modes:
   - **Map:** visualize existing topic clusters
   - **Build:** create a new topic cluster strategy
   - **Audit:** check internal linking health

4. For mapping/building:
   - Identify pillar page (main topic page)
   - Map cluster pages (supporting content)
   - Define internal linking structure
   - Identify gaps in the cluster

5. Display cluster map:
```
                    [PILLAR PAGE]
                    "{main topic}"
                         │
         ┌───────────────┼───────────────┐
         │               │               │
    [Cluster 1]     [Cluster 2]     [Cluster 3]
    "{subtopic}"    "{subtopic}"    "{subtopic}"
         │               │               │
    ┌────┴────┐     ┌────┴────┐     ┌────┴────┐
    │    │    │     │    │    │     │    │    │
   [S1] [S2] [S3] [S4] [S5] [S6] [S7] [S8] [S9]

  Legend: [✓] exists  [~] needs update  [ ] gap
```

6. List internal linking opportunities
7. Add gaps to ROADMAP.md
8. Update SEO-STRATEGY.md
</process>

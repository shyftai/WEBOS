---
name: web:research
description: Deep research on audience, competitors, or topic
argument-hint: "<workspace-name> <topic-or-question>"
---
<objective>
Research a topic in depth before creating content. Gather sources, data, and insights.

Workspace and topic: $ARGUMENTS
</objective>

<process>
1. Display mode header: `<< WEB:OS // RESEARCH >>`
2. Load workspace: AUDIENCE.md, PILLARS.md, COMPETITORS.md, LEARNINGS.md
3. Research using available tools:
   - Exa for authoritative sources and recent content
   - Firecrawl for scraping specific pages
   - Search Console for existing search data
   - Ahrefs/SEMrush for keyword and competitor data

4. Compile:
   - Key findings and statistics (with sources)
   - Expert opinions and quotes (with attribution)
   - Data points and trends
   - Competitor coverage of this topic
   - Content angle recommendations
   - Potential sources to cite

5. Save research to assets/research/
6. Offer: "Create a brief from this research? /web:brief"
</process>

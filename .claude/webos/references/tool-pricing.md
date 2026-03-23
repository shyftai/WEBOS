# Tool Pricing — Per-unit costs

Track these in COSTS.md for every workspace.

## SEO tools

| Tool | Action | Cost per unit | Notes |
|------|--------|--------------|-------|
| Ahrefs | Keyword lookup | Credit-based | 1 credit per row returned. Overview: 2 credits fixed. Check plan for monthly allocation. |
| Ahrefs | Backlink query | Credit-based | 1 credit per row — use limits to avoid burn. Always call overview first. |
| SEMrush | Keyword lookup | Unit-based | 10 units per row. Use `display_limit` to cap. |
| SEMrush | Domain analysis | Unit-based | 10 units per row. Start with limit=10 for exploration. |
| Moz | Domain analysis | Included in plan | |
| DataforSEO | SERP data | ~$0.002-0.01 | Per query, varies by endpoint |

## Research tools

| Tool | Action | Cost per unit | Notes |
|------|--------|--------------|-------|
| Exa | Search query | ~$0.007 | Per search (1-10 results). Free tier: 1,000/month. |
| Exa | Deep research | $5/agent search | Plus $5/page read. Use sparingly. |
| Firecrawl | Page scrape | ~$0.005 | Per page. 1 credit per page/crawl/map. |
| Firecrawl | Data extraction | Token-based | 15 tokens per credit. FIRE-1 always billed. |

## CMS / Publishing tools

| Tool | Action | Cost per unit | Notes |
|------|--------|--------------|-------|
| Webflow | CMS operations | Included in plan | API: 60 req/min. No per-item charge. |
| Webflow | Site publish | Included in plan | HARD GATE — confirm before every publish. |
| WordPress | API operations | Free (self-hosted) | REST API available on all installs. |
| Contentful | CMS operations | Included in plan | API rate limits vary by plan. |

## Analytics tools

| Tool | Action | Cost per unit | Notes |
|------|--------|--------------|-------|
| Google Analytics 4 | Data query | Free | API quota: 10,000 requests/day per project. |
| Google Search Console | Search data | Free | 1,200 queries/min. URL inspection: 600/day. |
| Google Search Console | URL removal | Free (dangerous) | HARD GATE — 6 month removal. See api-reference.md. |

## Monitoring tools

| Tool | Action | Cost per unit | Notes |
|------|--------|--------------|-------|
| Sentry | Error tracking | Included in plan | Free tier: 5,000 events/month. |
| Pingdom | Uptime monitoring | Included in plan | |
| Hotjar | Heatmap/recording | Included in plan | Free tier: 35 daily sessions. |

## AI processing

| Tool | Action | Cost per unit | Notes |
|------|--------|--------------|-------|
| Claude API | Content generation | ~$0.015/1K tokens | Output tokens. For batch/swarm mode. |
| Claude API | Research/analysis | ~$0.003/1K tokens | Input tokens. |

## Image optimization

| Tool | Action | Cost per unit | Notes |
|------|--------|--------------|-------|
| Cloudinary | Image transform | Included in plan | Free tier: 25,000 transformations/month. |
| TinyPNG | Image compression | Free (limited) | 500 free compressions/month via API. |

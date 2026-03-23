# WEB:OS — The Web Content Operating System

Turn Claude Code into a full web content operation. Write it. Publish it. Rank it. Convert it.

## Install

```bash
git clone https://github.com/shyftai/WEBOS.git
cd WEBOS
claude
```

That's it. WEB:OS boots automatically when Claude Code opens the repo.

### Connect your tools (recommended)

WEB:OS works best with MCP servers connected in Claude Code:

| MCP Server | What it unlocks |
|-----------|----------------|
| **Exa** | Content research, trending topics, competitor scanning |
| **Firecrawl** | Website scraping, SEO audits, competitor analysis |
| **Slack** | Team notifications and alerts |
| **Search Console** | Organic search data, keyword performance |

Add them in Claude Code → Settings → MCP Servers.

### API keys (optional)

Copy `.env.example` to `.env` and add keys for deeper integrations:

- **SEO:** Ahrefs, SEMrush, DataforSEO, Moz
- **CMS:** Webflow, WordPress, Contentful
- **Analytics:** GA4, Google Search Console
- **Research:** Exa, Firecrawl
- **Scale:** Anthropic API (for batch content generation)

## What it does

### Sources of truth
Every workspace has living documents that WEB:OS reads before every action:

| File | Purpose |
|------|---------|
| `BRAND.md` | Brand voice, identity, guidelines |
| `AUDIENCE.md` | Target audiences and segments |
| `PILLARS.md` | Content pillars and themes |
| `TOV.md` | Tone of voice rules |
| `SEO-STRATEGY.md` | Keyword clusters, targets, technical checklist |
| `SITE-ARCHITECTURE.md` | URL structure, navigation, internal linking map |
| `CALENDAR.md` | Content calendar and schedule |
| `PERFORMANCE.md` | Metrics, KPIs, benchmarks |
| `LEARNINGS.md` | Persistent intelligence — what works, what doesn't |
| `ROADMAP.md` | Content pipeline and auto-generated to-dos |
| `COMPETITORS.md` | Competitor content analysis |

### Quality gates
Every piece of content passes 8 checks before approval:

1. **Brief check** — matches the original brief
2. **Brand check** — matches brand voice and guidelines
3. **Audience check** — written for the right segment
4. **SEO check** — keyword, meta, headings, internal links
5. **Readability check** — grade level, sentence length, jargon
6. **Source check** — claims cited, nothing fabricated
7. **Page type check** — formatted correctly for page type
8. **Internal link check** — 3-5 links, no orphan pages

### Learnings system
WEB:OS learns from every piece of content:

- What topics drive organic traffic
- Which page types convert best
- What writing patterns rank
- Which SEO strategies work
- What CRO changes improve conversion
- What definitely doesn't work (anti-learnings)

Updated after every debrief. Loaded before every writing session.

### Role-based experience

| Role | Focus |
|------|-------|
| **Content Creator** | Writing, briefs, tone of voice |
| **Content Strategist** | Pillars, calendar, measurement |
| **SEO Specialist** | Keywords, audits, technical SEO, clusters |
| **CRO Specialist** | Conversion optimization, A/B testing |
| **Head of Content** | Everything — team, reporting, pipeline |
| **Agency** | Multi-brand, portfolio, templates |

## Commands

### Setup
| Command | What it does |
|---------|-------------|
| `/web:onboard` | Create a new workspace — guided setup |
| `/web:research` | Deep-dive into audience, competitors, or topic |

### Daily
| Command | What it does |
|---------|-------------|
| `/web:today` | Daily content briefing — what needs attention |
| `/web:dashboard` | Full workspace performance overview |

### Create
| Command | What it does |
|---------|-------------|
| `/web:brief` | Create a content brief for any web page |
| `/web:write` | Write content from a brief |
| `/web:batch` | Batch content creation at scale |

### SEO
| Command | What it does |
|---------|-------------|
| `/web:seo-audit` | Audit a page or site for SEO |
| `/web:keywords` | Keyword research and clustering |
| `/web:optimize` | Optimize existing content |
| `/web:cluster` | Topic cluster management |

### Technical
| Command | What it does |
|---------|-------------|
| `/web:vitals` | Core Web Vitals audit and recommendations |
| `/web:crawl` | Crawl health, sitemap, index coverage |
| `/web:links` | Internal link graph analysis |

### Publish
| Command | What it does |
|---------|-------------|
| `/web:publish` | Publish or schedule content to CMS |
| `/web:calendar` | View and manage content calendar |

### Conversion
| Command | What it does |
|---------|-------------|
| `/web:convert` | CRO analysis, landing page optimization, A/B tests |

### Intel
| Command | What it does |
|---------|-------------|
| `/web:trends` | Discover trending topics |
| `/web:competitor` | Monitor competitor content |

### Measure
| Command | What it does |
|---------|-------------|
| `/web:analytics` | Pull and analyze web metrics |
| `/web:report` | Generate performance reports |

### Review
| Command | What it does |
|---------|-------------|
| `/web:review` | Quality check before publishing |
| `/web:debrief` | Performance retrospective |
| `/web:compliance` | Compliance and brand safety check |

### Scale
| Command | What it does |
|---------|-------------|
| `/web:swarm` | Parallel agent operations for batch content |

### Other
| Command | What it does |
|---------|-------------|
| `/web:portfolio` | Multi-brand dashboard (agency) |
| `/web:feedback` | Submit feedback, report a bug, or request a feature |
| `/web:status` | Show all commands and system status |

## System status on boot

```
  ┌─ SYSTEM ──────────────────────────────────────────┐
  │                                                    │
  │  Workspaces:  acme-corp, startup-xyz               │
  │  Mode:        solo                                 │
  │                                                    │
  │  MCP servers:                                      │
  │  [x] Exa (research)      [x] Firecrawl (scraping)  │
  │  [ ] Slack (alerts)       [ ] Search Console        │
  │                                                    │
  │  API keys:                                         │
  │  [x] Ahrefs          [ ] SEMrush                   │
  │  [x] Webflow         [ ] GA4                       │
  │                                                    │
  │  2 MCP servers · 2 API keys · 6 missing            │
  │                                                    │
  └────────────────────────────────────────────────────┘
```

## The workflow

```
  BRAND ─── AUDIENCE ─── PILLARS ─── TOV
                  │
              STRATEGY
                  │
     ┌────────────┼────────────┐
     ▼            ▼            ▼
   RESEARCH    KEYWORDS     CLUSTERS
     │            │            │
     ▼            ▼            ▼
  BRIEF ───── WRITE ───── OPTIMIZE
                  │            │
               REVIEW     INTERNAL LINKS
                  │            │
              PUBLISH     ◈ SWARM
                  │       (optional)
           PERFORMANCE
                  │
      ANALYTICS + VITALS + CONVERT
                  │
           OPTIMIZE + LEARN
```

## Collaboration

- **Solo mode** — files stay local, single operator
- **Team mode** — shared state via Supabase, multi-writer coordination

Set during onboarding. Solo is the default.

## Scale mode

For batch operations (25+ pieces), choose:

- **Claude Code** — interactive, real-time review
- **API mode** — runs via Anthropic API, faster at scale (50-500+ pieces)

---

v1.2.0

MIT — Built by [Shyft AI](https://shyft.ai)

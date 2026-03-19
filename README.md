# WEB:OS — The Web Content Operating System

Turn Claude Code into a full content operation. Create it. Publish it. Measure it. Optimize it.

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

- **SEO:** Ahrefs, SEMrush, Moz
- **CMS:** WordPress, Webflow, Ghost
- **Social:** LinkedIn, Twitter/X, Instagram, TikTok
- **Scheduling:** Buffer, Hootsuite
- **Newsletter:** Beehiiv, ConvertKit, Substack
- **Research:** Exa, Firecrawl
- **Monitoring:** Mention, Brand24
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
| `CHANNELS.md` | Active channels, specs, frequency |
| `SEO-STRATEGY.md` | Keyword clusters, targets, technical checklist |
| `CALENDAR.md` | Content calendar and schedule |
| `PERFORMANCE.md` | Metrics, KPIs, benchmarks |
| `LEARNINGS.md` | Persistent intelligence — what works, what doesn't |
| `ROADMAP.md` | Content pipeline and auto-generated to-dos |
| `COMPETITORS.md` | Competitor content analysis |

### Quality gates
Every piece of content passes 7 checks before approval:

1. **Brief check** — matches the original brief
2. **Brand check** — matches brand voice and guidelines
3. **Audience check** — written for the right segment
4. **SEO check** — keyword, meta, headings, links
5. **Readability check** — grade level, sentence length, jargon
6. **Source check** — claims cited, nothing fabricated
7. **Channel check** — formatted for target platform

### Learnings system
WEB:OS learns from every piece of web:

- What topics drive engagement
- Which channels perform best
- What writing patterns convert
- Which SEO strategies work
- What definitely doesn't work (anti-learnings)

Updated after every debrief. Loaded before every writing session.

### Role-based experience

| Role | Focus |
|------|-------|
| **Content Creator** | Writing, briefs, tone of voice |
| **Content Strategist** | Pillars, calendar, measurement |
| **Social Media Manager** | Channels, scheduling, community |
| **SEO Specialist** | Keywords, audits, technical SEO |
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
| `/web:brief` | Create a content brief for any piece |
| `/web:write` | Write content from a brief |
| `/web:repurpose` | Transform content across channels |
| `/web:batch` | Batch content creation at scale |

### SEO
| Command | What it does |
|---------|-------------|
| `/web:seo-audit` | Audit a page or site for SEO |
| `/web:keywords` | Keyword research and clustering |
| `/web:optimize` | Optimize existing content |
| `/web:cluster` | Topic cluster management |

### Publish
| Command | What it does |
|---------|-------------|
| `/web:publish` | Publish or schedule content |
| `/web:calendar` | View and manage content calendar |

### Social
| Command | What it does |
|---------|-------------|
| `/web:social` | Create social media content |
| `/web:community` | Community engagement content |

### Intel
| Command | What it does |
|---------|-------------|
| `/web:trends` | Discover trending topics |
| `/web:competitor` | Monitor competitor content |

### Measure
| Command | What it does |
|---------|-------------|
| `/web:analytics` | Pull and analyze metrics |
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
| `/web:newsletter` | Create email newsletter content |
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
  │  [x] Buffer          [x] Beehiiv                   │
  │                                                    │
  │  2 MCP servers · 3 API keys · 8 missing            │
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
   RESEARCH     WRITE       METRICS
     │            │            │
     ▼            ▼            ▼
  IDEATE ──── CREATE ──── PUBLISH
                  │            │
             REPURPOSE    ◈ SWARM
                  │       (optional)
           PERFORMANCE
                  │
           OPTIMIZE + LEARN
                  │
             CALENDAR ──── CHANNELS
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

v1.0.0

MIT — Built by [Shyft AI](https://shyft.ai)

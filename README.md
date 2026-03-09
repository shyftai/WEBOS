# CONTENT:OS

A living content operating system that runs inside Claude Code. Research, write, publish, measure — all from the terminal.

Not a template. Not a tool. An operating system for content teams.

## Install

```bash
git clone https://github.com/shyftai/CONTENTOS.git
cd CONTENTOS
claude
```

That's it. CONTENT:OS boots automatically when Claude Code opens the repo.

### Connect your tools (recommended)

CONTENT:OS works best with MCP servers connected in Claude Code:

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
Every workspace has living documents that CONTENT:OS reads before every action:

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
CONTENT:OS learns from every piece of content:

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
| `/content:onboard` | Create a new workspace — guided setup |
| `/content:research` | Deep-dive into audience, competitors, or topic |

### Daily
| Command | What it does |
|---------|-------------|
| `/content:today` | Daily content briefing — what needs attention |
| `/content:dashboard` | Full workspace performance overview |

### Create
| Command | What it does |
|---------|-------------|
| `/content:brief` | Create a content brief for any piece |
| `/content:write` | Write content from a brief |
| `/content:repurpose` | Transform content across channels |
| `/content:batch` | Batch content creation at scale |

### SEO
| Command | What it does |
|---------|-------------|
| `/content:seo-audit` | Audit a page or site for SEO |
| `/content:keywords` | Keyword research and clustering |
| `/content:optimize` | Optimize existing content |
| `/content:cluster` | Topic cluster management |

### Publish
| Command | What it does |
|---------|-------------|
| `/content:publish` | Publish or schedule content |
| `/content:calendar` | View and manage content calendar |

### Social
| Command | What it does |
|---------|-------------|
| `/content:social` | Create social media content |
| `/content:community` | Community engagement content |

### Intel
| Command | What it does |
|---------|-------------|
| `/content:trends` | Discover trending topics |
| `/content:competitor` | Monitor competitor content |

### Measure
| Command | What it does |
|---------|-------------|
| `/content:analytics` | Pull and analyze metrics |
| `/content:report` | Generate performance reports |

### Review
| Command | What it does |
|---------|-------------|
| `/content:review` | Quality check before publishing |
| `/content:debrief` | Performance retrospective |
| `/content:compliance` | Compliance and brand safety check |

### Scale
| Command | What it does |
|---------|-------------|
| `/content:swarm` | Parallel agent operations for batch content |

### Other
| Command | What it does |
|---------|-------------|
| `/content:newsletter` | Create email newsletter content |
| `/content:portfolio` | Multi-brand dashboard (agency) |
| `/content:feedback` | Submit feedback, report a bug, or request a feature |
| `/content:status` | Show all commands and system status |

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

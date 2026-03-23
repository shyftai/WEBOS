# Changelog

## v1.2.0 — 2026-03-23

### Focus shift: Web-first
WEB:OS is now focused exclusively on website content — blogs, landing pages, product pages, docs, case studies, comparisons, and SEO. Social media, newsletters, and community content are moving to SOCIAL:OS and MARKETING:OS respectively.

### Added
- `/web:vitals` — Core Web Vitals audit and recommendations
- `/web:crawl` — Crawl health, sitemap status, index coverage
- `/web:links` — Internal link graph analysis (orphans, depth, coverage)
- `/web:convert` — CRO analysis, landing page optimization, A/B test design
- `seo-fundamentals.md` — deep SEO reference (E-E-A-T, technical SEO, schema, ranking factors)
- `geo-fundamentals.md` — GEO reference (AI search optimization, RAG retrieval, entity building)
- `SITE-ARCHITECTURE.md` template — URL structure, navigation, internal linking map
- Web page type specs: pillar, landing, product, comparison, case study, docs, FAQ, glossary, resource

### Changed
- `channel-specs.md` → now covers web page types only (was social platform specs)
- `defaults.md` → added CMS, Core Web Vitals, site architecture, and conversion defaults
- `BENCHMARKS.md` → added CWV, internal linking, conversion, site health benchmarks
- `writing-skill.md` → added landing page, product page, UX microcopy, documentation writing
- `content-frameworks.md` → added landing page, comparison, feature, FAQ, resource hub frameworks
- `distribution-playbook.md` → now covers internal linking, content hubs, site architecture, refresh strategy
- `notifications.md` → web-specific alerts (CWV, ranking drops, broken links, crawl issues)
- `report-template.md` → web performance reports (organic traffic, SEO, CWV, conversion)
- `tool-pricing.md` → added CMS, analytics, image optimization tools
- `api-reference.md` → removed Buffer, kept Webflow + SEO tools
- All templates updated: CHANNELS → web properties, CALENDAR, PERFORMANCE, TOV, LEARNINGS, ROADMAP
- README updated to reflect web-first focus
- Boot banner updated: "Write it. Publish it. Rank it. Convert it."
- Flow diagram updated: RESEARCH → KEYWORDS → CLUSTERS → WRITE → OPTIMIZE → PUBLISH

### Removed
- `/web:social` → moving to SOCIAL:OS
- `/web:community` → moving to SOCIAL:OS
- `/web:newsletter` → moving to MARKETING:OS
- `/web:repurpose` → moving to SOCIAL:OS
- Buffer API reference and integration
- Social platform specs (LinkedIn, Twitter, Instagram, YouTube, Reddit)
- Newsletter specs and tools (Beehiiv, ConvertKit, Substack)
- Social scheduling tools (Buffer, Hootsuite)
- Community tools (Reddit, Discord)
- Social/newsletter benchmarks and metrics

## v1.1.0 — 2026-03-09
- Add /web:today daily briefing command
- Add auto execution mode (interactive/auto with hard gates)
- Add ui-brand.md visual consistency standard
- Add /web:feedback command
- Add /web:debrief command
- Add /web:compliance command
- Add /web:portfolio agency command
- Add swarm reference for parallel content operations

## v1.0.0 — Launch

### Core system
- Boot sequence with ASCII banner and system status
- Workspace architecture with sources of truth
- Role-based onboarding
- MCP server and API key detection
- Solo/team collaboration mode
- Quality gates
- Learnings system (persistent intelligence)
- Content roadmap with auto-generated to-dos

### Integrations
- SEO: Ahrefs, SEMrush, DataforSEO, Moz, Search Console, Google Analytics
- CMS: WordPress, Webflow, Ghost, Contentful
- Research: Exa, Firecrawl
- Scale: Claude API for batch generation
- Collaboration: Supabase for team mode

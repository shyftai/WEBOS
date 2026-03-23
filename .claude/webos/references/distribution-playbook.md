# Web Distribution Playbook

## Core principle

For WEB:OS, distribution means making content **discoverable, navigable, and connected** within your own web properties. Social distribution, newsletters, and paid amplification belong to SOCIAL:OS and MARKETING:OS.

## Internal linking strategy

### Why internal links matter
- Pass authority (PageRank) from strong pages to weaker ones
- Help search engines understand site structure and topic relationships
- Keep users on-site longer (pages per session, time on site)
- Surface relevant content at the right moment in the reader's journey

### Internal linking rules

1. **Every page must have ≥3 internal links** — no orphan pages
2. **Link contextually** — anchor text should describe the destination, not "click here"
3. **Link from strong to weak** — high-authority pages should link to pages that need a boost
4. **Cluster pages link to pillar** — every cluster page links back to its pillar
5. **Pillar links to all clusters** — the pillar page is the hub
6. **New content links to existing** — every new page adds 3-5 links to relevant existing pages
7. **Existing content links to new** — after publishing, update 3-5 existing pages to link to the new one
8. **Don't over-link** — 3-5 internal links per 1,000 words is the sweet spot
9. **Audit monthly** — find and fix orphan pages, broken internal links, thin link profiles

### Link placement hierarchy

| Position | Impact | Use for |
|----------|--------|---------|
| First paragraph | Highest | Most important related page |
| Within body sections | High | Contextually relevant content |
| "Related reading" box | Medium | Topic-adjacent content |
| Sidebar / footer | Low | Navigation, not SEO value |

## Content hub architecture

### Hub-and-spoke model

```
              [HUB PAGE]
         (topic overview, high DA)
                  │
    ┌─────────────┼─────────────┐
    │             │             │
[SPOKE 1]    [SPOKE 2]    [SPOKE 3]
(subtopic)   (subtopic)   (subtopic)
    │             │             │
    └─────────────┼─────────────┘
          (cross-links between spokes)
```

- **Hub page:** Comprehensive overview, links to all spokes, targets head keyword
- **Spoke pages:** Deep dives on subtopics, link to hub and adjacent spokes
- **Cross-links:** Related spokes link to each other for discoverability
- **Update cycle:** Hub quarterly, spokes as data changes

### Building a content hub

1. **Identify the core topic** — Map to a high-volume keyword cluster
2. **Create the hub page first** — Comprehensive overview (2,000-4,000 words)
3. **Plan spokes around subtopics** — Each targets a cluster keyword
4. **Build spokes systematically** — 1-2 per week, interlink as you go
5. **Update the hub page** — Add links to new spokes as they publish
6. **Audit the hub monthly** — Check for gaps, update data, fix broken links

## Site architecture for SEO

### URL structure

```
domain.com/
├── /blog/                    ← Blog index
│   ├── /blog/{topic}/        ← Topic cluster index
│   └── /blog/{topic}/{slug}  ← Individual posts
├── /product/                 ← Product pages
│   ├── /product/{feature}    ← Feature pages
│   └── /product/pricing      ← Pricing
├── /resources/               ← Resource hub
│   ├── /resources/guides/    ← Guides
│   ├── /resources/templates/ ← Templates
│   └── /resources/tools/     ← Tools
├── /customers/               ← Case studies
│   └── /customers/{slug}     ← Individual case study
├── /docs/                    ← Documentation
│   └── /docs/{section}/{page}← Doc pages
├── /compare/                 ← Comparison pages
│   └── /compare/{x}-vs-{y}  ← Individual comparisons
└── /glossary/                ← Glossary
    └── /glossary/{term}      ← Individual terms
```

### Navigation principles

- **Main nav:** ≤7 items, most important pages only
- **Mega menu:** For complex sites, group by topic/category
- **Breadcrumbs:** On every page, with Breadcrumb schema
- **Footer:** All key pages + legal. Not a sitemap dump.
- **Sidebar (docs):** Full doc tree with current page highlighted
- **"Related" sections:** At bottom of every content page

## Content refresh strategy

### When to refresh

| Signal | Action |
|--------|--------|
| Ranking position 5-20 and dropping | Priority refresh — update content, add sections |
| Ranking #1-3 and stable | Don't touch — monitor only |
| Content >6 months old, not ranking | Evaluate: refresh or consolidate with another page |
| Competitor published better version | Skyscraper update — add what they have, plus more |
| Data/stats are outdated | Update numbers, re-publish with current date |
| New internal pages to link to | Add internal links, update related content sections |

### Refresh checklist

- [ ] Update all statistics and data points
- [ ] Add new sections for recently searched subtopics
- [ ] Refresh screenshots and visuals
- [ ] Add internal links to content published since original
- [ ] Update meta title and description if needed
- [ ] Check all external links still work
- [ ] Update publish date
- [ ] Resubmit URL to Google for re-crawling

## Canonical and redirect management

### Canonical tags
- Every page must have a self-referencing canonical
- Syndicated content canonicals point to the original
- Parameter URLs canonical to the clean version
- WWW vs non-WWW: pick one, canonical the other

### Redirects
- **301** for permanent URL changes (passes ~90% link equity)
- **302** for temporary changes only (does NOT pass equity)
- **Never chain redirects** — A→B→C should become A→C
- **Audit redirect chains quarterly**
- **Set up redirects BEFORE removing/moving content**

## Sitemap management

- XML sitemap submitted to Google Search Console
- Include only indexable, canonical pages
- Exclude noindex pages, redirects, and error pages
- Update automatically when content is published/unpublished
- Split sitemaps by content type for large sites (blog-sitemap.xml, pages-sitemap.xml)
- Monitor sitemap coverage in GSC weekly

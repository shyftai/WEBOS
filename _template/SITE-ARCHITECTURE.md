# Site Architecture — {brand-name}

## URL structure

```
{domain.com}/
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

## Topic clusters

| Pillar | Pillar page URL | Cluster pages | Coverage |
|--------|----------------|--------------|----------|
| | | | |

## Internal linking map

| Page | Links to | Links from | Click depth |
|------|---------|-----------|-------------|
| Homepage | | | 0 |
| | | | |

## Navigation

### Main nav
- {Item 1}
- {Item 2}
- {Item 3}

### Footer
- {Section 1}: {links}
- {Section 2}: {links}

## Technical config

| Setting | Value |
|---------|-------|
| CMS | {Webflow / WordPress / etc.} |
| CDN | |
| SSL | |
| Sitemap URL | |
| Robots.txt | |
| Canonical strategy | Self-referencing on all pages |
| Redirect management | |
| Breadcrumbs | Enabled |

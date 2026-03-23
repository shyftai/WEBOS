# WEB:OS — Defaults

Sensible defaults for everything. All overridable per workspace.

## Workspace defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Execution mode | interactive | workspace.config.md |
| Collaboration mode | solo | workspace.config.md |

## Content defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Blog post word count | 1,500-2,500 words | Brief |
| Pillar page word count | 2,000-4,000 words | Brief |
| Landing page word count | 300-800 words | Brief |
| Case study word count | 800-1,500 words | Brief |
| Documentation page | As long as needed | Brief |
| Meta title length | ≤60 characters | SEO-STRATEGY.md |
| Meta description length | ≤155 characters | SEO-STRATEGY.md |
| Readability target | Grade 8 (Flesch-Kincaid) | TOV.md |
| Avg sentence length | ≤20 words | TOV.md |
| Paragraph length | 2-3 sentences | TOV.md |
| CTA per page | 1 primary | Brief |

## Publishing defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Blog frequency | 2x/week | CALENDAR.md |
| Content review required | Yes | Never override |
| CMS | Webflow | workspace.config.md |
| Staging preview required | Yes before publish | Never override |
| Auto-publish | Never | workspace.config.md |

## SEO defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Min word count for ranking | 1,200 words | SEO-STRATEGY.md |
| Internal links per page | 3-5 | SEO-STRATEGY.md |
| External links per post | 2-3 authoritative | SEO-STRATEGY.md |
| Keyword density | 0.5-1.5% | Natural, never forced |
| Image alt text | Required on all images | Always |
| Schema markup | Article, FAQ, HowTo, Breadcrumb | SEO-STRATEGY.md |
| Canonical tags | Required on all pages | Never override |
| XML sitemap | Auto-generated, submitted to GSC | SEO-STRATEGY.md |
| Robots.txt | Review before publish | SEO-STRATEGY.md |
| Open Graph tags | Required on all pages | SEO-STRATEGY.md |

## Technical web defaults

| Setting | Default | Override in |
|---------|---------|------------|
| LCP (Largest Contentful Paint) | <2.5 seconds | workspace.config.md |
| INP (Interaction to Next Paint) | <200ms | workspace.config.md |
| CLS (Cumulative Layout Shift) | <0.1 | workspace.config.md |
| Image format | WebP with fallback | workspace.config.md |
| Image lazy loading | Enabled (except above-fold) | workspace.config.md |
| HTTPS | Required, no mixed content | Never override |
| Mobile responsive | Required | Never override |
| 404 handling | Custom page + redirect audit | SEO-STRATEGY.md |
| Redirect type | 301 for permanent moves | SEO-STRATEGY.md |
| URL structure | Lowercase, hyphens, no trailing slashes | SEO-STRATEGY.md |

## Site architecture defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Max click depth | 3 clicks from homepage | SEO-STRATEGY.md |
| Orphan page tolerance | 0 — every page must be linked | SEO-STRATEGY.md |
| Topic cluster structure | Pillar → Cluster → Support | SEO-STRATEGY.md |
| Breadcrumbs | Enabled on all pages | workspace.config.md |
| Navigation depth | ≤2 levels in main nav | workspace.config.md |
| Footer links | Key pages + legal | workspace.config.md |
| Internal link audit frequency | Monthly | SEO-STRATEGY.md |

## Conversion defaults

| Setting | Default | Override in |
|---------|---------|------------|
| CTA above fold | Required on landing pages | Brief |
| Form fields | Minimum necessary (name + email baseline) | Brief |
| Social proof near CTA | Required on landing pages | Brief |
| Exit intent popup | Disabled by default | workspace.config.md |
| A/B test minimum sample | 1,000 visitors per variant | workspace.config.md |
| Statistical significance threshold | 95% | workspace.config.md |

## Quality defaults

| Gate | Default | Override in |
|------|---------|------------|
| Brief required | Yes | Never override |
| Brand check | Yes | Never override |
| Source check | Yes | Never override |
| SEO check | Yes for all web content | Never override |
| Readability check | Yes | TOV.md |
| Review before publish | Yes | Never override |
| Staging preview | Yes | Never override |

## Batch defaults

| Setting | Default |
|---------|---------|
| Batch size (Claude Code) | 10 pieces |
| Batch size (API mode) | 50 pieces |
| Max parallel agents | 5 |
| Review mode | Batch of 5, then approve |

---

## How overrides work

1. WEB:OS checks the workspace-level file first (e.g. SEO-STRATEGY.md, TOV.md)
2. If the setting is specified there, use it
3. If not specified, fall back to these defaults
4. Non-overridable settings (marked above) always apply regardless of workspace config
5. Users can add a `## WEB:OS overrides` section to any workspace file to change defaults

# CONTENT:OS — Defaults

Sensible defaults for everything. All overridable per workspace.

## Content defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Blog word count | 1,500-2,500 words | Brief |
| LinkedIn post length | 150-300 words | CHANNELS.md |
| Twitter max length | 280 chars | Platform limit |
| Newsletter length | 500-800 words | CHANNELS.md |
| Meta title length | ≤60 characters | SEO-STRATEGY.md |
| Meta description length | ≤155 characters | SEO-STRATEGY.md |
| Readability target | Grade 8 (Flesch-Kincaid) | TOV.md |
| Avg sentence length | ≤20 words | TOV.md |
| Paragraph length | 2-3 sentences | TOV.md |
| CTA per piece | 1 primary | Brief |

## Publishing defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Blog frequency | 2x/week | CHANNELS.md |
| LinkedIn frequency | 5x/week | CHANNELS.md |
| Twitter frequency | 1-3x/day | CHANNELS.md |
| Newsletter frequency | 1x/week | CHANNELS.md |
| Best time (LinkedIn) | Tue-Thu 8-10am | LEARNINGS.md |
| Best time (Twitter) | Weekdays 12-1pm | LEARNINGS.md |
| Best time (Newsletter) | Tue/Thu 9am | LEARNINGS.md |

## SEO defaults

| Setting | Default | Override in |
|---------|---------|------------|
| Min word count for ranking | 1,200 words | SEO-STRATEGY.md |
| Internal links per post | 3-5 | SEO-STRATEGY.md |
| External links per post | 2-3 | SEO-STRATEGY.md |
| Keyword density | 0.5-1.5% | Natural, never forced |
| Image alt text | Required on all | Always |
| Schema markup | Article, FAQ, HowTo | SEO-STRATEGY.md |

## Quality defaults

| Gate | Default | Override in |
|------|---------|------------|
| Brief required | Yes | Never override |
| Brand check | Yes | Never override |
| Source check | Yes | Never override |
| SEO check | Yes for blog | Channel-specific |
| Readability check | Yes | TOV.md |
| Review before publish | Yes | Never override |

## Batch defaults

| Setting | Default |
|---------|---------|
| Batch size (Claude Code) | 10 pieces |
| Batch size (API mode) | 50 pieces |
| Max parallel agents | 5 |
| Review mode | Batch of 5, then approve |

# SEO Fundamentals — WEB:OS Reference

Deep SEO reference for audits, technical SEO, and content optimization. Load alongside seo-playbook.md for comprehensive SEO work.

---

## 1. E-E-A-T Framework

Google's quality evaluation framework — applies to all web content.

| Principle | Signals | How WEB:OS applies it |
|-----------|---------|----------------------|
| **Experience** | First-hand knowledge, real examples | Case studies with real data, "we tested" language |
| **Expertise** | Credentials, depth of knowledge | Author bios, detailed technical content |
| **Authoritativeness** | Backlinks, mentions, industry recognition | Topic clusters build authority, internal linking reinforces |
| **Trustworthiness** | HTTPS, transparency, accurate info | Source citations, "last updated" dates, clear authorship |

---

## 2. Core Web Vitals

| Metric | Poor | Needs improvement | Good | Target |
|--------|------|-------------------|------|--------|
| **LCP** (Largest Contentful Paint) | >4.0s | 2.5-4.0s | <2.5s | <1.5s |
| **INP** (Interaction to Next Paint) | >500ms | 200-500ms | <200ms | <100ms |
| **CLS** (Cumulative Layout Shift) | >0.25 | 0.1-0.25 | <0.1 | <0.05 |

### Common fixes

| Issue | Fix |
|-------|-----|
| High LCP | Optimize hero image (WebP, lazy load below fold), preload critical resources |
| High INP | Reduce JavaScript, defer non-critical scripts, use web workers |
| High CLS | Set explicit width/height on images, avoid dynamic content injection above fold |

---

## 3. Technical SEO Checklist

### Site structure

| Element | Purpose | Check |
|---------|---------|-------|
| XML sitemap | Help crawlers discover pages | Submitted to GSC, no 404s, no noindex pages included |
| robots.txt | Control crawler access | Not blocking important pages, blocking admin/staging |
| Canonical tags | Prevent duplicate content | Self-referencing on all pages, correct on syndicated |
| HTTPS | Security signal | No mixed content, all resources served over HTTPS |
| Breadcrumbs | Navigation + schema | BreadcrumbList schema on all pages |

### Performance

| Factor | Impact | Target |
|--------|--------|--------|
| Page speed | Core Web Vital, ranking factor | LCP <2.5s |
| Mobile-friendly | Required — mobile-first indexing | Responsive, no horizontal scroll |
| Clean URLs | Crawlability, user trust | Lowercase, hyphens, descriptive, no parameters |
| Redirect chains | Wasted crawl budget, diluted equity | ≤1 hop, no chains |
| 404 handling | User experience, crawl health | Custom 404 page, redirect broken pages |

### Crawl budget optimization

| Action | Impact |
|--------|--------|
| Block low-value pages (admin, tags, archives) | Preserve crawl budget for important content |
| Fix redirect chains | Reduce wasted crawls |
| Remove orphan pages | Crawlers can't find them anyway |
| Keep sitemap clean | Only indexable, canonical pages |
| Internal link from high-authority pages | Guides crawlers to priority content |

---

## 4. On-Page SEO Elements

| Element | Best practice | Notes |
|---------|---------------|-------|
| Title tag | 50-60 chars, primary keyword front-loaded, compelling | Most important on-page signal |
| Meta description | 150-155 chars, includes keyword, has CTA | Doesn't directly rank but affects CTR |
| H1 | One per page, includes primary keyword, matches search intent | Must match what the searcher expects |
| H2-H6 | Logical hierarchy, include secondary keywords naturally | Structure guides both readers and crawlers |
| Alt text | Descriptive of the image content, keyword where natural | Don't stuff — describe what you see |
| URL | Short, descriptive, includes keyword, lowercase with hyphens | Avoid parameters, dates (unless news), and IDs |
| First paragraph | Include primary keyword in first 100 words | Answer the search intent immediately |
| Internal links | 3-5 per page, contextual anchor text | Link to cluster pages and pillar |
| External links | 2-3 authoritative sources per page | Builds trust, signals relevance |

### Content quality signals

| Factor | What Google looks for |
|--------|----------------------|
| Depth | Comprehensive coverage of the topic — not word count for its own sake |
| Freshness | Regular updates, "last updated" dates, current data |
| Uniqueness | Original research, data, or perspective — not rewording competitors |
| Readability | Clear writing, proper structure, scannable formatting |
| User satisfaction | Low pogo-sticking, high time on page, low bounce from SERP |

---

## 5. Schema Markup Reference

| Type | Use for | Priority |
|------|---------|----------|
| Article | Blog posts, guides, news | High — all blog content |
| Organization | Company info on homepage/about | High — one per site |
| Person | Author profiles | High — E-E-A-T signal |
| FAQPage | FAQ sections on any page | High — rich snippet eligibility |
| HowTo | Step-by-step tutorials | Medium — structured data in SERP |
| Product | Product pages, pricing | High for SaaS/ecommerce |
| Review | Customer testimonials | Medium |
| BreadcrumbList | Navigation path | High — all pages |
| SoftwareApplication | SaaS product pages | Medium |
| DefinedTermSet | Glossary pages | Medium |
| ItemList | Resource hubs, listicles | Medium |

### Schema implementation rules
- Use JSON-LD (not microdata or RDFa)
- One primary schema type per page
- Can combine compatible types (Article + FAQPage + BreadcrumbList)
- Validate with Google Rich Results Test before publishing
- Keep schema data consistent with visible page content

---

## 6. AI Content Guidelines

Google's stance: AI content is fine if it's high-quality and helpful.

| Do | Don't |
|----|-------|
| Use AI for drafting, then add human expertise | Publish raw AI output without review |
| Add original insights, data, and experience | Regurgitate what's already ranking |
| Have subject matter experts review | Skip fact-checking AI claims |
| Follow E-E-A-T in all AI-assisted content | Use AI to mass-produce thin pages |
| Disclose AI assistance where appropriate | Try to pass AI content as personal experience |

---

## 7. Ranking Factors (Prioritized)

| Priority | Factor | WEB:OS lever |
|----------|--------|-------------|
| 1 | Quality, relevant content | /web:write with briefs, quality gates |
| 2 | Backlinks from authority sites | Case studies, original research, link-worthy content |
| 3 | Page experience (Core Web Vitals) | /web:vitals audit and fixes |
| 4 | Mobile optimization | Responsive design, mobile-first content |
| 5 | Technical SEO fundamentals | /web:crawl, /web:seo-audit |
| 6 | Internal linking structure | /web:links, /web:cluster |
| 7 | Content freshness | Content refresh strategy in distribution-playbook.md |
| 8 | Schema markup | Applied during /web:publish |

---

## 8. Measurement

| Metric | Tool | Frequency |
|--------|------|-----------|
| Keyword rankings | Google Search Console, Ahrefs | Weekly |
| Organic traffic | GA4 | Weekly |
| Core Web Vitals | PageSpeed Insights, GSC | Monthly |
| Index coverage | Google Search Console | Monthly |
| Backlink profile | Ahrefs, SEMrush | Monthly |
| Crawl errors | Google Search Console | Weekly |
| Conversion rate | GA4 | Weekly |
| Click-through rate | Google Search Console | Weekly |

---

> SEO is a long-term game. Quality content + technical excellence + patience = results.

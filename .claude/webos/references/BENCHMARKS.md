# Web Performance Benchmarks

## Organic traffic

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Organic traffic growth (MoM) | <2% | 2-5% | 5-10% | >10% |
| Organic traffic share (of total) | <30% | 30-50% | 50-70% | >70% |
| Non-branded organic share | <20% | 20-40% | 40-60% | >60% |
| Organic conversion rate | <0.5% | 0.5-1% | 1-3% | >3% |

## SEO

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Domain authority / DR | <20 | 20-40 | 40-60 | >60 |
| Keywords in top 10 | <50 | 50-200 | 200-1,000 | >1,000 |
| Organic CTR (avg) | <1% | 1-3% | 3-5% | >5% |
| Page 1 ranking rate | <10% | 10-25% | 25-50% | >50% |
| Crawl coverage (indexed/submitted) | <70% | 70-85% | 85-95% | >95% |
| Index bloat (indexed/intended) | >150% | 120-150% | 100-120% | ~100% |

## Core Web Vitals

| Metric | Poor | Needs improvement | Good | Target |
|--------|------|-------------------|------|--------|
| LCP (Largest Contentful Paint) | >4.0s | 2.5-4.0s | <2.5s | <1.5s |
| INP (Interaction to Next Paint) | >500ms | 200-500ms | <200ms | <100ms |
| CLS (Cumulative Layout Shift) | >0.25 | 0.1-0.25 | <0.1 | <0.05 |
| TTFB (Time to First Byte) | >1.8s | 0.8-1.8s | <0.8s | <0.4s |
| FCP (First Contentful Paint) | >3.0s | 1.8-3.0s | <1.8s | <1.0s |

## Page engagement

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Avg time on page (blog) | <1 min | 1-2 min | 2-4 min | >4 min |
| Bounce rate (blog) | >70% | 50-70% | 35-50% | <35% |
| Bounce rate (landing page) | >80% | 60-80% | 40-60% | <40% |
| Pages per session | <1.5 | 1.5-2.5 | 2.5-4.0 | >4.0 |
| Scroll depth (avg) | <30% | 30-50% | 50-75% | >75% |
| Return visitor rate | <15% | 15-25% | 25-40% | >40% |

## Conversion (web)

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Blog → lead conversion | <0.5% | 0.5-1% | 1-3% | >3% |
| Landing page conversion | <2% | 2-5% | 5-10% | >10% |
| Pricing page conversion | <1% | 1-3% | 3-7% | >7% |
| CTA click-through rate | <1% | 1-3% | 3-5% | >5% |
| Form completion rate | <20% | 20-40% | 40-60% | >60% |
| Free trial → paid | <2% | 2-5% | 5-15% | >15% |

## Site health

| Metric | Red flag | Healthy |
|--------|----------|---------|
| Broken links (4xx) | >20 | 0 |
| Server errors (5xx) | Any | 0 |
| Redirect chains | >3 hops | ≤1 hop |
| Orphan pages | >5% of pages | 0% |
| Duplicate content pages | >10 | 0 |
| Missing meta descriptions | >10% | 0% |
| Missing alt text | >20% | 0% |
| Mixed content (HTTP on HTTPS) | Any | 0 |
| Pages not in sitemap | >5% | 0% |
| Sitemap → 404 | Any | 0 |

## Internal linking

| Metric | Poor | Average | Good | Excellent |
|--------|------|---------|------|-----------|
| Avg internal links per page | <2 | 2-3 | 3-5 | >5 |
| Orphan pages (no inbound links) | >10% | 5-10% | 1-5% | 0% |
| Max click depth to any page | >5 | 4-5 | 3 | ≤2 |
| Pillar-cluster link coverage | <50% | 50-70% | 70-90% | >90% |

## Content production (web only)

| Metric | Solo | Small team | Content team | Agency |
|--------|------|-----------|-------------|--------|
| Blog posts/month | 4-8 | 8-16 | 16-30 | 20-50+ |
| Landing pages/quarter | 1-2 | 2-5 | 5-10 | 10-20+ |
| Case studies/quarter | 1 | 2-4 | 4-8 | 8+ |
| Content refreshes/month | 2-4 | 4-8 | 8-15 | 15+ |

---

## How to use these benchmarks

1. **Audits** — Compare site metrics against the "Average" column. Flag anything in "Poor".
2. **Debriefs** — Use to contextualize results. A 3% blog conversion rate is "Good", not "low".
3. **Goal setting** — Set targets at "Good" for new sites, "Excellent" for mature sites.
4. **Troubleshooting** — If a metric is "Poor", check the corresponding area:
   - Low organic traffic → keyword targeting, content quality, technical SEO
   - Poor Core Web Vitals → page speed, image optimization, CLS sources
   - Low conversion → CTA placement, page design, offer strength
   - Poor site health → crawl errors, broken links, redirect chains
   - Weak internal linking → orphan pages, click depth, cluster coverage

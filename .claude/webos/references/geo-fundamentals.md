# GEO Fundamentals — WEB:OS Reference

Generative Engine Optimization — how to get cited by AI search engines (ChatGPT, Claude, Perplexity, Gemini). Load this when optimizing content for AI discovery alongside traditional SEO.

---

## 1. What is GEO?

**GEO** = Generative Engine Optimization — optimizing content to be selected and cited by AI-powered search engines.

### SEO vs GEO

| Aspect | SEO | GEO |
|--------|-----|-----|
| Goal | Page 1 ranking | AI citation |
| Platform | Google, Bing | ChatGPT, Claude, Perplexity, Gemini |
| Metrics | Rankings, CTR, traffic | Citation rate, "according to" mentions |
| Focus | Keywords, backlinks | Entities, structured data, citable facts |
| Content style | Keyword-optimized | Clear answers, quotable statements |
| Time horizon | Weeks to months | Emerging — early movers win |

**Key insight:** SEO and GEO are complementary. Content that ranks well in Google is more likely to be in AI training data and retrieval indexes. Do both.

---

## 2. AI Engine Landscape

| Engine | Citation style | Opportunity | Notes |
|--------|----------------|-------------|-------|
| **Perplexity** | Numbered references [1][2] | Highest citation rate | Most transparent about sources |
| **ChatGPT** (with search) | Inline citations, footnotes | Huge user base | Custom GPTs can reference your content |
| **Claude** | Contextual references | Long-form research | Favors comprehensive, well-structured content |
| **Gemini** | Sources section below response | SEO crossover | Pulls from Google index |
| **Copilot** (Bing) | Footnote citations | Enterprise users | Pulls from Bing index |

---

## 3. How AI Retrieval Works (RAG)

When a user asks an AI a question, it uses Retrieval-Augmented Generation:

1. **Query understanding** — AI interprets the question
2. **Retrieval** — searches an index for relevant content
3. **Selection** — picks the best sources based on:

| Factor | Approx. weight | How to optimize |
|--------|----------------|-----------------|
| Semantic relevance | ~40% | Match the topic comprehensively, use natural language |
| Keyword match | ~20% | Include specific terms people search for |
| Authority signals | ~15% | Backlinks, domain authority, brand mentions |
| Freshness | ~10% | Recent publish/update dates, current data |
| Source diversity | ~15% | Be a unique source, not a copy of Wikipedia |

4. **Generation** — AI synthesizes an answer, citing selected sources

---

## 4. Content That Gets Cited

| Element | Why it works | Example |
|---------|--------------|---------|
| **Original statistics** | Unique, citable, can't be found elsewhere | "Our analysis of 10,000 SaaS websites shows..." |
| **Expert quotes** | Authority transfer, human credibility | "According to {Name}, {Title} at {Company}..." |
| **Clear definitions** | Easy for AI to extract and quote | "Content velocity is the rate at which..." |
| **Step-by-step guides** | Structured, actionable, complete | "To set up SSO: 1. Navigate to... 2. Click..." |
| **Comparison tables** | Structured data AI can reference directly | Feature-by-feature product comparisons |
| **FAQ sections** | Direct question → answer pairs | Matches how users query AI engines |
| **Data-backed claims** | Verifiable, trustworthy | "Companies that blog 4x/week get 3.5x more traffic (HubSpot, 2024)" |

### What does NOT get cited
- Vague marketing language ("We're the leading platform...")
- Content without dates or sources
- Thin pages that rewrite other sources
- Gated content (AI can't access it)
- Pages blocked by robots.txt for AI crawlers

---

## 5. GEO Content Checklist

Apply these when writing any web content through WEB:OS. These enhance SEO content, they don't replace it.

### Content elements

- [ ] Question-based titles or H2s (match how people ask AI)
- [ ] Summary / TL;DR near the top (easy extraction point)
- [ ] Original data with cited sources
- [ ] Expert quotes with name, title, and company
- [ ] FAQ section (3-5 question/answer pairs)
- [ ] Clear definitions for key terms
- [ ] "Last updated" timestamp visible on page
- [ ] Author bio with credentials and expertise signals
- [ ] Comparison tables for commercial content
- [ ] Specific numbers over vague claims

### Technical elements

- [ ] Article schema with `datePublished` and `dateModified`
- [ ] Person schema for author (name, credentials, URL)
- [ ] FAQPage schema for FAQ sections
- [ ] Fast loading (<2.5s LCP — AI crawlers have timeouts too)
- [ ] Clean HTML structure (semantic tags, not div soup)
- [ ] Open Graph tags (helps AI understand page context)
- [ ] Allow AI crawlers in robots.txt (see section 7)

---

## 6. Entity Building

AI engines understand entities (people, companies, concepts), not just keywords. Build your entity presence:

| Action | Purpose | Priority |
|--------|---------|----------|
| Consistent name/description across web | Entity consolidation — AI links mentions to one entity | High |
| Google Knowledge Panel | Google recognizes you as an entity | High |
| Wikipedia page (if notable enough) | Primary authority source for all AI engines | Medium |
| Industry mentions and citations | Authority signals that reinforce entity | High |
| Author profiles on company site | E-E-A-T + entity signals | High |
| Schema markup (Organization, Person) | Structured entity data for crawlers | High |
| Crunchbase, LinkedIn company page | Cross-reference entity data | Medium |

### Entity strategy for WEB:OS
- Define your brand entity clearly on the About page
- Use consistent brand name formatting across all pages
- Link author bios to author pages with Person schema
- Reference your brand by name when citing your own data

---

## 7. AI Crawler Access

### Key AI user-agents

| Crawler | Engine | robots.txt directive |
|---------|--------|---------------------|
| GPTBot | ChatGPT / OpenAI | `User-agent: GPTBot` |
| ChatGPT-User | ChatGPT browsing | `User-agent: ChatGPT-User` |
| Claude-Web | Claude / Anthropic | `User-agent: Claude-Web` |
| PerplexityBot | Perplexity | `User-agent: PerplexityBot` |
| Googlebot | Gemini (shared) | `User-agent: Googlebot` |
| Bytespider | TikTok / Doubao | `User-agent: Bytespider` |

### Access strategy

| Strategy | When to use | robots.txt |
|----------|-------------|------------|
| Allow all | You want maximum AI citations | Don't block any AI crawlers |
| Selective allow | Want citations but concerned about training | Allow PerplexityBot + Claude-Web, block GPTBot |
| Block all AI | Don't want content used by AI | Block all AI user-agents |

**WEB:OS default recommendation:** Allow all AI crawlers. The citation benefits outweigh the training concerns for most businesses.

---

## 8. Measurement

| Metric | How to track | Frequency |
|--------|--------------|-----------|
| AI citations | Manually search your brand/topics in ChatGPT, Perplexity, Claude | Weekly |
| "According to [Brand]" mentions | Search your brand name in AI engines | Weekly |
| Competitor citations | Compare your citation share vs competitors | Monthly |
| AI-referred traffic | UTM parameters, referrer analysis (t.co for Perplexity) | Weekly |
| Content citation rate | Track which pages/topics get cited most | Monthly |

### How to test AI citation
1. Ask Perplexity a question your content answers
2. Ask ChatGPT (with search enabled) the same question
3. Ask Claude the same question
4. Note: Are you cited? Is a competitor? What format was cited?

---

## 9. Anti-Patterns

| Don't | Do | Why |
|-------|-----|-----|
| Publish without dates | Add `datePublished` + `dateModified` | AI deprioritizes undated content |
| Use vague attributions | Name sources with titles and credentials | AI needs authority signals to cite |
| Skip author info | Show credentials, link to author page | E-E-A-T applies to AI retrieval too |
| Write thin content | Comprehensive, original coverage | AI selects the most complete answer |
| Gate all content | Keep core content open, gate extras | AI crawlers can't access gated content |
| Block AI crawlers by default | Allow crawlers unless you have a specific reason | No crawl access = no citations |
| Stuff keywords unnaturally | Write naturally, focus on entities and answers | AI understands semantics, not keyword density |

---

## 10. GEO + SEO Integration in WEB:OS

Every piece of content created through WEB:OS should optimize for both:

| Writing phase | SEO action | GEO action |
|---------------|-----------|-----------|
| Brief (`/web:brief`) | Define target keyword and search intent | Define target AI question and citation goal |
| Write (`/web:write`) | Keyword in H1, meta, first paragraph | TL;DR at top, FAQ section, quotable statements |
| Review (`/web:review`) | SEO check (keyword, meta, links) | GEO check (dates, author, schema, citable facts) |
| Publish (`/web:publish`) | Submit to GSC, update sitemap | Verify AI crawler access, check schema |
| Measure (`/web:analytics`) | Track rankings and organic traffic | Track AI citations and referral traffic |

---

> AI cites content that's clear, authoritative, and easy to extract. Be the best answer — for humans and machines.

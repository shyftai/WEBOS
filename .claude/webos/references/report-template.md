# Report Templates — WEB:OS

## Report types

- **Weekly pulse** — quick status update, key web metrics, flags
- **Monthly review** — full performance analysis, SEO progress, recommendations
- **Quarterly review** — strategic assessment, trends, resource allocation

---

## Weekly Pulse Template

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  WEEKLY PULSE — {Workspace}                                     ┃
┃  Week of {date}                                                 ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

  Status: ON TRACK / NEEDS ATTENTION / PAUSED

  ┌─ Organic Traffic ───────────────────────────────────────────┐
  │                                                              │
  │  Sessions         {n}        vs last week     {+/-n%}        │
  │  Unique visitors  {n}        vs last week     {+/-n%}        │
  │  Pages/session    {n}        Bounce rate      {n}%           │
  │  Avg time on page {n}m       Organic share    {n}%           │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ SEO Snapshot ──────────────────────────────────────────────┐
  │                                                              │
  │  Keywords top 10   {n}    ({+/-n} vs last week)              │
  │  Keywords top 3    {n}    ({+/-n} vs last week)              │
  │  New rankings      {n}    Lost rankings     {n}              │
  │  Avg position      {n}    ({+/-n})                           │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ Core Web Vitals ───────────────────────────────────────────┐
  │                                                              │
  │  LCP     {n}s    {PASS/FAIL}                                 │
  │  INP     {n}ms   {PASS/FAIL}                                 │
  │  CLS     {n}     {PASS/FAIL}                                 │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  Published this week:
  - {title} — {page type} — {url}
  - {title} — {page type} — {url}

  Top performing pages:
  1. {title} — {sessions} sessions, {conversion}% conversion
  2. {title} — {sessions} sessions, {conversion}% conversion

  Flags:
  - {anything that needs attention}

  Next week:
  - {planned content}
  - {planned optimizations}
```

---

## Monthly Review Template

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  MONTHLY REVIEW — {Workspace}                                   ┃
┃  {Month Year}                                                   ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

  ┌─ Traffic Summary ───────────────────────────────────────────┐
  │                                                              │
  │                    This month   Last month   MoM change      │
  │  Organic sessions    {n}          {n}        {+/-n%}         │
  │  Direct sessions     {n}          {n}        {+/-n%}         │
  │  Referral sessions   {n}          {n}        {+/-n%}         │
  │  Total sessions      {n}          {n}        {+/-n%}         │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ SEO Progress ──────────────────────────────────────────────┐
  │                                                              │
  │  Keywords in top 10      {n}    ({+/-n} vs last month)       │
  │  Keywords in top 3       {n}    ({+/-n} vs last month)       │
  │  Domain authority        {n}    ({+/-n})                     │
  │  Backlinks acquired      {n}                                 │
  │  Pages indexed           {n}    of {n} submitted             │
  │  Avg organic CTR         {n}%                                │
  │                                                              │
  │  Best keyword gains:                                         │
  │  - "{keyword}" — #{old} → #{new} ({+/-n})                    │
  │  - "{keyword}" — #{old} → #{new} ({+/-n})                    │
  │                                                              │
  │  Biggest drops:                                              │
  │  - "{keyword}" — #{old} → #{new} ({+/-n})                    │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ Content Published ─────────────────────────────────────────┐
  │                                                              │
  │  Page type         Published  Sessions  Conversions          │
  │  ─────────────────────────────────────────────────           │
  │  Blog posts          {n}       {n}        {n}                │
  │  Landing pages       {n}       {n}        {n}                │
  │  Case studies        {n}       {n}        {n}                │
  │  Docs/guides         {n}       {n}        {n}                │
  │  Pages refreshed     {n}       {n}        {n}                │
  │  ─────────────────────────────────────────────────           │
  │  Total               {n}       {n}        {n}                │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ Conversion Funnel ─────────────────────────────────────────┐
  │                                                              │
  │  Organic visitors   {n}   ████████████████████████████  100% │
  │  Blog readers       {n}   ██████████████████████░░░░░░   75% │
  │  CTA clicks         {n}   ████░░░░░░░░░░░░░░░░░░░░░░░    8% │
  │  Form fills         {n}   ██░░░░░░░░░░░░░░░░░░░░░░░░░    3% │
  │  Leads              {n}   █░░░░░░░░░░░░░░░░░░░░░░░░░░    2% │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ Site Health ───────────────────────────────────────────────┐
  │                                                              │
  │  Core Web Vitals     {PASSING / NEEDS WORK}                  │
  │  Broken links        {n}   ({+/-n} vs last month)            │
  │  Orphan pages        {n}                                     │
  │  Redirect chains     {n}                                     │
  │  Missing meta        {n} titles, {n} descriptions            │
  │  Missing alt text    {n} images                              │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ Top Performing Pages ──────────────────────────────────────┐
  │                                                              │
  │  1. {title} — {sessions} sessions, {conversion}% CVR        │
  │  2. {title} — {sessions} sessions, {conversion}% CVR        │
  │  3. {title} — {sessions} sessions, {conversion}% CVR        │
  │  4. {title} — {sessions} sessions, {conversion}% CVR        │
  │  5. {title} — {sessions} sessions, {conversion}% CVR        │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  ┌─ Spend ─────────────────────────────────────────────────────┐
  │                                                              │
  │  Monthly budget:   ${budget}                                 │
  │  Spent:            ${spent}     ████████░░░░  {pct}%         │
  │  Cost per lead:    ${cpl}                                    │
  │  By tool:                                                    │
  │    Ahrefs:    ${n}    Firecrawl:  ${n}    Claude:  ${n}      │
  │                                                              │
  └──────────────────────────────────────────────────────────────┘

  Recommendations:
  1. {data-backed recommendation}
  2. {data-backed recommendation}
  3. {data-backed recommendation}

  Plan for next month:
  - {planned content and optimizations}
```

---

## Quarterly Review Template

Same structure as monthly but with:
- Quarter-over-quarter trends for all metrics
- Topic cluster performance by hub
- Content ROI analysis (cost per lead by content type)
- Strategic alignment assessment (content vs business goals)
- Competitive positioning update (ranking overlaps, content gaps)
- Resource allocation review (time spent vs results per content type)
- Recommendations for next quarter's content strategy

---

## Notes

- All reports use the WEB:OS box style from ui-brand.md
- Include benchmark comparisons from BENCHMARKS.md where relevant
- Highlight metrics above or below benchmarks with [GREEN] or [RED]
- Reports can be exported as markdown files to `reports/`

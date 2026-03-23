# Slack Notifications — WEB:OS

## Configuration

Notifications are sent via Slack MCP server when available. Set up by connecting Slack MCP in Claude Code.

1. Ensure Slack MCP is connected in Claude Code
2. Set the notification channel in `global/COLLABORATION.md`:
   ```
   ## Notifications
   slack_channel: #webos-alerts
   slack_enabled: true
   ```
3. Optionally set per-workspace channels in `workspace.config.md`:
   ```
   slack_channel: #brand-name-web
   ```

---

## Alert types

### Critical (always notify if Slack is connected)

| Event | Message format |
|-------|---------------|
| Core Web Vitals failing | `[{workspace}] CWV alert: {page/site} — LCP {n}s, CLS {n}, INP {n}ms` |
| Ranking drop >5 positions | `[{workspace}] SEO alert: "{keyword}" dropped from #{old} to #{new}` |
| Organic traffic drop >20% WoW | `[{workspace}] Traffic alert: organic down {pct}% vs last week ({n} → {n})` |
| Broken links on live site | `[{workspace}] Broken links: {n} 4xx errors detected on live pages` |
| Index coverage drop | `[{workspace}] Indexing alert: {n} pages dropped from Google index` |
| CMS publish error | `[{workspace}] Publish failed: {page} — {error detail}` |
| Server errors (5xx) | `[{workspace}] Server error: {n} pages returning 5xx` |

### Important (notify during active work)

| Event | Message format |
|-------|---------------|
| Content published to live site | `[{workspace}] Published: "{title}" → {url}` |
| Content refresh completed | `[{workspace}] Refreshed: "{title}" — updated {n} sections, {n} links` |
| New keyword ranking (first page) | `[{workspace}] Ranking: "{keyword}" entered page 1 at #{position}` |
| Crawl budget alert | `[{workspace}] Crawl alert: {pct}% of crawl budget consumed — {n} pages crawled` |
| Redirect chain detected | `[{workspace}] Redirect chain: {url} → {n} hops — needs cleanup` |
| Orphan page detected | `[{workspace}] Orphan: "{title}" has 0 internal links — needs linking` |

### Informational (optional — enable per workspace)

| Event | Message format |
|-------|---------------|
| Weekly SEO report ready | `[{workspace}] Weekly SEO report ready — {n} keywords tracked, {n} changes` |
| Content audit complete | `[{workspace}] Content audit: {n} pages reviewed, {n} flagged for refresh` |
| Internal link audit complete | `[{workspace}] Link audit: {n} orphans, {n} broken links, {n} thin pages` |
| Sitemap updated | `[{workspace}] Sitemap updated: {n} pages submitted, {n} indexed` |
| Competitor content detected | `[{workspace}] Competitor: {competitor} published "{title}" targeting "{keyword}"` |

---

## How to send

When a notification trigger fires:

1. Check if `slack_enabled: true` in COLLABORATION.md
2. Determine the correct channel (workspace-specific or global)
3. Send via Slack MCP: `mcp__claude_ai_Slack__slack_send_message`
4. Format: plain text, no markdown formatting, keep under 200 characters
5. If Slack MCP is not available, display the notification inline with `!!` prefix

---

## User control

Users can configure notifications during onboarding or at any time:
- `slack_enabled: true/false` — master toggle
- `notify_critical: true` — CWV failures, ranking drops, traffic drops, broken links
- `notify_important: true` — publishes, new rankings, crawl alerts
- `notify_info: false` — reports, audits, sitemap updates

Default: critical only.

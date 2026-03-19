# API Reference — WEB:OS (Content Publishing + SEO)

Dangerous and destructive endpoint reference for content publishing and SEO tools. **HARD GATE — always stop and confirm before calling any endpoint below.**

Last updated: 2026-03-13

**Rules (apply to ALL platforms):**
1. Never call a DELETE endpoint without explicit user confirmation showing the exact blast radius
2. Always prefer unpublishing/archiving over hard deletes
3. Publishing operations on live sites are production deployments — treat them with the same caution
4. Log all destructive API calls in `logs/decisions.md` with full context
5. Check remaining API credits BEFORE any SEO tool query
6. Never exceed 80% of any documented rate limit — build in buffer
7. When in doubt, the safe alternative is always "do nothing and ask"

---

## Quick Reference — Danger Summary Table

| Platform | Highest-Risk Endpoint | Worst Case | Recovery |
|----------|----------------------|-----------|----------|
| **Buffer** | `DELETE /updates/{id}` | Scheduled post permanently deleted | None — must recreate |
| **Buffer** | Channel disconnect | All scheduled posts for channel destroyed | Must reconnect and reschedule |
| **Ahrefs** | Credit-intensive queries | Entire monthly API credit budget burned in minutes | None — credits consumed, wait for next cycle |
| **SEMrush** | Credit-intensive queries | API unit budget exhausted | None — must purchase more or wait |
| **Webflow** | `POST /sites/{id}/publish` | Broken content pushed to live site | Must fix and republish — live site is broken in the meantime |
| **Webflow** | `DELETE /collections/{id}` | Entire CMS collection + all items destroyed | None — permanent |
| **Google Search Console** | `POST /urlRemovals:add` | URLs removed from Google search results for 6 months | Can cancel, but re-indexing takes weeks |

---

## 1. Buffer (api.bufferapp.com)

**Auth:** OAuth2 access token in `Authorization: Bearer {token}`
**Base URL:** `https://api.bufferapp.com/1`
**Rate limits:** 60 requests/minute for most endpoints. Publishing: lower limits (not publicly documented). Exceeding returns 429.

### DELETE/Destructive Endpoints

| Endpoint | Blast Radius | Irreversible? | Safe Alternative |
|----------|-------------|---------------|-----------------|
| `DELETE /updates/{id}` | Permanently deletes a scheduled, sent, or draft post. If scheduled, the post will never be published. No archive, no recovery. | YES | Move to draft status instead: `POST /updates/{id}/move_to_top` to requeue, or simply leave in queue. |
| `POST /updates/{id}/destroy` | Same as DELETE — permanently destroys an update. Exists as an alternative endpoint. | YES | Reschedule to a far-future date if you want to "remove" without destroying. |
| `POST /profiles/{id}/schedules/update` | Changes the posting schedule for a profile/channel. If set incorrectly (e.g., empty schedule), all queued posts will never be published. | NO — can fix schedule, but missed posting windows are gone | Review current schedule before modifying. Never set an empty schedule. |
| `POST /profiles/{id}/updates/reorder` | Reorders the posting queue. Can accidentally move time-sensitive content to wrong slots. | NO — can reorder again | Verify the full queue order before committing. |
| `POST /profiles/{id}/updates/shuffle` | **Randomly shuffles all posts in the queue.** Any carefully planned content calendar is destroyed. Time-sensitive posts land on random dates. | NO — can manually reorder, but the original order is lost | Never call this on a production queue. Only use on test profiles. |

### Channel Management Risks

| Action | Risk | Mitigation |
|--------|------|------------|
| Disconnecting a social channel | ALL scheduled posts for that channel are permanently deleted. Reconnecting creates a fresh profile with empty queue. | Export all scheduled posts before disconnecting. |
| Reconnecting a channel | Creates a new profile ID. All automations, webhooks, and integrations referencing the old profile ID break. | Update all integrations after reconnecting. |
| OAuth token expiry | Buffer cannot post if the OAuth token for the social platform expires. Posts silently fail. | Monitor for failed posts. Re-authenticate promptly. |

### Unexpected Behaviors
- **Buffer does not retry failed posts.** If a post fails (API error, token expiry, rate limit on the social platform), it moves to "Failed" status. It will NOT automatically retry.
- **Sent posts can be deleted from Buffer but not from the social platform.** Deleting a sent update in Buffer removes it from Buffer's analytics but the post remains live on Twitter/LinkedIn/etc.
- **Queue is FIFO.** The posting schedule determines when Buffer picks the next item from the queue. If you reorder posts, they publish at the next available schedule slot — not at the time originally intended.
- **Multi-image posts have platform-specific limits.** Buffer silently drops excess images rather than erroring. You may think you posted a carousel but only 1 image went out.
- **Analytics retention varies by plan.** Free plans retain 30 days of analytics. Deleting a post loses analytics immediately. Paid plans retain longer but deletion still destroys post-level analytics.

---

## 2. Ahrefs (api.ahrefs.com)

**Auth:** API token in `Authorization: Bearer {token}`
**Base URL:** `https://api.ahrefs.com/v3`
**Rate limits:** Varies by plan. Credits deducted per query based on data volume returned. Monthly credit allocation resets on billing date.

### No DELETE Endpoints (Read-Only)

Ahrefs API is entirely read-only. There are no endpoints that modify, create, or delete data. The risk is purely **credit-based**.

### Credit-Burning Risks

| Endpoint | Credit Cost | Risk | Mitigation |
|----------|-------------|------|------------|
| `GET /site-explorer/all-backlinks` | 1 credit per row returned. Large sites can have millions of backlinks. | **CATASTROPHIC credit burn.** A single query on a high-authority domain (e.g., wikipedia.org) can consume your entire monthly allocation. | Always use `limit` parameter. Start with `limit=100`. Check total count with `GET /site-explorer/overview` first. |
| `GET /site-explorer/organic-keywords` | 1 credit per row returned. | Same risk as backlinks for sites ranking for many keywords. | Use `limit` and filter parameters. |
| `GET /site-explorer/referring-domains` | 1 credit per row returned. | Less risky than backlinks but still significant for large sites. | Limit and paginate. |
| `GET /site-explorer/top-pages` | 1 credit per row returned. | Can return thousands of pages for large sites. | Use `limit`. |
| `GET /keywords-explorer/keyword-overview` | Variable credits. | Less expensive per query but adds up in bulk. | Batch keyword research carefully. |
| `GET /site-explorer/overview` | 2 credits (fixed). | Cheap — use this to gauge data volume before detailed queries. | Always call this first. |

### Credit Management Rules

1. **Always check overview first.** Before querying backlinks/keywords, call the overview endpoint to see total counts. If a site has 5M backlinks, don't query all-backlinks without a strict limit.
2. **Cache aggressively.** Ahrefs data changes slowly (weekly index updates). Cache results for at least 7 days.
3. **Use filters to reduce result sets.** Filter by DR (Domain Rating), traffic, language, etc. to reduce rows returned.
4. **Monitor credit balance.** `GET /subscription/info` shows remaining credits. Check before any large query.
5. **Credits do NOT roll over.** Unused credits expire at billing cycle end. But this is NOT a reason to burn them — overspending in one batch means no credits for the rest of the month.

### Unexpected Behaviors
- **Credit consumption is per-row, not per-request.** A single API call returning 10,000 rows costs 10,000 credits. The number of API calls is irrelevant — it's the data volume that matters.
- **No real-time data.** Ahrefs crawls on its own schedule. API data may be days or weeks old. Don't make decisions based on Ahrefs data alone for time-sensitive situations.
- **Rate limits are separate from credits.** You can be within your credit budget but exceed rate limits (or vice versa). Both must be managed.
- **Some endpoints return estimated data.** Traffic estimates, keyword difficulty, and CPC values are Ahrefs' models, not exact figures.

---

## 3. SEMrush (api.semrush.com)

**Auth:** API key as query parameter `key={api_key}`
**Base URL:** `https://api.semrush.com`
**Rate limits:** 10 requests/second. Monthly API unit allocation based on plan (Guru: 5,000 units/request, 30,000/day; Business: more).

### No DELETE Endpoints (Read-Only)

SEMrush API is read-only. No data modification, creation, or deletion endpoints. The risk is purely **credit/unit-based**.

### Unit-Burning Risks

| Endpoint | Unit Cost | Risk | Mitigation |
|----------|-----------|------|------------|
| `GET /?type=domain_organic` | 10 units per line returned. Max 10,000 lines per request. | **100,000 units in a single call.** A domain with 10K+ organic keywords consumes significant budget. | Use `display_limit` to cap results. Start with 100. |
| `GET /?type=domain_organic_organic` | 10 units per line. | Competitor organic keyword overlap — large result sets for big domains. | Filter by specific keywords or limit results. |
| `GET /?type=domain_adwords` | 10 units per line. | Paid keyword data — similar volume risk. | Limit and filter. |
| `GET /?type=backlinks_overview` | 10 units per line. | Backlink data — same credit-burning pattern as Ahrefs. | Limit strictly. |
| `GET /?type=url_organic` | 10 units per line. | URL-level keyword data. Lower volume but adds up across many URLs. | Batch carefully. |
| `GET /?type=phrase_all` | 10 units per line. | Keyword research — broad match can return thousands of variations. | Use exact match or strict filters. |
| Position tracking API | Variable units. | Tracking hundreds of keywords across multiple locations multiplies cost. | Track only essential keywords. Review tracked keyword list monthly. |

### Unit Management Rules

1. **Start every query with `display_limit=10` for exploration.** Scale up only after verifying the data is what you need.
2. **Cache results for 7-14 days.** SEMrush data updates monthly for most metrics. Daily re-queries waste units.
3. **Use `display_filter` to narrow results.** Filter by position, volume, CPC, etc. to reduce returned rows.
4. **Monitor unit consumption.** Check your plan dashboard for remaining units before large queries.
5. **Database selection matters.** Each country database is a separate query. Don't query all 140+ databases — pick the relevant ones.
6. **Export limits exist.** Some endpoints cap at 10,000 rows regardless of units available. Plan pagination accordingly.

### Unexpected Behaviors
- **Unit costs are per-line, per-database.** Querying the same domain in US and UK databases costs double. 10 databases = 10x the units.
- **Empty results still cost units.** If a domain has no data in a database, the API call still consumes minimum units.
- **Historical data costs more.** Adding `display_date` for historical queries may increase unit costs depending on the endpoint.
- **API and UI share the same unit pool** on some plans. Heavy API usage can lock you out of UI exports.

---

## 4. Webflow (api.webflow.com)

**Auth:** API token or OAuth2 in `Authorization: Bearer {token}`
**Base URL:** `https://api.webflow.com/v2`
**Rate limits:** 60 requests/minute per token. Exceeding returns 429. Some endpoints (publish) have lower limits.

### DELETE/Destructive Endpoints

| Endpoint | Blast Radius | Irreversible? | Safe Alternative |
|----------|-------------|---------------|-----------------|
| `POST /sites/{site_id}/publish` | **PRODUCTION DEPLOYMENT.** Publishes the current state of the site to the live domain. If CMS content is broken, missing, or in draft, the live site reflects that immediately. All visitors see the changes. | NO — can republish with fixes, but broken state is live until then | Stage changes and verify in the Webflow designer before publishing via API. Use `domains` parameter to publish to staging domain first. |
| `DELETE /collections/{collection_id}` | **CATASTROPHIC.** Permanently deletes an entire CMS collection and ALL items within it. If the collection powers blog posts, product pages, or any templated content, those pages vanish from the site on next publish. | YES — no recovery | Never delete a collection via API. Archive items individually or create a new collection and migrate. |
| `DELETE /collections/{collection_id}/items/{item_id}` | Deletes a single CMS item. The item's page disappears on next publish. If other items reference this item (via reference fields), those references break. | YES — no recovery | Set the item to "Draft" status via `PATCH` instead. Drafts are not published. |
| `DELETE /collections/{collection_id}/items` (bulk) | Bulk deletes up to 100 CMS items in a single call. | YES — no recovery | Bulk set to Draft status instead. |
| `DELETE /sites/{site_id}/webhooks/{webhook_id}` | Removes a webhook. Integrations relying on Webflow events (form submissions, CMS changes, ecommerce orders) break silently. | YES | Disable the webhook if possible. |
| `PATCH /collections/{collection_id}/items/{item_id}` with `archived: true` | Archives a CMS item. The item is hidden from the published site but NOT deleted. | NO — can unarchive | This IS the safe approach for "removing" content. |
| `PATCH /collections/{collection_id}/items/{item_id}` with `draft: true` | Sets item to draft. Unpublished from live site on next publish. | NO — can un-draft | This IS the safe approach for temporarily removing content. |
| `POST /collections/{collection_id}/items` (create) | Creates CMS items. If `live: true` is set, the item is immediately published to the live site without a separate publish step. | NO — can delete or draft | Never use `live: true` for untested content. Create as draft first. |

### Publishing Risks (CRITICAL)

| Scenario | Risk | Mitigation |
|----------|------|------------|
| Publishing with broken CMS references | Pages with broken references may show blank sections or errors on the live site. | Verify all reference fields before publishing. |
| Publishing during active editing | If a designer is editing the site while API publishes, their unsaved changes may or may not be included — behavior is unpredictable. | Coordinate publish windows. Never auto-publish. |
| Publishing to all domains | Default behavior publishes to ALL custom domains. You may intend to update only staging. | Always specify the `domains` array to target specific domains. |
| Publishing after deleting items | Deleted CMS items create 404s. If Google has indexed those pages, you get crawl errors. | Set up 301 redirects before deleting/unpublishing content. |
| Auto-publish via API on webhook trigger | If you set up a pipeline that publishes on CMS change, any CMS edit immediately goes live — including typos and draft content. | Add a manual approval step in any publish pipeline. |

### Unexpected Behaviors
- **Publish is NOT instant.** After calling the publish endpoint, the site build takes 30 seconds to several minutes depending on site size. The endpoint returns immediately but the site isn't live yet. Use webhook `site_publish` to detect completion.
- **CMS item slugs are immutable after first publish.** If you publish an item then want to change its slug, the old URL 404s unless you set up a redirect. The API will let you change the slug, but the old page vanishes.
- **Rate limits are per-token, not per-site.** If you manage multiple sites with one token, all sites share the 60 req/min limit.
- **Webflow API v2 does NOT support all v1 features.** Some endpoints (e.g., ecommerce) are only in v1. Check endpoint availability before building integrations.
- **Collection schema changes are dangerous.** Adding/removing/renaming fields on a CMS collection can break existing items if those items rely on the changed fields. Test schema changes on a duplicate collection first.
- **Form submission data is accessible via API.** `GET /sites/{id}/form-submissions` exposes all form data. Ensure API tokens are scoped appropriately — a token for CMS management should not have access to form submissions containing PII.

### Ecommerce Risks
- `POST /orders/{order_id}/fulfill` — marks an order as fulfilled. If called prematurely, customer receives fulfillment notification before product ships.
- `POST /orders/{order_id}/refund` — issues a refund. Irreversible financial action.
- `PATCH /collections/{id}/items/{id}` on product items — changing price or inventory via API takes effect immediately on the live store if the item is published.

---

## 5. Google Search Console API (searchconsole.googleapis.com)

**Auth:** OAuth2 with `https://www.googleapis.com/auth/webmasters` scope
**Base URL:** `https://searchconsole.googleapis.com`
**Rate limits:** 1,200 queries/minute (default). URL Inspection: 600 inspections/day per property, 2,000/day per site owner. Exceeding returns 429.

### DELETE/Destructive Endpoints

| Endpoint | Blast Radius | Irreversible? | Safe Alternative |
|----------|-------------|---------------|-----------------|
| `POST /webmasters/v3/sites/{siteUrl}/urlRemovals:add` | **Removes a URL from Google search results for approximately 6 months.** The page is de-indexed and stops appearing in search. Affects ALL search variants (www, non-www, etc. if property is domain-level). | PARTIAL — can cancel the removal request, but re-indexing takes weeks to months. SEO damage can be significant. | Use robots.txt `noindex` for temporary exclusion. Or use URL parameters in Search Console UI for more controlled removal. |
| `DELETE /webmasters/v3/sites/{siteUrl}` | Removes a property (website) from your Search Console account. You lose access to all performance data, coverage reports, and sitemaps. The property can be re-added but historical data access depends on verification. | PARTIAL — can re-add, but data access gaps | Remove users from the property instead of deleting it. |
| `DELETE /webmasters/v3/sites/{siteUrl}/sitemaps/{feedpath}` | Removes a sitemap from Search Console. Google stops using this sitemap for crawling prioritization. Does NOT de-index URLs in the sitemap, but may slow crawling of those URLs. | NO — can resubmit | Rarely a reason to delete a sitemap. Leave old sitemaps and submit updated ones. |
| `POST /webmasters/v3/sites/{siteUrl}/urlNotifications:publish` with `type: URL_DELETED` | Notifies Google that a URL has been deleted. Google will prioritize de-indexing. If sent for a live URL, Google may de-index a page that should be indexed. | PARTIAL — page can be re-indexed, but takes time | Only send deletion notifications for actually deleted URLs. Verify URL returns 404 before notifying. |

### URL Removal Risks (CRITICAL)

| Scenario | Risk | Mitigation |
|----------|------|------------|
| Removing a high-traffic URL | Immediate loss of organic traffic. Recovery takes weeks after cancellation. | Check search performance data for the URL before removing. Verify the URL actually needs removal. |
| Bulk URL removal via API | Can de-index hundreds of pages rapidly. If the URL pattern is wrong, you de-index valuable content. | Never automate URL removal. Process one at a time with manual verification. |
| Removing a URL that has canonical pointing to it | Other URLs with canonical tags pointing to the removed URL may also lose ranking. Canonical signals are disrupted. | Audit canonical tags before any removal. |
| Domain-level property removal | Removes a URL across ALL subdomains and protocols if using domain property. Much wider blast radius than URL-prefix properties. | Use URL-prefix properties for targeted removals. |

### Unexpected Behaviors
- **URL removal lasts 6 months, then automatically expires.** If the underlying content issue isn't fixed (page still exists, content still needs removal), the URL will reappear in search results.
- **Removal API does not verify URL ownership rigorously.** If you have verified the property, you can remove any URL under that property — including URLs you didn't intend to target due to URL pattern matching.
- **URL Inspection API is read-only but has strict quotas.** 600 inspections/day per property. Automated SEO monitoring can exhaust this quickly, leaving no quota for manual debugging.
- **Performance data has a 3-day delay.** Data for today won't appear in the API for 3 days. Making removal decisions based on "current" data means you're acting on data from 3+ days ago.
- **Search Analytics data retention is 16 months.** Data older than 16 months is inaccessible via API. Deleting a property and re-adding it does not recover data from the deletion period.
- **Verification is property-level.** Losing DNS or file verification causes you to lose access to ALL data for that property. Re-verification restores access but the gap period may miss critical alerts.

### Indexing API vs URL Removal
- **Indexing API** (`/v3/urlNotifications:publish`) is for notifying Google about new or updated content. It does NOT guarantee indexing — it's a hint.
- Sending excessive indexing requests can be seen as spam and may cause Google to ignore future requests from your property.
- Daily quota: 200 publish requests per day per property. Using this for automated publishing workflows can exhaust the quota quickly.

---

## Cross-Platform Safety Rules for WEB:OS

1. **Before any publish action (Webflow, Buffer):** Always preview the content in staging/draft first. Never auto-publish untested content.
2. **Before any URL removal (Search Console):** Verify the URL genuinely needs removal. Check organic traffic to the URL. Understand that recovery takes weeks.
3. **Credit-intensive tools (Ahrefs, SEMrush):** Always check remaining credits before queries. Start with small limits and scale up. Cache results for at least 7 days.
4. **CMS deletions (Webflow):** Always use draft/archive status changes instead of DELETE. Set up 301 redirects before removing published content.
5. **Content calendar (Buffer):** Never disconnect a channel without exporting all scheduled posts. Never shuffle a production queue.
6. **SEO data integrity:** Never delete a Search Console property. Performance data has a 16-month retention window — gaps cannot be recovered.
7. **Log everything:** Every destructive API call should be logged in `logs/decisions.md` with: timestamp, endpoint, parameters, blast radius assessment, and the reason for the action.

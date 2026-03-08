<swarm_architecture>

## Agent Swarm — Optional Parallel Execution

CONTENT:OS supports optional agent swarms for high-volume operations. Swarms are never the default —
they activate only when explicitly requested or when batch size exceeds 25 pieces.

### When to use swarms

- Batch creating 25+ social posts at once
- Generating blog outlines for an entire keyword cluster
- Repurposing one piece across 5+ channels simultaneously
- Running SEO audits across multiple pages
- Creating a month of newsletter editions

### Execution mode — Claude Code vs API

For large-scale operations, ask the user how they want to run it:

```
  How do you want to run this?

  >> Claude Code (default) — runs here, you see results in real time
     Best for: <25 pieces, interactive review, first-time runs

  >> API (faster, more scale) — runs via Anthropic API in the background
     Best for: 25-500+ pieces, batch processing, overnight runs
     Requires: ANTHROPIC_API_KEY in .env
```

**Claude Code mode:** Uses agent swarm within the current session. Interactive, real-time review, but limited by session context.

**API mode:** Spawns work via the Anthropic API. Results saved to files, user reviews when ready. Handles 100-500+ pieces without session limits.

Always ask before choosing — never default to API mode without user consent.

### When NOT to use swarms

- Single piece or small batch (<10) — sequential is faster
- Tasks requiring human approval at every step
- First workspace setup — get the workflow right sequentially first

---

## Swarm Architecture

```
                    ORCHESTRATOR
                   (stays lean — coordinates only)
                         │
              ┌──────────┼──────────┐
              │          │          │
           WAVE 1     WAVE 2     WAVE 3
           (parallel)  (after 1)  (after 2)
              │
    ┌─────────┼─────────┐
    │         │         │
  Agent A   Agent B   Agent C
  (pieces 1-10) (pieces 11-20) (pieces 21-30)
```

**Orchestrator role:**
- Loads workspace context once
- Splits work into batches
- Spawns agents per batch
- Collects results
- Presents unified output for approval
- Never executes piece-level work itself

**Agent role:**
- Receives batch of content tasks + full workspace context paths
- Reads context fresh (BRAND, AUDIENCE, TOV, PILLARS)
- Processes each piece in its batch
- Returns structured results
- Never publishes anything — returns drafts only

---

## Batch Sizing

| Operation | Default batch size | Max parallel agents |
|-----------|-------------------|---------------------|
| Social posts | 10 posts per agent | 5 |
| Blog outlines | 5 outlines per agent | 4 |
| Repurpose variants | 5 pieces per agent | 4 |
| Newsletter editions | 4 editions per agent | 3 |
| SEO audits | 10 pages per agent | 4 |

---

## Swarm Output Format

Every agent returns a structured result. Orchestrator collects all results and presents them
in a single unified view for approval.

```
<< CONTENT:OS // SWARM COMPLETE >>

  ┌─ SWARM RESULTS ───────────────────────────────┐
  │                                                │
  │  Agents spawned:  4                            │
  │  Pieces created:  38                           │
  │  Ready for review: 35                          │
  │  Flagged:         3 (need manual review)       │
  │  Errors:          0                            │
  │                                                │
  └────────────────────────────────────────────────┘
```

Then each piece is presented sequentially for approval — or if the user trusts the output,
they can batch-approve with `>> Approve all` (only available after reviewing at least 3 samples).

---

## Safety Rules

1. **Swarm agents never publish anything** — they draft only. All publishing requires human approval.
2. **Credit checks happen once at orchestrator level** before spawning — not per agent.
3. **Every swarm run is logged** in COSTS.md with agent count, batch sizes, and approval status.
4. **Batch-approve requires sample review** — user must review at least 3 drafts before `Approve all` unlocks.
5. **Quality gates run per piece** — agents validate individually, orchestrator spot-checks.

</swarm_architecture>

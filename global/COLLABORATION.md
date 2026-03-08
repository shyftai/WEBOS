# Collaboration Mode

## Mode: solo

Options:
- `solo` — all state is file-based, single operator
- `team` — shared state via Supabase, multi-user

## Solo mode (default)
- All files stored locally in workspace folders
- No external dependencies
- Full functionality, single operator

## Team mode
- Requires Supabase project (free tier works)
- Shared content calendar, briefs, and approvals
- Multi-writer coordination
- Required keys in .env: SUPABASE_URL, SUPABASE_ANON_KEY

### Setup
1. Create a Supabase project at supabase.com
2. Add SUPABASE_URL and SUPABASE_ANON_KEY to .env
3. Run /content:onboard with team mode selected

# MOLI — map-first (pre-charity)

**Primary job:** free, account-gated road sightings map (data collection).
**Secondary:** possible charity formation later — not required for the map to work.

## Product rules

| Rule | Detail |
|------|--------|
| Browse map | Public, no login |
| Add a pin | Free, requires Princess of Reality account |
| Public pins | Moderated only (`status: approved`) |
| Not a charity | Copy stays clear until registration |
| Safety | Never encourage stopping on fast roads |

## Auth path

1. **Now:** local contributor mode → queue in localStorage
2. **Next:** Supabase Auth (shared with hub) + moli_reports table
3. Approve → public sightings feed

## Deploy

Upload as `moli/` → https://haylynn.github.io/haylynn/moli/

# C1C Bot Surface — Source of Truth

This repo stores the **canonical command surfaces** for all C1C bots and a **migration plan** to harmonize ops commands across bots.

## Layout
```
c1c-bot-surface/
├─ data/
│  ├─ ops_commands.json         # shared ops (canonical names + aliases)
│  ├─ bot_specific.json         # bot-unique commands
│  ├─ migration_plan.csv        # old→new + progress flags
│  └─ decision_log.csv          # decisions with reasons & next steps
└─ schema/
   ├─ ops_commands.schema.json
   └─ bot_specific.schema.json
```

## Editing workflow
- Propose changes via PRs editing files in `data/`.
- Keep ops names canonical; use `migration_plan.csv` to track aliases and help/doc updates.
- After merge, Google Sheets will pull the updates on the next scheduled sync.

## Status values
- **Everywhere** — implemented in all bots
- **In progress** — partially implemented or under active migration
- **Missing** — not implemented yet

## Apps Script endpoints (raw GitHub)
Use the `raw.githubusercontent.com` URLs, e.g.:
```
https://raw.githubusercontent.com/YOUR_ORG/c1c-bot-surface/main/data/ops_commands.json
https://raw.githubusercontent.com/YOUR_ORG/c1c-bot-surface/main/data/bot_specific.json
https://raw.githubusercontent.com/YOUR_ORG/c1c-bot-surface/main/data/migration_plan.csv
https://raw.githubusercontent.com/YOUR_ORG/c1c-bot-surface/main/data/decision_log.csv
```

---

*Generated: 2025-09-29*

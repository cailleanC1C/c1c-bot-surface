# 🔹 C1C Bot Ops Contract v1.0

All C1C bots (Reminder, WelcomeCrew, Matchmaker, Achievements) must implement this **core set of operational commands**.
They guarantee consistent naming, uniform response formatting, and optional aliases for backward compatibility.

---

## 1. Core Commands

| Command       | Purpose                                    | Output (canonical)                                                                                                                                     | Notes / Aliases                                  |
| ------------- | ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------ |
| `!ping`       | Quick “alive” check                        | ✅ `<BotName> vX.Y.Z` alive — latency `XXms`                                                                                                            | Short one-line.                                  |
| `!health`     | Detailed health check                      | Header: Bot name + version<br>Bullets: uptime, Discord conn, Sheets conn, Google API quota, config sources, last reload<br>Footer: latency + timestamp | Primary status cmd.                              |
| `!digest`     | Post health digest to channel              | Same content as `!health`, but as a **posted message** instead of ephemeral reply                                                                      | New core command.                                |
| `!reload`     | Reload bot config/templates & clear caches | ✅ Reloaded config/templates; sources listed                                                                                                            | Harmonizes `!reloadconfig`, `!welcome-refresh`.  |
| `!checksheet` | Run sheet diagnostics                      | Sheet name(s), row counts, last sync timestamp                                                                                                         | Harmonizes `!sheetsstatus`.                      |
| `!env`        | Show required env vars & hints             | ✅ present / ❌ missing per var; with short hint                                                                                                         | Harmonizes `!env_check`.                         |
| `!config`     | Show current config & short summary        | Config sources, active tabs, status flags                                                                                                              | Combines `!testconfig` + `!configstatus`.        |
| `!reboot`     | Soft restart                               | ✅ Restart initiated; uptime resets                                                                                                                     | No bot left behind — must be present everywhere. |

---

## 2. Response Formatting Standard

**Header**

```
✅ C1C-Reminder v1.0.3 — Health
```

**Body (bullets, in this order)**

* Uptime: `3d 4h 22m`
* Discord: Connected ✅ (latency XXms)
* Sheets: ✅ (last sync 12:33 UTC)
* Google API quota: 1,234/10,000 used
* Config sources: `bot_info!A:D` (last reload 10:15 UTC)
* Extra (bot-specific health notes)

**Footer**

```
Latency: XXms • Checked at 2025-09-29 18:44 UTC
```

All other ops commands (`!reload`, `!checksheet`, `!env`, `!config`, `!reboot`) follow the **same template**:

* ✅/❌ emoji to show success/failure
* Clear, one-line summary
* Footer with timestamp

---

## 3. Scope & Broadcast Rules

* **Broadcast**: `!ping`, `!health`, `!digest` → All bots reply if run without qualifier.
* **Scoped**: `@BotName ping` or `!reminder ping` → Only that bot replies.
* **Namespace**: Bots must recognize `!reminder`, `!welcome`, `!matchmaker`, `!achievements` prefixes for all ops commands. Example:

  * `!reminder health`
  * `!welcome reload`

---

## 4. Aliases (backward compat)

* `!reloadconfig` → `!reload`
* `!welcome-refresh` → `!reload`
* `!sheetsstatus` → `!checksheet`
* `!env_check` → `!env`
* `!testconfig` / `!configstatus` → `!config`

Aliases are kept functional but not advertised. Usage logged for later sunset.

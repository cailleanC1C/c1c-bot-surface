# C1C Bot-Specific Commands v1.0

## Reminder (C1C Reminder)

**Members**

* `!holiday` — Open UI to file/cancel absences.
* `!myreminders` — Personal snooze timers list.

**Leaders**

* `!summary <Clan>` — Show reminder setup for a clan.
* `!summaryall` — All clans’ setups, paginated.
* `!tanking <mode> <clan> [on|off|announce|status|here] [text=…]` — Tanking controls + comms.
* `!next [<Clan>]` — Show next scheduled times (all modes, per our policy).

**Admin / Testing**

* `!testrem <mode> <clan> [2m|1h|…|in=MIN]` — Dry-run a normal reminder.
* `!testcow <cow_mode> [in=MIN] [text=…]` — Dry-run a CoW cycle post.
* `!testcustom <Label> [2m|1h|…|in=MIN] [here]` — Dry-run a custom reminder.
* `!tanking [default|variant=…] [pr|nonpr|cvc=…] [here]` — Tanking preset helpers.

> Uses core ops set (`!ping`, `!health`, `!digest`, `!reload`, `!checksheet`, `!env`, `!config`, `!reboot`).

---

## Welcome Crew (C1C-WelcomeCrew)

**Recruiters & Mods (user actions)**

* (Automations driven by watcher) — On Close Ticket, tag picker & sheet write.

**Admin / Maintenance**

* `!watch_status` — Show watcher ON/OFF + last actions.
* `!watch_on` / `!watch_off` — Toggle thread watchers.
* `!backfill_tickets` — Scan/ingest historical tickets.
* `!backfill_details` — Pull thread details for missing rows.
* `!dedupe_sheet` — Remove dupes; keep newest by rule.
* *(Optional utility commands present in help:)* `!keep_newest_entry`, `!upload_diffs` (if you’ve exposed them; keep as internal if not needed by staff).

> Harmonized to core:
>
> * `!sheetsstatus` → **alias of** `!checksheet`
> * `!env_check` → **alias of** `!env`
> * `!reload` already present (also clears sheet cache)
> * Keep `!reboot`, `!ping`, `!health`, `!digest`, `!config`.

---

## Matchmaker (C1C-Matchmaker)

**For Recruiters**

* `!clanmatch` — Open the placement panel.
* `!clan <TAG>` — Quick view of a clan.
* `!welcome` — Onboarding/welcome flow.

**For Members**

* `!clansearch` — Browse/open spots.

**Admin / Maintenance**

* `!welcome-on` / `!welcome-off` — Toggle welcome automations.
* `!welcome-status` — Status of welcome automations.
* `!welcome-refresh` — **alias of** `!reload` (refresh templates + cache under the hood).

> Uses full core ops set (`!ping`, `!health`, `!digest`, `!reload`, `!checksheet`, `!env`, `!config`, `!reboot`).

---

## Achievements (C1C Appreciation & Claims)

**Staff**

* `!listach [filter]` — List loaded achievements.
* `!findach <text>` — Search achievements.
* `!testach <key> [where]` — Preview an achievement embed.
* `!testlevel [query] [where]` — Preview a level embed.

> Harmonized to core:
>
> * `!testconfig`, `!configstatus` → **alias of** `!config`
> * `!reloadconfig` → **alias of** `!reload`
> * Uses `!ping`, `!health`, `!digest`, `!checksheet`, `!env`, `!reboot` as per contract.

---

## Namespace & Channel Behavior (applies to all)

* **Broadcast in admin channels**: `!ping`, `!health`, `!digest` may elicit multi-bot responses.
* **Scoped anywhere**: `@BotName ping` or `!reminder ping` (namespaced prefixes: `!reminder`, `!welcome`, `!matchmaker`, `!achievements`).
* **Cooldown**: Optional suppression after N bots reply to broadcast to reduce spam (kept in the contract).

---

## Deprecation ledger (so we don’t forget)

* `!sheetsstatus` → `!checksheet` (alias now, stop advertising)
* `!env_check` → `!env` (alias now, stop advertising)
* `!reloadconfig` → `!reload` (alias now, stop advertising)
* `!welcome-refresh` → `!reload` (alias now, keep text “refresh templates” in `!reload` success line)
* `!testconfig` / `!configstatus` → `!config` (aliases now)

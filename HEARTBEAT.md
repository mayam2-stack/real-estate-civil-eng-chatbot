# HEARTBEAT.md — Self-Healing Monitor / مراقب التعافي الذاتي

*Nadia checks this on every heartbeat to ensure the team is running smoothly.*

## Cron Health Check / فحص صحة المهام المجدولة

Check if any daily cron jobs have stale lastRunAtMs (>26 hours since last run). If stale, trigger them via CLI.

### How to find job IDs / كيف تجد معرفات المهام

To see all scheduled jobs and their IDs, run:

```bash
openclaw cron list
```

This prints a table with each job's ID, name, schedule, and last run time.

To force-run a stale job, copy its ID from that list and run:

```bash
openclaw cron run <paste-job-id-here> --force
```

> 💡 Job IDs are assigned by OpenClaw when you create cron jobs. You don't make them up — you find them with `openclaw cron list`.

## Jobs to Monitor / المهام المراقبة

### Morning Sweep (8:00 AM) — Tariq Research

- Check `intel/DAILY-INTEL.md` was updated today
- Verify competitor/client/investor data is fresh
- If stale → force re-run Tariq's morning research

### Data Sync (9:00 AM) — Layla Data Check

- Check `sheets/` folder for today's summaries
- Verify tracker files are accessible and readable
- If stale → force re-run Layla's data sync

### Technical Review (10:00 AM) — Khalid Technical

- Check `technical/` folder for any new CAD analysis
- Verify project file inventory is current
- If stale → force re-run Khalid's technical sweep

### Feasibility Update (11:00 AM) — Sara Feasibility

- Check `feasibility/` for updated reports
- Verify financial data is current
- If stale → force re-run Sara's feasibility check

### Evening Summary (5:00 PM) — Nadia Wrap-up

- Compile all agent outputs into daily summary
- Update `memory/YYYY-MM-DD.md` with the day's activity
- Flag any items needing human attention tomorrow

## System Checks / فحوصات النظام

- [ ] All agent SOUL.md files are accessible
- [ ] `data/` folder is mounted and readable
- [ ] Telegram bot is responsive
- [ ] No file conflicts (one-writer-many-readers pattern intact)

## Recovery Actions / إجراءات التعافي

If gateway crashes:

```bash
openclaw gateway restart
```

If an agent is unresponsive, restart it by name (use one of: `tariq`, `layla`, `khalid`, `sara`, `nadia`):

```bash
openclaw agent restart tariq
```

If memory files are corrupted:

- Restore from daily logs in `memory/`
- Rebuild MEMORY.md from last 7 days of daily notes

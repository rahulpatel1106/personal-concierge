# Pick Up Here — Next Session

**Last worked:** 2026-04-13 (evening)
**Goal:** Finish Layer 3 — weekly Friday-morning concierge briefing via remote scheduled agent.

## Decision already made
- **Option A**: private GitHub repo + remote trigger that clones it weekly and commits a briefing back.

## What I (the user) need to do before the next session
1. Go to https://github.com/new
2. Create a **private** repo named `personal-concierge` (or whatever you prefer — just remember the name)
3. Do NOT initialize it with a README (we'll push existing content)
4. Paste the repo URL to Claude next session

## What Claude will do next session
1. Initialize git in `C:\Users\haven\.claude\projects\personal-concierge\`
2. Copy the relevant memory files from `~/.claude/projects/c--Users-haven--claude/memory/user_concierge_*.md` + `user_personal_concierge_profile.md` into a `context/` subfolder in the repo (so the remote agent can read them)
3. Add a `briefings/` folder for weekly outputs
4. Commit + push to the new private repo
5. Create the remote trigger via `RemoteTrigger`:
   - **Schedule:** Fridays, 8am America/New_York = **13:00 UTC** → cron `0 13 * * 5`
   - **Model:** claude-sonnet-4-6
   - **Repo:** the new private repo
   - **Prompt:** self-contained briefing instructions (draft below)
6. Run it once manually to verify output
7. Give user the dashboard link

## Draft prompt for the remote agent (refine before shipping)

> You are a personal concierge agent. Read everything in `context/` to understand the user's profile, preferences, wife, travel history, budget style, and active trips. Read `reference/key-dates.md` and all files in `trips/` for active trip status. Read `reference/recommendations-log.md` for history.
>
> Today's date is the current date. Produce a weekly briefing as a new file at `briefings/YYYY-MM-DD.md` with these sections:
>
> 1. **This week's focus** — the single most time-sensitive thing (1-2 sentences)
> 2. **Active trips** — status, what needs booking, what's overdue
> 3. **Upcoming dates** — anything in the next 8 weeks (anniversary, birthdays, ADE window)
> 4. **Fresh ideas (3 max)** — date nights, weekend trips, or experiences that fit the profile and the current week/season. Each with a 1-line "why it fits."
> 5. **Open questions** — anything the user needs to decide to unblock planning
>
> Constraints:
> - Pull from memory context, not generic suggestions
> - Smart-luxury tone, not corporate
> - Flag anything time-sensitive (award space, ticket drops, reservation windows)
> - Keep it under 500 words — this is a briefing, not an essay
> - Commit the briefing file with message `briefing: YYYY-MM-DD`

## Active context for next session
- Budapest + Vienna trip locked: **Aug 12-18, 2026**, couple-only, grandparent drop-off
- See [trips/2026-08-budapest-vienna/brief.md](trips/2026-08-budapest-vienna/brief.md)
- Open decisions on that trip: night split, Polaris award check, childcare routing (NJ vs NC), hotel tier, birthday dinner booking

## Environment note
- Environment ID for remote trigger: `env_01XiWkyvWgDE7RsDkzfi9Sgf` (Default, just created)

# Personal Concierge

A second brain for trips, dates, and life recommendations — tuned to me, my wife, and (sometimes) our daughter.

## How to use

- **On-demand:** Ask Claude `/concierge <request>` — e.g. `/concierge weekend in Charleston`, `/concierge date night Friday`, `/concierge cocktail bars in Atlanta for my wife`.
- **Proactive:** A weekly Friday-morning agent pings me with timely ideas (anniversaries, birthdays, long weekends, ADE windows, ticket drops).

## Folder map

- `trips/` — one folder per trip. Itinerary, bookings, picks, post-trip notes.
- `reference/` — durable info: key dates, wishlist, recommendations log, blackout dates.
- `README.md` — this file.

All persistent personal data (preferences, wife profile, food/drink, travel history, budget style) lives in Claude's memory at `~/.claude/projects/c--Users-haven--claude/memory/`. The concierge always reads those first.

## Operating principles

1. Never recommend generic AI slop. Pull from memory first, the web second, then synthesize.
2. Default planning unit = couple. Always confirm if daughter is joining.
3. Smart-luxury: splurge on the flight + the experience, save on the bed.
4. One anchor nice meal per trip + lots of street food / local hotspots.
5. Wanderer-friendly itineraries: 1 anchor activity per day, rest is open.
6. Always flag what needs to be pre-booked.
7. Score Europe trips partly on whether they hit the "3 new countries per year" goal.

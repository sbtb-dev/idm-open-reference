# Operator Relations — Index

Sourced organization-to-environment relationships: who holds which role, as of when.

An edge claims only the role(s) listed, as of the cited date. It establishes nothing
about quality, openness to outreach, deal terms, or permanence, and absence of an
edge establishes nothing at all — this list is not, and will never be, complete.
Ordering is alphabetical by environment and carries no meaning. See `README.md` for
the role vocabulary and this record type's stricter sourcing rule.

## Edges

| Environment | Organization | Role(s) | As of | Entry |
|---|---|---|---|---|
| ARC Raiders | Embark Studios | operates | 2026-09-10 | [edges/arc-raiders--embark-studios.md](edges/arc-raiders--embark-studios.md) |
| Asphalt Legends Unite | Gameloft | operates | 2026-09-25 | [edges/asphalt-legends-unite--gameloft.md](edges/asphalt-legends-unite--gameloft.md) |
| Brawl Stars | Supercell | operates | 2026-09-10 | [edges/brawl-stars--supercell.md](edges/brawl-stars--supercell.md) |
| Driving Empire | Voldex | operates | 2026-09-10 | [edges/driving-empire--voldex.md](edges/driving-empire--voldex.md) |
| EA SPORTS FC 26 | Electronic Arts | operates | 2026-09-10 | [edges/ea-sports-fc-26--electronic-arts.md](edges/ea-sports-fc-26--electronic-arts.md) |
| Free Fire | Garena | operates | 2026-09-10 | [edges/free-fire--garena.md](edges/free-fire--garena.md) |
| Genshin Impact | HoYoverse | operates | 2026-09-10 | [edges/genshin-impact--hoyoverse.md](edges/genshin-impact--hoyoverse.md) |
| GOALS | GOALS AB | operates | 2026-09-10 | [edges/goals--goals-ab.md](edges/goals--goals-ab.md) |
| GTA Online | Rockstar Games | operates | 2026-09-10 | [edges/gta-online--rockstar-games.md](edges/gta-online--rockstar-games.md) |
| League of Legends: Wild Rift | Riot Games | operates | 2026-09-10 | [edges/league-of-legends-wild-rift--riot-games.md](edges/league-of-legends-wild-rift--riot-games.md) |
| Minion Rush | Gameloft | operates | 2026-09-25 | [edges/minion-rush--gameloft.md](edges/minion-rush--gameloft.md) |
| Mobile Legends: Bang Bang | MOONTON Games | operates | 2026-09-10 | [edges/mobile-legends-bang-bang--moonton-games.md](edges/mobile-legends-bang-bang--moonton-games.md) |
| NBA 2K27 | 2K | operates | 2026-09-10 | [edges/nba-2k27--2k.md](edges/nba-2k27--2k.md) |
| Overwatch 2 | Blizzard Entertainment | operates | 2026-09-10 | [edges/overwatch-2--blizzard-entertainment.md](edges/overwatch-2--blizzard-entertainment.md) |
| PGA TOUR 2K25 | 2K | operates | 2026-09-10 | [edges/pga-tour-2k25--2k.md](edges/pga-tour-2k25--2k.md) |
| PUBG MOBILE | Level Infinite | operates | 2026-09-10 | [edges/pubg-mobile--level-infinite.md](edges/pubg-mobile--level-infinite.md) |
| Riders Republic | Ubisoft | operates | 2026-09-10 | [edges/riders-republic--ubisoft.md](edges/riders-republic--ubisoft.md) |
| Rocket League | Psyonix | operates | 2026-09-10 | [edges/rocket-league--psyonix.md](edges/rocket-league--psyonix.md) |
| skate. | Electronic Arts | operates | 2026-09-10 | [edges/skate--electronic-arts.md](edges/skate--electronic-arts.md) |
| The Sims 4 | Electronic Arts | operates | 2026-09-10 | [edges/the-sims-4--electronic-arts.md](edges/the-sims-4--electronic-arts.md) |
| Toca Boca World | Toca Boca | operates | 2026-09-10 | [edges/toca-boca-world--toca-boca.md](edges/toca-boca-world--toca-boca.md) |

## Stale (as_of over 12 months old)

Flagged here rather than silently left current. A stale edge is reviewed, re-sourced,
or removed — see `README.md`'s Maintenance section.

| Environment | Organization | Role(s) | As of | Entry |
|---|---|---|---|---|
| BGMI | KRAFTON India | operates | 2023-05-19 | [edges/bgmi--krafton-india.md](edges/bgmi--krafton-india.md) |

Filed already stale: the only qualifying independent source found (TechCrunch, reporting
KRAFTON India's 2023 relaunch of BGMI after its India ban) predates this pass by over three
years. Nothing found during this pass's search updates it with a fresher qualifying source —
trade coverage of KRAFTON India's ongoing BGMI esports program (e.g. Digit.in, 2025-11-04)
describes the relationship without stating it outright, so it doesn't clear the bar. Left
here rather than unfiled since the underlying fact is citable, just not recently re-confirmed.

## Sweeps run

Logged so that gaps read as gaps rather than as judgments.

| Date | Scope | Edges filed | Notes |
|---|---|---|---|
| 2026-09-10 | Pass 1 of `notes/proposals/roster-operator-edge-inventory-guide.md` (`idm-on-ramp`) — brand-presence outward, all 20 `brand-presence/entries/` checked | 20 (19 to Edges, 1 — BGMI — filed directly to Stale) | Each `brand-presence` entry's own `operator:` field was treated as a lead only and re-sourced against this record type's stricter bar (platform storefront attribution or independent trade press, never either party's own material) — in every filed case the lead held up under re-sourcing, except **PUBG MOBILE**, where Google Play's own listing (package `com.tencent.ig`) attributes Developer to Level Infinite (Tencent's publishing label), not KRAFTON (the `brand-presence` lead) — filed under Level Infinite once a `vendor-census` entry for it existed (added 2026-09-10, same day, from a separate verification pass), resolving what this pass had initially left unfiled for lack of a census entry to land on. Two other entries required a second look before filing: **GOALS** — initially misrouted to Roblox on a wrong platform assumption, corrected by checking Steam directly, where GOALS AB is both Developer and Publisher. **Mobile Legends: Bang Bang** — Google Play's Developer field names MOONTON while the App Store's Seller field for the same app names a different-looking legal entity (YOUNGJOY TECHNOLOGY LIMITED); re-checking Google Play's own page directly (past an initial fetch failure) found its own "About the developer" trader-disclosure block, under the same MOONTON developer ID, also names YoungJoy Technology Limited with a moonton.com contact address — the platform's own page ties the two names to one entity, clearing the bar. |
| 2026-09-25 | Pass 1 continuation, same guide — the two `brand-presence` entries added since the 2026-09-10 run (Asphalt Legends Unite, Minion Rush) | 2 — Asphalt Legends Unite, Minion Rush | Both entries' `operator:` lead (Gameloft) held up under re-sourcing: the Apple App Store's Seller field names Gameloft directly on each app's own listing, independent of Gameloft's own site or press material. Livewire, a `vendor-census` candidate surfaced the same day by the Gameloft verification pass (credited by its own case study with building a separate Samsung activation inside Asphalt Legends Unite), was not filed as a `built_for` edge — the only source for that claim is Livewire's own case study, which doesn't clear this record type's stricter bar; left unfiled per step 5 rather than filed on a thin source. |

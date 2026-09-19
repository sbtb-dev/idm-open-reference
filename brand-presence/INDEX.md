# Brand Presence — Index

Environments demonstrated to have carried third-party brand presence at least once.

An entry claims only that. It establishes nothing about current openness, terms,
scale, repeatability, or outcome, and absence establishes nothing at all — this
list is not, and will never be, complete. Ordering is alphabetical and carries no
meaning. See `README.md` for scope and exclusions.

## Entries

| Environment | Operator | First observed | Entry |
|---|---|---|---|
| Animal Crossing: New Horizons | Nintendo | 2026 | [`entries/animal-crossing-new-horizons.md`](entries/animal-crossing-new-horizons.md) |
| ARC Raiders | Embark Studios | 2026 | [`entries/arc-raiders.md`](entries/arc-raiders.md) |
| BGMI | KRAFTON India | 2026 | [`entries/bgmi.md`](entries/bgmi.md) |
| Brawl Stars | Supercell | 2026 | [`entries/brawl-stars.md`](entries/brawl-stars.md) |
| Driving Empire | Voldex | 2025 | [`entries/driving-empire.md`](entries/driving-empire.md) |
| EA SPORTS FC 26 | Electronic Arts | 2026 | [`entries/ea-sports-fc-26.md`](entries/ea-sports-fc-26.md) |
| Free Fire | Garena Online (Thailand) Co., Ltd. | 2025 | [`entries/free-fire.md`](entries/free-fire.md) |
| Genshin Impact | HoYoverse | 2026 | [`entries/genshin-impact.md`](entries/genshin-impact.md) |
| GOALS | GOALS AB | 2026 | [`entries/goals.md`](entries/goals.md) |
| GTA Online | Rockstar Games | 2021 | [`entries/gta-online.md`](entries/gta-online.md) |
| League of Legends: Wild Rift | Riot Games | 2026 | [`entries/league-of-legends-wild-rift.md`](entries/league-of-legends-wild-rift.md) |
| Mobile Legends: Bang Bang | MOONTON Games | 2026 | [`entries/mobile-legends-bang-bang.md`](entries/mobile-legends-bang-bang.md) |
| NBA 2K27 | 2K (Visual Concepts / Take-Two Interactive) | 2026 | [`entries/nba-2k27.md`](entries/nba-2k27.md) |
| Overwatch 2 | Blizzard Entertainment | 2024 | [`entries/overwatch-2.md`](entries/overwatch-2.md) |
| PGA TOUR 2K25 | 2K Games | 2026 | [`entries/pga-tour-2k25.md`](entries/pga-tour-2k25.md) |
| PUBG MOBILE | KRAFTON (Level Infinite / Tencent Games publishing) | 2026 | [`entries/pubg-mobile.md`](entries/pubg-mobile.md) |
| Riders Republic | Ubisoft | 2026 | [`entries/riders-republic.md`](entries/riders-republic.md) |
| Rocket League | Psyonix (Epic Games) | 2026 | [`entries/rocket-league.md`](entries/rocket-league.md) |
| skate. | Electronic Arts (Full Circle) | 2026 | [`entries/skate.md`](entries/skate.md) |
| Sprint League | Poki | 2026 | [`entries/sprint-league.md`](entries/sprint-league.md) |
| The Sims 4 | Electronic Arts (Maxis) | 2026 | [`entries/the-sims-4.md`](entries/the-sims-4.md) |
| Toca Boca World | Toca Boca (Spin Master) | 2026 | [`entries/toca-boca-world.md`](entries/toca-boca-world.md) |
| Watermelon Drop | Poki | 2026 | [`entries/watermelon-drop.md`](entries/watermelon-drop.md) |

## Now covered by an access regime record

Environments removed from this list because a published access regime was
recorded for them. The regime record is the more informative artifact.

_None yet._

## Sweeps run

Logged so that gaps read as gaps rather than as judgments. Entries above dated
before the first logged sweep were seeded from ad-hoc observation, not a
tracked sweep — no sweep-log row exists for them.

| Date | Scope of sweep | Entries added | Notes |
|---|---|---|---|
| 2026-08-29 | Live-fire validation pass, targeting the `operator press-release feed: {environment}` query family, per `idm-sweep`'s `docs/SEARCH_PROMPT.md`, gated on `TRIAGE_RUBRIC.md` rev `2026-08-24-v1` | 1 — Brawl Stars | All three structural tests (in vs. about, sanctioned vs. unsolicited, third-party vs. operator) settled from a single joint Supercell/adidas press release. |
| 2026-08-30 | Live-fire pass, targeting `{environment} brand activation announcement`, deliberately aimed at a non-UGC-platform category to test recall breadth beyond Roblox/Fortnite | 0 — Forza Horizon 6 proposed, then excluded on manual review | The cited Forza.net post (2026-08-26) announces a 7-Eleven Evolving World and EventLab Content Pack, but the post itself states nothing is playable yet — content ships "alongside the October series update," with specifics not yet disclosed. `README.md`'s claim is that an environment *has carried* brand presence at least once; an announced, unshipped content pack is not existence proof of that yet. Hold for re-proposal once the content actually ships. |
| 2026-09-03 | Proposed batch of six from a single Havas Media Network press release ("Renault 5 infiltrates popular video games with Havas Play") | 0 — Garry's Mod, Palworld, Stardew Valley, Stray, Subnautica, The Sandbox proposed, then excluded on manual review | The press release's own language ("infiltrates," modders using brand-supplied 3D models to build "mods") describes commissioned mods delivered through each game's modding tools, with no evidence of sanction from any of the six operators (Facepunch, Pocketpair, ConcernedApe, BlueTwelve Studio, Unknown Worlds Entertainment, TSB Gaming Ltd) — no operator quote, no co-announcement, no stated cooperation. `README.md`'s scope requires presence "sanctioned by the operator"; a brand commissioning mods through third-party modders is the mirror image of the KFC/Roblox unsanctioned-fan-content pattern `TRIAGE_RUBRIC.md` already excludes, just brand-initiated rather than fan-initiated. One proposed entry (Stardew Valley) cited a Nexus Mods fan-mod page as a second source, which is itself evidence of unofficial distribution rather than an operator-sanctioned channel. Hold for re-proposal only if operator-side sanction for a specific game can be independently confirmed. |
| 2026-09-18 | Targeted pass against two named candidates (not a query-family sweep): CeraVe Pharmacy × Poki's Sprint League, and Littlest Pet Shop × Poki's Watermelon Drop, both surfaced via Super League's "The Renaissance of Instant Play on the Web" white paper (2026-09-17), gated on `TRIAGE_RUBRIC.md` rev `2026-08-24-v1` | 2 — Sprint League, Watermelon Drop | Single third-party source for both (Super League's own case-study white paper; `first_party: false` on both entries — Super League is neither Poki nor the marketed brand). All three structural tests settled from the source's own plainly-stated language ("L'Oréal's CeraVe built a custom CeraVe Pharmacy inside Poki's Sprint League"; "In-game integration in Watermelon Drop... Littlest Pet Shop"). `ugc_platform` checked and left unset on both — neither environment is hosted on Fortnite/Minecraft/Roblox/Zepeto. Poki itself was evaluated as a possible `access-reference` regime and rejected: it hosts many separate, independently-built games (Sprint League by OnRush Studio, Watermelon Drop by yeqwep, per Poki's own developer credits) with no shared build/account/currency substrate, the same distribution-layer shape that sank the `curseforge` referral (see that repo's 2026-09-06 decision) — not filed. The builder/broker behind both integrations, Super League, was independently confirmed (Digiday, 2025-05-01) and is already on record as `super-league-enterprise` in `vendor-census/`. |

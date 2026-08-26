# ZEPETO Studio — Item & World Creation

- **`regime_id`:** REGIME/zepeto-studio
- **`last_reviewed`:** 2026-08-26
- **`next_review`:** 2026-11-24

## Scope of this record

This record covers ZEPETO's standing creator regime: a party other than Naver Z (ZEPETO's operator) enrolls a ZEPETO Studio account and builds avatar items or worlds distributed inside the ZEPETO app. Enrollment runs through a "ZEPETO ID" account login followed by "a simple profile form" requiring an email and phone number; no separate application or approval gate is documented for baseline access, and the same account is used for item creation, Build It world creation, and World SDK development. [1]

Governing terms: creators submitting content must comply with "ZEPETO Terms of Service, ZEPETO Studio Terms of Service, ZEPETO Studio Content Guidelines, [and] Specific Item Guidelines" [2], and use of the World SDK's creative tools is separately governed by a World SDK license that layers on top of — rather than replaces — the Studio Terms of Use and ZEPETO's general Terms of Use. [3] This record could not retrieve the full text of either the Studio Terms of Use (`studio.zepeto.me/terms`, which renders client-side) or the general ZEPETO Terms of Use (`support.zepeto.me`, which returned HTTP 403 to automated retrieval throughout this research); both are named and their role is documented, but their content is stated here only where a specific developer-documentation page paraphrases a requirement. See Open Questions.

Role model: no source this record could retrieve documents a multi-user or team-permission model for a single Studio account, in either direction. Publishing itself is stated to be restricted to "accounts that own the world id" [4], consistent with a single-account model, and search-indexed content attributed to ZEPETO's own support center suggests account-sharing for joint world creation is discouraged — but that page, like the general Terms of Use, returned HTTP 403 to direct automated retrieval and is not treated as a confirmed source here. See Open Questions.

This record does **not** cover:

- **ZEPETO's brand/advertising track** (`brands.zepeto.me`'s solution offerings, interstitial/immersive ad placements, and the Global Partnership Program) — investigated separately and found to be a contact-initiated, negotiated sales process with no self-serve enrollment; see `COVERAGE.md`'s "Investigated and excluded" table.
- **Promotional or branded content submitted through ordinary Studio channels.** Content that names, depicts, or advertises a brand, product, or specific person is classified as "promotional" and requires advance contact with ZEPETO, disclosure of intent, and — where a licensed figure or work is used — an uploaded licensing contract before submission. There is no self-serve path for this category; it is a case-by-case gate layered on the base regime described below, not a separate regime. [5]
- **ZEPETO Live streaming.** Studio's "Insight" dashboard reports live-stream metrics (broadcasts, viewers, gift revenue) alongside item-sales metrics in the same menu [6], suggesting Live is reached through the same Studio account, but this record did not locate documentation of what, if anything, gates starting a live stream, so Live is not characterized as part of the build surface below.
- **The "ZEPETO Official Creator Program"** — a follower-gated (10,000+ on ZEPETO, or 1,000+ on named social platforms) application tier layered on top of base Studio access [7]. It reads as a benefits/visibility tier rather than a separate enrollment path, but this record does not detail its terms.

Sourcing note: this record was built primarily via automated retrieval, consistent with this repo's current terms-of-service posture (`CONTRIBUTING.md`). Pages that resisted automated retrieval (HTTP 403s, client-side rendering) are named in prose rather than cited as sources; see Open Questions.

## What a third party can render

**Items.** Creators build fashion/avatar items via a 2D template editor (downloading template files and editing textures) or by registering 3D asset files authored in Maya or Blender. [1] Submissions are reviewed against ZEPETO's Contents Guidelines, which prohibit sexual/nudity content, hate speech and excessive violence, unauthorized depictions of regulated goods (alcohol, tobacco, drugs, weapons — with some conditional allowance for weapons inside worlds specifically), IP/trademark/likeness violations, undisclosed AI-generated content, and low-quality or misleading submissions such as embedded QR codes or URLs. [8]

**Worlds.** Worlds are built either with "Build It," a free PC/Mac map editor (Windows 10 or macOS Mojave minimum; Intel i5, 8GB RAM, GeForce GTX 660, 500MB storage) using pre-built templates, terrain, sky, and object placement [9], or with the ZEPETO World SDK, a Unity-integrated toolkit (ZeptoScript scripting, multiplayer support, ZEPETO-avatar and social-feature integration) aimed at more capable development; the World SDK is documented as free to use. [10] The SDK's API surface is separately documented in a preview-status API reference organized into Multiplay (Server), Product, Module, and Character Controller packages, which states it "does not cover all packages within the ZEPETO World SDK" and that "some content may not be up-to-date." [11] Publishing a world requires configuring Unity build/quality/player settings, generating a `.zepetopackage` file, and submitting it through a "World Console" tied to the account that owns the world ID. [4][12]

**Review.** All submissions — items and worlds — pass through a ZEPETO Studio review team before being serviced to users. Standard evaluation is documented as taking "up to 2 business weeks excluding weekends and holidays," with expedited review available to premium-membership subscribers. [2]

## What behavior the regime lets a third party instrument

**Third-party-defined instrumentation.** The ZEPETO Analytics package lets a world creator capture custom events via a `LogEvent` function (single string/number/boolean parameters or a generic payload), delivered through a required Google Analytics 4 integration: the creator creates their own Google Analytics account and a "web"-platform data stream (using the world ID as the stream's URL), then supplies the resulting Measurement ID and a Measurement Protocol API key back into the ZEPETO Analytics component. [13] Once active, the component also auto-accumulates cumulative session/residence time. Real-time custom events surface in Google Analytics' own "Realtime overview" report; non-realtime reports take unspecified additional processing time, and debug mode blocks data transmission entirely. [13] Because this pathway routes through a creator's own Google Analytics property, the resulting data is read from Google's dashboard, not a ZEPETO-hosted one — relevant to the read/export section below.

Separately, a Multiplay World DataStorage API lets a world store and retrieve player-scoped key/value data (keys ≤50 characters, alphanumeric/underscore only, ≤1,000 keys per user; values ≤500,000 characters per user; 200 Get and 200 Set calls per minute), alongside inventory, currency-balance, and ZEM sales/transaction records, with logs searchable up to 90 days. [14] This is player-facing game-state storage a creator's own code reads and writes, not a delivered analytics feed — the only other third-party-defined data-capture surface this record found documented.

**Operator-defined metrics.** World Console's Statistics menu reports Recent Visitors (7-day count, including repeat visits), Total Visitors (cumulative since launch, including repeat visits), and Unique Visitors (deduplicated); a separate "World Statistics Guide" is referenced as covering more detail but was not itself retrieved. [12][15] Studio's separate "Insight" dashboard reports, for items: units sold, ZEM revenue, a "best item" ranking, weekly sales/revenue rankings, likes, purchase-route, and buyer-nationality breakdowns, with daily-aggregated trend graphs over a selectable 1–31 day window and period-over-period trend labels ("surge," "spike," "new," "falling"); and for live streams: broadcast count, viewer counts, airtime, gift revenue, gift/watch-time rankings, peak concurrent viewers, and follower gains, aggregated daily except for weekly-aggregated follower data. [6]

**Breakdowns/segmentation.** Documented segmentation is limited to what's listed above (time window; purchase route and buyer nationality for items). No source retrieved documents demographic, platform/device, or acquisition-source segmentation for world-visitor statistics.

## What a third party can read and export, and who can read it

World Console is the primary read surface for world-registration status and visitor statistics. [12][15] Studio's Insight dashboard is the primary read surface for item-sales and live-stream performance. [6] Custom ZEPETO Analytics events are read from the creator's own Google Analytics 4 property, not from a ZEPETO-hosted dashboard [13] — access to that specific data stream is governed by whatever Google Analytics account-sharing the creator sets up themselves, entirely outside ZEPETO's own documentation.

**Binding constraint:** no source this record could retrieve documents a role or team-permission model for a ZEPETO Studio account — no named roles, no scoped (e.g., analytics-only or finance-only) access, and no documented mechanism to grant a collaborator visibility into World Console or Insight short of full account access. World earnings above a 5,000-ZEM balance can be exchanged (5,000 ZEM for $106 as documented at retrieval) [16], but no source retrieved states whether payout requires any particular account configuration.

No source retrieved documents a CSV/bulk-export function, a reporting API, or any programmatic read-back path for World Console or Insight data; both read, in what this record could access, as dashboard-only surfaces.

## Open questions

- Whether ZEPETO Studio, or the ZEPETO general Terms of Use, documents a minimum age or eligibility floor specific to creating in Studio (as opposed to the platform-general age figures reported by third-party parent-advice sites, which are not used as fact here). The Terms of Use page (`support.zepeto.me/hc/en-us/articles/360047786633-Terms-of-Use`) returned HTTP 403 to automated retrieval throughout this research.
- Whether a ZEPETO Studio account supports any form of multi-user or team access. Search-indexed content attributed to a ZEPETO support article titled "[Build it] Can I make a World with someone else?" suggests account-sharing for joint world creation is discouraged due to personal-information-leakage risk, and a separate article, "I want to change my personal account to a business account," suggests a business-account conversion changes tax/payout handling — but both pages returned HTTP 403 to direct automated retrieval throughout this research, so neither is treated as a confirmed source here; this record names them without asserting their content.
- The full text of the Studio Terms of Use (`studio.zepeto.me/terms`) — the page renders client-side and returned only navigation chrome to automated retrieval.
- Whether item-sale and world-earning ZEM balances share a single payout mechanism or are handled separately. A World SDK page states a 5,000-ZEM minimum balance and a 5,000-ZEM-to-$106 exchange rate for world earnings specifically [16]; a separate "Payment Request" page exists under the item-focused Studio Guide, but its content could not be retrieved (metadata only, no body text).
- What payment method(s), tax documentation, and account-type requirements govern payout — not confirmed from any directly retrieved source.
- Whether ZEPETO Live streaming is part of this regime (reached via the same Studio account, per Insight's inclusion of live-stream analytics) or a separately gated feature of the main ZEPETO app — no source documenting eligibility to go live was retrieved.
- The exact cardinality or size limits, if any, on ZEPETO Analytics custom events and payload fields — not stated in the retrieved documentation.
- Whether any programmatic export or reporting API exists for World Console or Insight data, distinct from the dashboard views documented here.
- ZEPETO's own World SDK "Getting Started" documentation states in-world advertising revenue support is "coming soon" as of this record's retrieval date [10] — not yet available, and not part of this regime as documented today.

## Sources

1. ZEPETO Studio Guide (welcome/overview), `docs.zepeto.me/studio-guide`, retrieved 2026-08-26 via automated tool — official developer documentation.
2. "Submitting for Evaluation," Studio Guide, `docs.zepeto.me/studio-guide/q6OY-submitting-for-evaluation`, retrieved 2026-08-26 via automated tool — official developer documentation.
3. "ZEPETO World SDK License and terms," World SDK Guide, `docs.zepeto.me/world-sdk-guide/zepeto-world-sdk-license-and-terms`, retrieved 2026-08-26 via automated tool — official program terms.
4. "Releasing your World," World SDK Guide, `docs.zepeto.me/world-sdk-guide/releasing-your-world`, retrieved 2026-08-26 via automated tool — official developer documentation.
5. "promote a brand or product," Studio Guide, `docs.zepeto.me/studio-guide/promote-a-brand-or-product`, retrieved 2026-08-26 via automated tool — official developer documentation.
6. "Insight," Studio Guide, `docs.zepeto.me/studio-guide/insight`, retrieved 2026-08-26 via automated tool — official developer documentation.
7. "ZEPETO Official Creator Program," `studio.zepeto.me/program/creator`, retrieved 2026-08-26 via automated tool — official program page.
8. "Contents Guidelines," Studio Guide, `docs.zepeto.me/studio-guide/contents-guidelines`, retrieved 2026-08-26 via automated tool — official developer documentation.
9. "Installing 'Build it'," Studio Guide, `docs.zepeto.me/studio-guide/installing-build-it`, retrieved 2026-08-26 via automated tool — official developer documentation.
10. "Getting Started," World SDK Guide, `docs.zepeto.me/world-sdk-guide/`, retrieved 2026-08-26 via automated tool — official developer documentation.
11. "Home," World SDK API Reference, `developer.zepeto.me/docs/intro/`, retrieved 2026-08-26 via automated tool — official API reference documentation.
12. "Making a World Console," World SDK Guide, `docs.zepeto.me/world-sdk-guide/making-a-world-console`, retrieved 2026-08-26 via automated tool — official developer documentation.
13. "ZEPETO Analytics," World SDK Guide, `docs.zepeto.me/world-sdk-guide/zepeto-analytics`, retrieved 2026-08-26 via automated tool — official developer documentation.
14. "World Data Management," World SDK Guide, `docs.zepeto.me/world-sdk-guide/world-data-management`, retrieved 2026-08-26 via automated tool — official developer documentation.
15. "How to check the statistics data of the world," World SDK Guide, `docs.zepeto.me/world-sdk-guide/how-to-check-the-statistics-data-of-the-world`, retrieved 2026-08-26 via automated tool — official developer documentation.
16. "How do I withdraw money?," World SDK Guide, `docs.zepeto.me/world-sdk-guide/how-do-i-withdraw-money`, retrieved 2026-08-26 via automated tool — official developer documentation.

## Standing note

Published documentation is a party describing its own product.

## Closing disclaimer

This record describes what this access regime documents as available. It does not establish that any activation running under it produces anything in particular. Capacity is not inventory.

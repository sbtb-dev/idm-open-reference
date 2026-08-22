# Roblox Creator Program — Studio-Built Experiences

- **`regime_id`:** REGIME/roblox-creator-experiences
- **`last_reviewed`:** 2026-08-21
- **`next_review`:** 2026-11-19

## Scope of this record

Enrollment runs through a standard Roblox account signed into Roblox Studio, a free desktop application; no separate application or approval gate exists to start building. By using Roblox Studio to build and publish an "experience," a creator becomes subject to the Roblox Terms of Use plus the Creator Terms, which the Terms of Use incorporate by reference and which specifically govern use of Roblox Studio, offering experiences and virtual items, and related creator conduct. [1] A second, narrower terms document — the Developer Exchange (DevEx) Terms of Use — governs a separate, opt-in step (cashing out Earned Robux for real currency) with its own eligibility gate (age 13+, a minimum Earned Robux balance, tax forms, account standing). [2]

The role model has two distinct shapes depending on ownership. For an individually-owned experience, access runs through four flat permission levels — Owner, Edit, Play, No Access — and, critically, Edit access (which is required to see the experience's Creator Dashboard analytics) can only be granted to Roblox friends. For a Group/Community-owned experience, a configurable role-and-permission system lets the owner grant analytics access and revenue/finance access as separate, independently assignable permissions, decoupled from edit or publish rights. This role split is the load-bearing fact of this regime (see "read and export" below).

This record does **not** cover Roblox's advertising products: the Ads Manager / Immersive Ads / Sponsored Experiences program, governed by the separate Roblox Advertising Terms (an agreement between Roblox Advertising Services LLC and *advertisers*, a party role distinct from — though sometimes overlapping with — a Creator); or the Advertising Integrations Terms, which govern a developer placing third-party ad content directly inside their own experience outside Roblox's native ad services, and which carry their own eligibility gate (13+, ID/2FA verification, public-experience status) and revenue-share terms layered on top of, but separate from, base Creator Terms enrollment. Both are separate regimes with separate enrollment/terms from the one described here; note only, not covered.

## What a third party can render

Roblox Studio is free and available for Windows 10+ / macOS 10.14+ (recommended Windows 11 / macOS 14+, 3 GB RAM minimum, 8 GB recommended); it requires signing in with a Roblox account, but the documentation does not state a minimum age to use Studio itself. [4] Using Studio, a creator builds an "experience" (game) on the Roblox engine and publishes it to the platform, where it is discovered through Roblox's own surfaces (home, discover, search, etc. — not detailed further here since discovery mechanics fall outside this record's sourcing).

Publishing is gated by a tiered, escalating verification and evaluation system, effective from a May 2026 policy change: [16][17][18]

- **Personal Use** — any account in good standing can publish privately; no additional verification.
- **Trusted Friends and 16+** — requires an age check (ID verification or facial age estimation) and an account in good standing; reaches age-checked users 16+ and designated trusted connections.
- **All Ages (including Kids/Select audiences)** — requires everything in the 16+ tier plus ID verification (with a parental account link for under-13 creators), two-factor authentication, and either a one-time 1,000 Robux fee, a 100,000 Robux expedited-review fee, or an active Roblox Plus/Premium subscription held for two consecutive months. New experiences targeting younger audiences must also pass an evaluation process: the game is first released only to age-checked 16+ users and must accumulate roughly 250–500 unique plays from highly engaged, verified players within a 60-day window (figures differ slightly between sources describing the same mechanism) before Roblox expands its reach to younger age tiers. [16][18]

All published experiences must complete a content-maturity and compliance questionnaire; only experiences rated Minimal or Mild maturity are playable by Roblox Kids accounts (ages 5–8), and Moderate or below by Roblox Select accounts (ages 9–15). [16][18] Separately, all uploaded content (images, meshes, audio, video) and every experience publish/update passes through a multi-step review combining automated tooling (filter-bypass and policy-violation detection, CSAM/duplicate-content scanning, copyright checks on audio) and a continuously operating human review team, with an appeals path for moderation decisions. [15]

Collaboration inside Studio (Team Create) is itself age-gated: giving Edit access to another creator outside your own age group requires an age check (facial estimation or ID verification) on both sides, and cross-age-group collaboration additionally requires either parental permission (for a under-16 collaborator) or an established "Trusted Friend" connection; solo work and single-person sessions are exempt, and an experience owner is never blocked from their own experience. [12]

Roblox Groups — now generally labeled "Communities" in current help-center documentation, while the Creator Hub reference documentation still uses "Groups" — let multiple creators collaborate under shared ownership: a group/community can own an experience directly, multiple members can be granted rights to edit, publish, and monetize it without any ownership transfer, and revenue earned by the experience is applied to the group rather than to whichever individual member created it. [8][20]

## What behavior the regime lets a third party instrument

**Third-party-defined instrumentation (AnalyticsService, in-engine).** A developer logs custom analytics events from server-side Luau code via the `AnalyticsService` API, available only from the server and only in published games (not from the client or in Studio): [5][14]

- `LogCustomEvent(player, eventName, value, customFields)` — counter or value-bearing custom events; up to 100 distinct custom event names per game, with custom fields recommended for segmentation because event names carry a tighter cardinality limit than fields (exact numeric limit not published). [5]
- `LogEconomyEvent(...)` — logs in-experience currency/economy transactions (flow type, currency, amount, ending balance, item SKU).
- `LogFunnelStepEvent` / `LogOnboardingFunnelStepEvent` — logs steps of a multi-step funnel (e.g., checkout, first-time-user onboarding), grouped by funnel name and session ID.
- `LogProgressionEvent` and its `Start`/`Fail`/`Complete` variants — logs player progression through levels/achievements.
- `GetPlayerSegmentsAsync(player)` — the one read-back method in the API: returns operator-computed player segment data (e.g., `WhenUserFirstPlayed`, `ActivePayerStatus`) at runtime, for in-experience personalization. [14]

Logged events are aggregated daily; new custom-event data can take up to 24 hours to appear on the dashboard. [5]

**Operator-provided metrics (Creator Dashboard / Analytics Dashboard).** Full KPI access requires the experience to have exceeded 10 daily active users (DAU) and 10 play-hours for 7 consecutive days, plus a verified email and two-step verification on the creator's account. [6] Documented KPI groups: retention (return-visit rate after first visit), engagement (average session time, new-user first-session retention), acquisition (traffic source, share-link visits), demographics (age, gender, country, language of MAU), monetization (revenue, ARPPU, ARPDAU, conversion rate, avatar-item sales), and player feedback/ratings. [6][7][13] A separate Insights layer surfaces revenue/DAU deltas against benchmark pools (Top 200/500/1000 experiences by rolling 30-day playtime), top drivers of revenue or DAU movement, outlier detection across demographic segments, and player-feedback summaries; general insights require 100+ DAU, AI-generated reports require 1000+ DAU, and feedback reports require 20+ comments. [7]

**Available breakdowns/segmentation.** Documented dashboard filters include: demographics (age band, gender, country, language); platform and device (computer, phone, tablet, console, VR) and operating system; user-acquisition source; spender-status cohort (top 15%, intermediate 35%, casual 50%, lapsed, never); first-play cohort (0–30 days through 365+ days since first play); and device memory tier. [6]

## What a third party can read and export, and who can read it

The Creator Dashboard is the primary read surface. Individual charts can be exported to CSV via an on-page Export button; separately, sales/transaction data is available as an automated CSV download refreshed every 48 hours, reachable from the transaction pages of both personally-owned and group-owned accounts. [6] The canonical Open Cloud API reference (`create.roblox.com/docs/cloud`) does not list an Analytics endpoint among its documented services as of the retrieval date — Open Cloud's officially documented surface covers game/server management, data stores, user restrictions, and inventory, not analytics read-back. [21] (A community-reported, undocumented beta "Open Cloud Analytics Query API" surfaced in an unofficial devforum post is noted in Open Questions below, not treated as fact — it was found by a third party, not announced or confirmed by Roblox, and its rollout scope is explicitly uncertain even in that post.)

**The binding constraint — who on a team actually gets access:**

- **Individually-owned experiences.** Access runs through four flat levels: Owner, Edit, Play, No Access. Edit access — the level required to reach the Creator Dashboard, and with it analytics — can only be granted to Roblox friends of the owner; Play-only access (which can be granted to any user or group) does not carry dashboard/analytics visibility. There is no documented mechanism to grant analytics access on a personal experience without also granting edit rights. [19]
- **Group/Community-owned experiences.** A configurable, per-role permission system lets the group owner grant "access analytics across all group experiences" as a permission independent of edit/publish rights, and separately, revenue/finance visibility (viewing the group's Robux balance and configuring payout splits) is gated by its own permission (documented under "Spend Community Funds," which also opens the Revenue section of the Community Admin Page). [8][9][10][25] This means a group owner can hand a member analytics visibility without finance visibility, finance visibility without analytics, both, or neither — an explicit, costless-to-configure decision the owner makes per role. The default "Base Member" role that every new member receives on joining carries neither by default; every other role and its permissions are created and assigned explicitly by the owner or a member with role-management rights. [9]

**DevEx cash-out.** Turning Earned Robux into real currency is a separate, gated step layered on top of the base regime: the creator must be 13+, hold at least 30,000 Earned Robux, have a verified email and an active DevEx Portal account, and have filed the applicable IRS tax form (W-9 for U.S. taxpayers, W-8 otherwise); one cash-out request is allowed per calendar month, each request is reviewed individually with no guarantee of approval regardless of prior approvals, and an account inactive for two and a half years or more becomes ineligible. [2][3][11]

## Open questions

- Whether an Open Cloud Analytics Query API is officially available, to whom, and on what documented terms. A community devforum post (not an official Roblox announcement, and not included in the Sources list below) reported testing a beta endpoint covering retention, engagement, monetization, acquisition, performance, stability, economy events, custom events, and advertising data, authenticated via an API key scoped to `universe-analytics` / `universe.analytics:read` — but the post's author states they could not find a corresponding public Roblox announcement and had not confirmed the beta's rollout scope. This is recorded here as unknown, not as an available capability, and is unverified third-party testimony rather than documentation.
- The exact cardinality limit on `AnalyticsService` custom fields (documentation states the limit is "much tighter" for event names than for custom fields but does not publish a number). [5]
- Whether any programmatic/automated export path exists for Creator Dashboard analytics beyond the manual per-chart CSV export and the 48-hour sales CSV.
- The precise minimum age to create a Roblox account at all. Documentation addresses COPPA compliance and enhanced protections/restrictions for users under 13, and requires parental consent for any minor, but does not publish a numeric floor for account creation itself. [24]
- Whether "Group" and "Community" are fully synonymous and interchangeable across all current official documentation, or represent a terminology migration still in progress — the Creator Hub reference documentation (`create.roblox.com/docs/projects/groups`) still uses "Group," while current help-center articles use "Community" throughout.
- Whether granular per-role, per-experience analytics permissions for group/community-owned experiences (e.g., a "View group experience analytics" toggle referenced in developer-forum discussion) are stable, generally available, and reliable — this record found forum discussion (unverified, community-sourced, not used as a factual source above) suggesting inconsistent behavior at some point, but no official documentation confirming or denying current behavior was located.
- Whether an experience owner without a group can ever delegate analytics-only access to a non-friend collaborator through any documented mechanism; none was found.

## Sources

1. Roblox Terms of Use, Roblox Support (via Zendesk Help Center API, article 115004647846), retrieved 2026-08-21 — official program/legal terms.
2. Developer Exchange Terms of Use, Roblox Support (via Zendesk Help Center API, article 115005718246), retrieved 2026-08-21 — official program terms.
3. Developer Exchange Program, Roblox Creator Hub documentation (`create.roblox.com/docs/production/monetization/developer-exchange`), retrieved 2026-08-21 — official developer documentation.
4. Roblox Studio setup, Roblox Creator Hub documentation (`create.roblox.com/docs/studio/setup`), retrieved 2026-08-21 — official developer documentation.
5. Custom events, Roblox Creator Hub documentation (`create.roblox.com/docs/production/analytics/custom-events`), retrieved 2026-08-21 — official developer documentation.
6. Analytics dashboard, Roblox Creator Hub documentation (`create.roblox.com/docs/production/analytics/analytics-dashboard`), retrieved 2026-08-21 — official developer documentation.
7. Insights, Roblox Creator Hub documentation (`create.roblox.com/docs/production/analytics/insights`), retrieved 2026-08-21 — official developer documentation.
8. Groups (teams), Roblox Creator Hub documentation (`create.roblox.com/docs/projects/groups`), retrieved 2026-08-21 — official developer documentation.
9. Community Roles/Ranks and Permissions, Roblox Support (via Zendesk Help Center API, article 203313770), retrieved 2026-08-21 — official help center.
10. Community Clothing, Revenue Management, and Payouts, Roblox Support (via Zendesk Help Center API, article 203313830), retrieved 2026-08-21 — official help center.
11. DevEx Eligibility & General Questions, Roblox Support (via Zendesk Help Center API, article 27954482561300), retrieved 2026-08-21 — official help center.
12. Age Guidelines for Collaborating in Roblox Studio, Roblox Support (via Zendesk Help Center API, article 45500519296532), retrieved 2026-08-21 — official help center.
13. Engagement, Roblox Creator Hub documentation (`create.roblox.com/docs/production/analytics/engagement`), retrieved 2026-08-21 — official developer documentation.
14. AnalyticsService, Roblox Creator Hub API reference (`create.roblox.com/docs/reference/engine/classes/AnalyticsService`), retrieved 2026-08-21 — official API reference documentation.
15. Content Moderation on Roblox, Roblox Support (via Zendesk Help Center API, article 21416271342868), retrieved 2026-08-21 — official help center.
16. How to Publish Games on Roblox, Roblox Support (via Zendesk Help Center API, article 203313890), retrieved 2026-08-21 — official help center.
17. New Publishing Requirements & Evaluation Process for Games, official Roblox staff announcement, Roblox Developer Forum (`devforum.roblox.com/t/new-publishing-requirements-evaluation-process-for-games/4573166`), retrieved 2026-08-21 — official program announcement.
18. Roblox Kids and Select, Roblox Creator Hub documentation (`create.roblox.com/docs/production/publishing/kids-and-select`), retrieved 2026-08-21 — official developer documentation.
19. Collaboration, Roblox Creator Hub documentation (`create.roblox.com/docs/projects/collaboration`), retrieved 2026-08-21 — official developer documentation.
20. Group Experiences, Roblox Support (via Zendesk Help Center API, article 203313760), retrieved 2026-08-21 — official help center.
21. Cloud API reference, Roblox Creator Hub documentation (`create.roblox.com/docs/cloud`), retrieved 2026-08-21 — official API reference documentation.
22. Roblox Advertising Terms, Roblox Support (via Zendesk Help Center API, article 15494846263060), retrieved 2026-08-21 — official program terms (cited only to establish the boundary excluded from this record's scope).
23. Advertising Integrations Terms, Roblox Support (via Zendesk Help Center API, article 47656162239124), retrieved 2026-08-21 — official program terms (cited only to establish the boundary excluded from this record's scope).
24. Roblox Privacy and Cookie Policy, Roblox Support (via Zendesk Help Center API, article 115004630823), retrieved 2026-08-21 — official policy document (age/COPPA context only).
25. How to Manage a Community, Roblox Support (via Zendesk Help Center API, article 203313810), retrieved 2026-08-21 — official help center.

## Standing note

Published documentation is a party describing its own product.

## Closing disclaimer

This record describes what this access regime documents as available. It does not establish that any activation running under it produces anything in particular. Capacity is not inventory.

# Fortnite Island Creator (Fortnite Creative & UEFN)

- **`regime_id`:** REGIME/fortnite-island-creator
- **`last_reviewed`:** 2026-08-21
- **`next_review`:** 2026-11-19

## Scope of this record

This record covers the standing arrangement under which a non-operator party builds and publishes island content for Fortnite and instruments/reads data about it. The enrollment path is Epic's Fortnite Developer Program, joined through the Fortnite Creator Portal (`create.fortnite.com`) [1][2]. Epic's own documentation shows this program's name in transition: a legacy page still resolves at the URL slug `island-creator-program` and is marked for deprecation in favor of documentation now titled "Fortnite Developer Program" [21], while the Content Guidelines still point developers to "Fortnite Island Creative Rules" as a named resource [20]. This record treats "Island Creator Program," "Island Creator & Engagement Program," and "Fortnite Developer Program" as successive names for the same enrollment path, portal, and terms, not as separate regimes, since the individuation rule turns on enrollment/terms/roles rather than branding.

Fortnite Creative and Unreal Editor for Fortnite (UEFN) are treated as **one regime** here because both are built and published through the same enrollment (Fortnite Developer Program), the same Creator Portal, the same governing terms (Fortnite Developer Terms, Fortnite Developer Rules), and the same team-role model (Owner / Administrator / Publisher / Collaborator) [1][4][5][9][10][11]. Publishing from either tool routes through the same Creator Portal publish flow [16], and UEFN is itself defined by its supplemental terms as a tool for creating "Developer-Made Content" inside Fortnite, alongside Fortnite Creative [6].

Governing terms accepted at enrollment: **Fortnite Developer Terms** [4], **Fortnite Developer Rules** (referred to during enrollment as "Community Rules") [5][1], and an **Addendum to Fortnite Developer Terms** that enrollment requires accepting by name [1] (its full text was not independently confirmed via official fetch — see Open Questions). UEFN use additionally requires the **Unreal Editor for Fortnite Supplemental Terms** [6], layered on the general **Epic Games Terms of Service / Fortnite EULA** [7]. Content is separately bound by the **Epic Games Content Guidelines** [20].

**Explicitly out of scope:** the **Support-A-Creator program** is a separate regime, not covered here. Its own terms describe it as "an affiliate marketing program for creators that publish Content on third-party media platforms," compensated through referral Creator Codes and attribution links on purchases — it has no build surface inside Fortnite and is governed by separate Support-A-Creator Program Terms [8]. It fails element (1) of this repo's regime definition (build/place/publish inside the environment) and is therefore a different regime under the individuation rule, not a variant of this one.

Sponsored Row / Discover paid-promotion campaigns are **not** treated as a separate regime — they are a feature reached through the same Creator Portal, under the same enrollment and roles, for boosting visibility of content already built under this regime [19].

## What a third party can render

UEFN is a PC application for building and publishing island content directly into Fortnite, using Verse as its scripting language; unlike standard Unreal Engine, UEFN does not include Blueprint visual scripting [15]. A developer can place "Props and devices" from the Creative toolset and Epic/Fortnite-specific content library, and write "Custom gameplay logic" in Verse via UEFN's integrated code editor [15]. Fortnite Creative provides the equivalent island-building toolset, including devices such as Tracker Devices for gameplay logic [14]. The Fortnite Developer Terms define the resulting "Content" as: assets, Islands, items, and other materials created using UEFN tools; Islands created using Fortnite Creative tools; and related off-platform materials [4].

Publishing is initiated from either tool — "Publish Island" in Island Settings (Fortnite Creative) or "Publish Project" (UEFN) — and completed through the Creator Portal: filling out public metadata under Game Details, completing an IARC content-rating questionnaire, uploading promotional media (thumbnails, trailers, lobby backgrounds), adding Attribution for any third-party assets used, choosing Listed or Unlisted visibility, and submitting for review [16]. Content moderation runs in two stages — a metadata/assets review (title, description, thumbnails, lobby background, promotional screenshots, trailers, assets) followed by an in-island gameplay review — and both stages must comply with the Fortnite Developer Rules and the Epic Games Content Guidelines [5][18][20]. Rules require obtaining IARC age ratings on publish, disclosing numerical odds for any paid random items prior to purchase, and disclosing sponsor/brand relationships for paid promotional content [5].

Published islands reach players through Discover: a personalized "For You" row driven by a given player's engagement history, genre rows whose ordering varies per player, an editorially curated "Epic's Picks" row for "high novelty, innovative islands," and search combining keyword matching with semantic search [17]. Epic states "Engagement drives distribution," with automated systems continuously scoring islands against "engagement, retention, social, and similarity signals," and new islands receiving up to a two-week testing window across Discover rows before broader placement decisions [17]. Creators can additionally pay for visibility by bidding for impressions in Discover's Sponsored Row via Creator Portal campaigns [19].

## What behavior the regime lets a third party instrument

**Third-party-defined event capture.** Tracker Devices let a creator "create and track custom objectives that a player can complete, and send a signal to another device when the player completes a tracked objective," across a documented list of built-in trackable behaviors — eliminations, being eliminated, chests/llamas opened, player revived, player interrogated, weapons fished, props destroyed, shield potions consumed, distance traveled (on foot/vehicle/air), races completed, rounds won, games completed [14]. The Analytics device separately registers when players trigger other devices it's attached to (stepping on a trigger, entering a volume, eliminating an enemy, pressing a button), and requires the creator to "give each analytic event a unique name so you can tell what the device is monitoring" [12]. For fully custom instrumentation, UEFN documentation directs developers to "Create a Verse script following the directions in Create Your Own Verse Device" to script custom analytics events in code rather than only placing preset devices; the Analytics device "records this data and sends it to the Creator Portal every day" [13].

**Operator-defined metrics.** Epic separately measures and surfaces: Discover-ranking signals including average playtime, retention rate, bounce rate, and a "Qualified Play-Through Rate (QPTR)" (an engagement-weighted play-through metric) [17]; and an engagement-payout formula tracking active playtime, island retention (day-over-day return), Item Shop purchase-window playtime, and new/returning player acquisition (with a documented 75%-of-spend reward for six months on newly- or re-acquired players) [3].

**Breakdowns/segmentation.** The Analytics Dashboard shows a "Total Activations Graph" aggregating data across all registered devices on an island alongside a per-device list, viewable over selectable date ranges [12]. The Sponsored Row campaign dashboard reports impressions delivered, click-through rate, and concurrent player counts (CCU), refreshed hourly for live campaigns and daily (prior-day UTC) for historical Market History Chart data [19]. Documentation does not describe demographic, geographic, or platform-level breakdowns for either the Analytics Dashboard or engagement-payout data (see Open Questions).

## What a third party can read and export, and who can read it

The regime's binding constraint is stated directly in its own governing terms: the Fortnite Developer Terms disclaim any inspection right over Epic's own systems — **"Neither these Terms nor any other agreement or legal principle provide any right for you or any third party to inspect or examine any of Epic's data, documents, records, software, or systems, related to or in any way connected with the Developer Program"** [4]. Everything documented below is what Epic chooses to surface through the Creator Portal, not an audit or inspection right.

**Role gating.** The Creator Portal's UEFN team documentation defines four roles with explicit, differentiated analytics and financial access:

- **Owner** — "Has access to everything in the project. Controls all team branding, branding profiles, and monetization... Able to view all project analytics. **Only owners can see monetization.**" [10]
- **Administrator** — can manage projects, versions, and metadata, and promote/demote admins; "Able to view all project analytics." No monetization access documented [10].
- **Publisher** — can publish and manage projects; "Able to view all project analytics." No monetization access documented [10].
- **Collaborator** — can view/version/edit project metadata but not publish; "Able to view **technical project analytics**" only — a narrower, undefined tier compared to the other three roles. No monetization access documented [10].

The parallel Fortnite Creative team-roles documentation names the same four roles with matching publish/edit/branding responsibilities, but its published table does not repeat this analytics tiering — it states only that the Owner "Controls all team branding, branding profiles, and monetization," without describing Administrator/Publisher/Collaborator analytics access [11]. Under the individuation rule this is still one regime (same portal, same role names, same terms), so this record treats the UEFN doc's explicit tiering as the documented model and flags the Creative doc's silence as an open question rather than a contradiction (see Open Questions). Consistent with Owner-only financial access, Sponsored Row campaign documentation separately notes "all campaign receipts are emailed to the island owner" [19].

**Export mechanisms documented:**
- Analytics Dashboard (Creator Portal → Analytics → Analytics Device tab, per island): Total Activations Graph, full registered-device list, selectable date range, and a "Download Button" to "download a copy of the data for your records and import the raw data into their spreadsheet app of choice" — the exact export file format is not stated [12].
- Engagement and payout data appear in a dedicated "Monetization Payout tab" of the Creator Portal once a developer is accepted into the program [3].
- The Creator Portal's legacy top-level "Analytics" navigation link is explicitly noted as deprecated, with current data directed instead to per-project analytics pages [9].
- Sponsored Row campaign performance is viewable live in a Campaigns dashboard in the Creator Portal, with receipts emailed separately to the island owner [19].
- No documented API or bulk/programmatic export path was found beyond the dashboard's manual download button (see Open Questions).

## Open questions

- Whether Administrator, Publisher, or Collaborator roles can see any engagement-payout / Monetization Payout tab data, or whether that tab is Owner-only in practice — the team-roles doc restricts "monetization" to Owner, but the Engagement Payout doc does not itself address roles [3][10].
- What "technical project analytics" (the Collaborator tier) actually includes or excludes relative to "all project analytics" (Owner/Admin/Publisher) — not defined in the fetched documentation [10].
- Whether the Fortnite Creative-specific team-roles page's silence on analytics tiering (as opposed to the UEFN team-roles page's explicit tiering) reflects an actual product difference between the two build surfaces, or is simply uneven documentation of the same underlying role system [10][11].
- Whether custom Verse-scripted analytics events (via "Create Your Own Verse Device") land in the same Analytics Dashboard as built-in Analytics Device events, or are surfaced through a separate path — not fully specified [13].
- The exact file format of the Analytics Dashboard's downloadable export (CSV, XLSX, or other) — not stated [12].
- Data retention period for Analytics Device / Tracker Device data — not stated in the fetched documentation.
- Whether any programmatic/API access to analytics or payout data exists beyond the manual dashboard download — not found in official documentation searched.
- Full current text and scope of the "Addendum to Fortnite Developer Terms" referenced by name during enrollment [1] — not independently confirmed via an official (`legal.epicgames.com`) fetch; only third-party document hosts surfaced its content, which this record does not cite as fact.
- Whether a maximum team-member count applies to Creator Portal teams — surfaced only in secondary/aggregated search results, not confirmed by direct fetch of primary documentation, so left unstated here.
- Current specific eligibility thresholds (e.g., the $20/365-day spend or purchase-history requirement) may be revised by Epic over time; this record reflects the thresholds documented as of the retrieval date [1].

## Sources

1. Epic Games, "Fortnite Developer Program," `dev.epicgames.com/documentation/fortnite/fortnite-developer-program`, retrieved 2026-08-21 — official developer documentation.
2. Epic Games, "Fortnite Developer Program FAQs," `dev.epicgames.com/documentation/fortnite/fortnite-developer-program-faqs-in-fortnite`, retrieved 2026-08-21 — official developer documentation.
3. Epic Games, "Engagement Payout in Fortnite Creative," `dev.epicgames.com/documentation/en-us/fortnite/engagement-payout-in-fortnite-creative`, retrieved 2026-08-21 — official developer documentation.
4. Epic Games, "Fortnite Developer Terms," `legal.epicgames.com/fortnite/developer-terms`, retrieved 2026-08-21 — official program terms.
5. Epic Games, "Fortnite Developer Rules," `legal.epicgames.com/fortnite/developer-rules`, retrieved 2026-08-21 — official program terms.
6. Epic Games, "Unreal Editor for Fortnite Supplemental Terms," `legal.epicgames.com/epicgames/uefn`, retrieved 2026-08-21 — official program terms.
7. Epic Games, "Epic Games Terms of Service" (Fortnite EULA), `legal.epicgames.com/fortnite/eula`, retrieved 2026-08-21 — official EULA.
8. Epic Games, "Support-A-Creator Program Terms," `legal.epicgames.com/fortnite/eula/sac`, retrieved 2026-08-21 — official program terms (cited to establish this program is out of scope).
9. Epic Games, "Creator Portal Overview in Fortnite Creative," `dev.epicgames.com/documentation/fortnite/creator-portal-overview-in-fortnite-creative`, retrieved 2026-08-21 — official developer documentation.
10. Epic Games, "Creating Teams in Creator Portal in Unreal Editor for Fortnite," `dev.epicgames.com/documentation/en-us/fortnite/creating-teams-in-creator-portal-in-unreal-editor-for-fortnite`, retrieved 2026-08-21 — official developer documentation.
11. Epic Games, "Setting Up Teams in Fortnite Creative," `dev.epicgames.com/documentation/fortnite/setting-up-teams-in-fortnite-creative`, retrieved 2026-08-21 — official developer documentation.
12. Epic Games, "Analytics Device Dashboard in Fortnite Creative," `dev.epicgames.com/documentation/en-us/fortnite/analytics-device-dashboard-in-fortnite-creative`, retrieved 2026-08-21 — official developer documentation.
13. Epic Games, "Using Analytics in Unreal Editor for Fortnite," `dev.epicgames.com/documentation/en-us/fortnite/using-analytics-in-unreal-editor-for-fortnite`, retrieved 2026-08-21 — official developer documentation.
14. Epic Games, "Using Tracker Devices in Fortnite Creative," `dev.epicgames.com/documentation/en-us/fortnite/using-tracker-devices-in-fortnite-creative`, retrieved 2026-08-21 — official developer documentation.
15. Epic Games, "UEFN vs UE in Unreal Editor for Fortnite," `dev.epicgames.com/documentation/fortnite/uefn-vs-ue-in-unreal-editor-for-fortnite`, retrieved 2026-08-21 — official developer documentation.
16. Epic Games, "Publishing Islands in Fortnite Creative," `dev.epicgames.com/documentation/fortnite/publishing-islands-in-fortnite-creative`, retrieved 2026-08-21 — official developer documentation.
17. Epic Games, "How Discover Works in Fortnite," `dev.epicgames.com/documentation/fortnite/how-discover-works-in-fortnite`, retrieved 2026-08-21 — official developer documentation.
18. Epic Games, "Island Moderation Tips and FAQs in Fortnite Creative," `dev.epicgames.com/documentation/en-us/fortnite/island-moderation-tips-and-faqs-in-fortnite-creative`, retrieved 2026-08-21 — official developer documentation.
19. Epic Games, "Campaign FAQs in Fortnite," `dev.epicgames.com/documentation/fortnite/campaign-faqs-in-fortnite`, retrieved 2026-08-21 — official developer documentation.
20. Epic Games, "Epic Games Content Guidelines," `legal.epicgames.com/epicgames/content-guidelines`, retrieved 2026-08-21 — official program terms.
21. Epic Games, "Island Creator Program" (legacy page), `dev.epicgames.com/documentation/en-us/fortnite/island-creator-program`, retrieved 2026-08-21 — official developer documentation (legacy/deprecated; cited only for program-naming lineage).

## Standing note

Published documentation is a party describing its own product.

## Closing disclaimer

This record describes what this access regime documents as available. It does not establish that any activation running under it produces anything in particular. Capacity is not inventory.

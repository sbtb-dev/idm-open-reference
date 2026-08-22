# Roblox Advertising (Ads Manager / Immersive Ads)

- **`regime_id`:** REGIME/roblox-ads
- **`last_reviewed`:** 2026-08-21
- **`next_review`:** 2026-11-19

## Scope of this record

This record covers Roblox's self-service advertising regime: a brand or advertiser (not the operator of any given Roblox experience, and not the creator/developer building that experience) enrolls a dedicated advertiser account through Ads Manager (ads.roblox.com) and buys ad placements that are rendered inside experiences built and operated by third-party creators, or on Roblox's own Home/Discover/Search surfaces.

Enrollment path: a personal or business "ads account," gated on a Roblox account with a verified email and a minimum age of 13, funded by credit/debit card (18+) or Robux converted to Ad Credits (13+) [1][4]. This is a distinct signup flow from Roblox Studio / the developer program that experience-builders use.

Governing terms: Roblox's own documentation names Roblox Advertising Standards, Roblox Community Standards, Roblox Terms of Use, and an Independent Advertising Policy as the compliance documents advertisers and their content must satisfy, with account/game suspension as the stated consequence of violation [10]. These are advertising-specific terms layered on top of (not identical to) the terms a Studio developer agrees to when building an experience.

Role model: every fetched source describes account access as tied to a single Roblox account (the "personal" vs. "business" distinction is a labeling choice at account creation, not a documented multi-seat structure), and the programmatic API explicitly supports only user-owned credentials, not group-owned ones [6]. No source describes named team members or scoped roles (e.g., billing-only vs. reporting-only) on a shared ads account.

This record does **not** cover:
- **Roblox Studio / the experience-building creator regime** — a separate enrollment path (developer/Studio account, not an ads account), separate terms, and a separate role model (Studio, Team Create, and group-based permissions). Covered by a separate record.
- **Managed, Insertion-Order-based campaigns** apparently run through Roblox's sales/brand-partnerships team under a title search results indexed as "Roblox Advertising Terms (Managed Campaigns)." This record could not independently confirm that document's content (see Open Questions); to the extent it constitutes negotiated, per-IO access rather than a standing self-serve program, it would fall outside this repo's inclusion policy regardless.
- **Independent/creator-paid brand integrations**, i.e. a brand paying a creator directly to feature a product inside that creator's experience outside of Ads Manager. Roblox's Independent Advertising Policy appears to regulate disclosure for this activity, but it is a negotiated creator-brand arrangement, not a published standing enrollment path with its own build/instrument/read surfaces, so it is not a regime this record documents.

## What a third party can render

Through Ads Manager, an advertiser buys **Immersive Ads**, which are placed inside ad units that experience creators (not the advertiser) build into their own experiences:

- **Image ads (billboards):** a static, non-clickable image displayed in the experience's 3D space [2][5].
- **Video ads (billboards):** a video up to 30 seconds long, either click-to-play or autoplaying (autoplay is sound-off and pauses when the viewer looks away) [2][5].
- **Portal ads:** a static, non-clickable image with a door that teleports the player into the advertiser's own experience; the advertiser's experience is required to include a button letting the player return to the experience they teleported from [2][5].

The ad unit itself (the in-world part) is placed by the publisher/creator, not the advertiser, and must fall within documented size bounds — no smaller than 8×4.5 studs, no larger than 32×18 studs — sit inside the experience's Workspace, not obstruct the player's view, and not duplicate an AdGui/SurfaceGui on the same face; for portal ads, only the ad unit's scale, position, and rotation may be modified by the publisher [2][5]. Ad content is served programmatically and personalizes per user; a player ineligible for a given ad sees a customizable fallback image or the Roblox logo instead [2].

Separately, through the same Ads Manager account, an advertiser can buy placements on Roblox's own platform surfaces rather than inside another party's experience: Search ads (sponsored game tiles matched to search keywords), Sponsored games (featured tiles in the Sponsored category, available in All Ages/9+/13+ tiers), and Sponsored items (user-generated 3D content promoted on marketplace pages) [10]. These share the same enrollment, terms, and account as Immersive Ads but do not render inside a third-party experience the way Immersive Ads do.

## What behavior the regime lets a third party instrument

No fetched source describes an advertiser defining or capturing its own custom events (e.g., a pixel or SDK an advertiser configures); all measurement here is Roblox-operator-defined per ad format.

Operator-defined metrics, as documented:
- Ads Manager reporting surfaces Amount Spent, Impressions, Clicks, Plays, Playtime, Cost-per-Play (CPP), and Robux Earnings [1][4].
- Roblox defines what counts as a billable/reportable event per format: an image-ad impression requires ≥1 second of view, the ad occupying ≥1.5% of the viewport, a viewing angle of ≤55°, and ≥50% of the ad's pixels visible; an autoplay video impression uses the same viewport/angle/visibility thresholds at ≥0.5 seconds; a click-to-play video is credited once ≥15 seconds are watched; a portal ad is credited on each successful teleport into the advertiser's experience [2][5].

Breakdowns/segmentation documented: reporting can be filtered by date range and by game/campaign; attribution differs by user segment — "New Users" carry up to a 30-day attribution window, while "Recent Users" are credited only for sessions that start with an ad click — and reported data can take up to 48 hours to appear [1][4].

Roblox's advertiser-facing marketing page separately names third-party measurement partners integrated into the platform — IAS and DoubleVerify (brand suitability), iSpot.tv and Nielsen (audience verification), Kantar and Cint (business outcomes) [9] — but no fetched source describes the mechanism by which their data reaches the advertiser or whether it requires separate enrollment with those vendors; left as an open question.

## What a third party can read and export, and who can read it

**Binding constraint:** no fetched source describes any role or team-permission model for a Roblox ads account. Documented access is per individual Roblox account credential; the one place roles are addressed at all is the Open Cloud API, which explicitly supports only user-owned API keys and states group-owned keys are "not in this version" [6]. There is no documented path for a business to grant a teammate scoped access (e.g., reporting-only, or billing-only) to a shared ads account.

Read surfaces, as documented:
- **Ads Manager dashboard** (ads.roblox.com): the primary reporting and billing interface, where an advertiser selects a date range and game/campaign to view the metrics listed above [1][4].
- **Open Cloud "Ads Manager" / Sponsored Campaigns API**, marked experimental (v1): authenticated via API key or OAuth2 using scopes including `ad.campaign:read`, `ad.campaign:write`, and `ad.billing:read`. It supports listing and reading campaigns, billing accounts, advertisable experiences, campaign eligibility/options, and the creative-asset library, and supports creating, updating, pausing, resuming, and cancelling campaigns [6][8]. Performance/reporting data is explicitly excluded from this API version — "Reporting is deliberately not in v1" — with reporting data remaining available only through the dashboard UI and a stated (unconfirmed) plan to fold metrics into a separate Analytics API later [6]. No source describes any of these endpoints as production-supported; the API is documented as subject to change.

No fetched source documents a CSV export function, a bulk-download path, or any reporting API in the current, generally-available product. Whether such export exists in the dashboard UI but is simply undocumented is left open below.

## Open questions

- Whether a Roblox "business" ads account supports multiple named users or seats with distinct roles (e.g., reporting-only vs. billing-admin) is not addressed in any fetched source.
- The full text and specific content-level rules of Roblox Advertising Standards, Roblox Advertising Terms, and the Independent Advertising Policy could not be independently confirmed: the Roblox Support (help.roblox.com) pages that appear to host them returned HTTP 403 to automated retrieval throughout this research, so this record names these documents (per create.roblox.com's own reference to them) without asserting their internal content.
- Whether a separately named "Roblox Advertising Terms (Managed Campaigns)" track exists, and if so, whether it is a negotiated per-Insertion-Order arrangement (which would place it outside this repo's inclusion policy) or an addendum to the same standing enrollment documented here, is unresolved — the title surfaced in search indexing but the page itself could not be fetched.
- The exact minimum Ad Credit purchase and Robux-to-Ad-Credit exchange rate is unresolved: fetched renderings of the same underlying documentation page disagreed (one gave 285 Robux per Ad Credit, another gave 263), so no specific figure is asserted here.
- A 2024-era self-serve Immersive Ads beta announcement stated a campaign-creation requirement of 18+ with credit-card-only payment, while the current general Ads Manager documentation states 13+ eligibility with Robux-funded Ad Credits accepted; no fetched source reconciles whether the eligibility requirement has since changed, or differs by ad format.
- Whether and how the third-party measurement partners named on Roblox's advertiser marketing page (IAS, DoubleVerify, Nielsen, iSpot.tv, Kantar, Cint) deliver data back to the advertiser, and whether that requires separate enrollment with those vendors, is not documented in any fetched source.
- Whether CSV/bulk export of Ads Manager dashboard reporting exists in-product (distinct from the API, which excludes reporting) is not addressed in any fetched source.

## Sources

1. Roblox Creator Hub, "Ads Manager," create.roblox.com/docs/production/promotion/ads-manager, retrieved 2026-08-21, official developer/advertiser documentation.
2. Roblox Creator Hub, "Immersive ads," create.roblox.com/docs/production/monetization/immersive-ads, retrieved 2026-08-21, official developer/advertiser documentation.
3. Roblox Creator Hub, "Advertise on Roblox," create.roblox.com/docs/production/promotion/advertise-on-roblox, retrieved 2026-08-21, official developer/advertiser documentation.
4. Roblox Corporation, Roblox/creator-docs GitHub repository, source markdown for "Ads Manager," raw.githubusercontent.com/Roblox/creator-docs/main/content/en-us/production/promotion/ads-manager.md, retrieved 2026-08-21, official documentation source repository.
5. Roblox Corporation, Roblox/creator-docs GitHub repository, source markdown for "Immersive ads," raw.githubusercontent.com/Roblox/creator-docs/main/content/en-us/production/monetization/immersive-ads.md, retrieved 2026-08-21, official documentation source repository.
6. Roblox Developer Forum (Roblox staff announcement), "[Test] Ads Manager API Now on Open Cloud," devforum.roblox.com/t/test-ads-manager-api-now-on-open-cloud/4766543, retrieved 2026-08-21, official first-party developer forum announcement.
7. Roblox Developer Forum (Roblox staff announcement), "Self-Serve Immersive Ads Creation and Management with Ads Manager [Beta]," devforum.roblox.com/t/self-serve-immersive-ads-creation-and-management-with-ads-manager-beta/2398950, retrieved 2026-08-21, official first-party developer forum announcement.
8. Roblox Creator Hub, Open Cloud reference, "Sponsored Campaigns," create.roblox.com/docs/cloud/reference/features/sponsored-campaigns, retrieved 2026-08-21, official API reference documentation.
9. Roblox for Brands, "Immersive Ads on Roblox," brands.roblox.com/advertising, retrieved 2026-08-21, official advertiser-facing marketing/product page.
10. Roblox Corporation, Roblox/creator-docs GitHub repository, source markdown for "Advertise on Roblox," raw.githubusercontent.com/Roblox/creator-docs/main/content/en-us/production/promotion/advertise-on-roblox.md, retrieved 2026-08-21, official documentation source repository.

## Standing note

Published documentation is a party describing its own product.

## Closing disclaimer

This record describes what this access regime documents as available. It does not establish that any activation running under it produces anything in particular. Capacity is not inventory.

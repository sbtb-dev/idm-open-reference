# `operator-relations/`

A sourced record of one relationship: which organization holds which role toward which environment.

## What an edge claims

That, as of the cited date, a named organization holds a specific, documented role toward a named environment — `operates`, `built_for`, `licenses`, or `hosts` — sourced to the hosting platform's own attribution or to independent third-party reporting.

**That is the entire claim.** An edge establishes nothing about the organization's quality, the environment's openness to outreach, the terms of the relationship, or whether it will still hold next month. It is a dated fact, not a standing endorsement, and it goes stale the way any dated fact does — see Maintenance below.

## Why it exists

`vendor-census/` states that an organization exists in this space. `brand-presence/` states that an environment has carried third-party brand presence at least once — including, in its own `operator` field, who built or ran the specific documented activation. Neither answers a different, narrower question: **who currently operates this environment's own instrumentation, right now** — the party a planner or vendor would actually need to reach for anything beyond the one activation `brand-presence` happened to document.

Those are not always the same organization. A studio can build an environment under commission and hand it off; a brand can hold the IP and license a separate studio to run it; a platform can host an environment whose day-to-day operation belongs to neither the platform nor the original builder. Without a dedicated record, the easiest-to-find name — often a licensor, findable by a plain search — surfaces ahead of whoever actually operates the thing, with no way for a reader to tell the difference. An edge exists to make that distinction a sourced fact instead of a guess.

## Role vocabulary — closed, no free text

- **`operates`** — runs the environment's own instrumentation day to day. The only role that supports "this organization's own records come from here."
- **`built_for`** — built the environment under commission, on behalf of another named party. Says nothing about who runs it now.
- **`licenses`** — holds or grants IP rights over the environment or its brand. Does not by itself mean this organization runs its instrumentation.
- **`hosts`** — provides the underlying platform or infrastructure the environment runs on. Not an operational claim about the environment itself.

Only `operates` says the named organization runs the environment's own records. The other three are informational — useful for knowing who else is in the picture — and never substitute for `operates` in anything that reads this roster to decide who to contact about an environment's own data.

An edge can carry more than one current role for the same organization-environment pair (a studio that built an environment and has since taken over operating it holds both `built_for` and `operates`) — see `ENTRY_TEMPLATE.md`. Each role is sourced and dated on its own; holding one role does not imply another.

## Sourcing — stricter than the rest of this repo, deliberately

Every other record type in this repo accepts an organization's own announcement about its own activity as a legitimate, often preferred, source — the organization is the authoritative party on what happened inside its own environment. An edge is different: it exists specifically so a reader can trust *who to contact*, and a self-report of "we operate this" is exactly the claim most worth independently checking before it routes anyone anywhere.

**Accepted:**
- **`PLATFORM_STATEMENT`** — the hosting platform's own public attribution, independent of either named party: a storefront or catalog page's "Created by," "Developer," or equivalent verified field (a Roblox experience page, an app-store listing, a console storefront's publisher/developer field).
- **`THIRD_PARTY_REPORTING`** — independent trade press or documented reporting naming the relationship, not authored by either party the edge names.

**Not accepted, on their own, no matter how it's phrased:** an announcement, press release, or public statement from either party the edge names — including the organization's own site, and including an operator's own announcement about a party it claims to have hired, acquired, or licensed. If the only available source is one of the two parties describing the relationship, the edge is not yet filable; wait for platform attribution or independent reporting, or route the finding to `brand-presence/` instead if it documents an activation rather than a standing relationship.

## What is not recorded, deliberately

**Contract terms, deal structure, or compensation.** An edge states a role, not an arrangement's substance.

**History.** An edge states the current role(s), sourced and dated. It is not a timeline of every organization that has ever touched an environment — a lapsed relationship is removed, not archived in place (see Maintenance).

**Anything about the organization's or environment's quality, reach, or fit.** Same non-evaluative discipline as every other record type here.

## Maintenance

An edge is a claim as of a date, not a permanent fact — organizations acquire and divest environments. An edge whose `as_of` date is more than 12 months old is flagged stale in `INDEX.md` rather than treated as current; a stale edge is reviewed, re-sourced, or removed, not left standing. This cadence is this repo's own — set independently, not by reference to any downstream consumer's convention, though it happens to match one.

Delisting is honored on request from either named party, without argument and without a stated reason, on the same terms as the vendor census.

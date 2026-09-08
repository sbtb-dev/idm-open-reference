# Proposal: widen `vendor-census`'s scope to cover environment operators

**Status: scope statement adopted; entry backfill pending.**
`vendor-census/INDEX.md`'s scope line now carries the extension this
proposal recommends. What's still open is the "immediate consequence"
below — backfilling minimal entries for the operators this unblocks — and
the sourcing caveat it's paired with. This document stays as the record of
why, not a pending ask.

An internal roster-design proposal — a mismatch between two of this repo's
own record types, not an outside request. Surfaced via `idm-on-ramp`'s use
of the roster (its `DEMONSTRATED (via operator edge)` basis is inert for
most `brand-presence` entries as a result), but the problem holds
independent of that consumer: `vendor-census` and `brand-presence` describe
overlapping ground without being able to join on it.

**Prerequisite, already done separately:** `vendor-census/INDEX.md`'s scope
line previously read "the third-party access, instrumentation, and
measurement space around game and virtual environments" — a description
that matched none of the 31 entries actually filed (zero mention
instrumentation, measurement, analytics, or access; all 31 build,
commission, broker, or operate branded experiences and integrations for
brand clients). That line has been corrected to describe the roster's
actual population, independent of this proposal. The gap and fix below are
restated against the corrected line, not the stale one.

## The gap

`vendor-census/`'s (corrected) scope is organizations found "building,
commissioning, brokering, or operating branded experiences and integrations
inside games and virtual environments" — vendors a brand would hire to get
an in-world presence. `brand-presence/`'s `operator:` field names a
different population: whoever runs the environment a placement happened in,
which is often the game's own first-party publisher — an organization that
does none of those four things for hire, since it isn't building or
brokering anyone else's presence, it's granting access to its own.

The two populations barely overlap. Across all current `brand-presence`
entries, 20 distinct operators are named (Electronic Arts, Riot Games,
Rockstar Games, Blizzard, HoYoverse, Ubisoft, Embark Studios, and others).
Exactly one — Voldex — also has a `vendor-census` entry, because Voldex
happens to run a studio-for-hire business on the side. The other 19 have no
route into the roster at all: they're out of `vendor-census`'s scope by
definition, and none of them has an `access-reference/records/` entry either
(that directory covers five platform-level programs — Fortnite Island
Creator, Minecraft Marketplace, Roblox Ads, Roblox Creator Experiences,
Zepeto Studio — none of which are these operators).

This isn't just a naming gap. `operator-relations/`'s per-edge
`organization` field must resolve to a `vendor-census` entry — that's
`roster-operator-edge-inventory-guide.md`'s step 3 (an `idm-on-ramp` doc,
see `notes/proposals/roster-operator-edge.md` there for the record type
itself). So the majority of `brand-presence`'s highest-value, already-vetted
environments structurally cannot get an `operates` edge filed, not for lack
of a citable source, but because the organization side of the edge has
nowhere to live in this repo.

The practical cost lands on `idm-on-ramp`'s planners, but it's this repo's
own roster that has the hole: a reader who already trusts `brand-presence`'s
evidence has no roster entry to carry that trust into for 19 of 20 named
operators. Nothing else in the roster (not `access-reference`, which is
platform-program-scoped, not `operator-relations`, which needs
`vendor-census` to already have the name) fills it.

## Recommended fix: extend the (now-corrected) scope statement, not the shape

Add one more clause to `vendor-census/INDEX.md`'s corrected scope line,
alongside "builds, commissions, brokers, or operates": also cover any
organization already documented elsewhere in this roster as operating,
building, licensing, or hosting a covered environment — i.e., anyone named
in a `brand-presence` entry's `operator:` field or eligible for an
`operator-relations` edge. Scope stays anchored to existing evidence trails,
not "any game studio that exists": an organization qualifies because this
roster already has a sourced reason to name it, the same bar `vendor-census`
already applies to a vendor found in a sweep.

No change to `vendor-census`'s contribution rule, template, or non-endorsement
framing. An entry for Rockstar Games reads exactly like an entry for Atlas
Creative: name, slug, website, a one-line non-evaluative "what they do,"
added by someone other than the org. The roster has never claimed a vendor
is good; it won't start claiming an operator is reachable, either — presence
states only that the organization was found operating in this space, full
stop.

**Immediate consequence, not a separate step:** every operator already named
in a `brand-presence` entry is now in scope and can get a minimal
`vendor-census` entry through the normal low-friction process. This unblocks
`roster-operator-edge-inventory-guide.md`'s Pass 1 for the ~19 operators
currently stuck at its step 3 — that guide's "waits or is deferred" language
for a missing `vendor-census` entry should be revisited once this lands,
since for these cases the wait ends here rather than staying open-ended.

## Why this doesn't require any `idm-on-ramp` change

`idm-on-ramp`'s `pre-call-prep.md` already assumes the org across the table
may be a licensor or platform holder rather than a service vendor — its
COUNTERPARTY check exists precisely to catch that case (see
`idm-on-ramp/notes/design-decisions.md`, "Why the operator edge is a roster
record, not a prompt inference"). The on-ramp's prep and discovery flows
don't care what kind of deal an organization implies; they only need a named
organization to reason about. This proposal supplies that name where it's
currently missing — it changes no on-ramp logic.

## Alternatives considered

- **Do nothing; let planners identify these organizations ad hoc.** Rejected
  — this is the exact reverse-engineering cost the roster exists to remove,
  and it falls hardest on `brand-presence`'s already-vetted, highest-value
  entries.
- **A fifth record type (e.g. `operator-census`) parallel to
  `vendor-census`.** Rejected — the actual problem is a scope statement,
  not a missing shape. A second roster would also break
  `operator-relations`'s single join key (`organization` resolving to one
  place), reintroducing exactly the "which of two directories" ambiguity
  the fourth-record-type decision in `roster-operator-edge.md` avoided.

## What this doesn't change

`vendor-census`'s name and framing stay as they are — renaming it once it
also covers platform holders is a bigger, separable question, and the
current name has not caused confusion in the roster's own docs (`operator`
and `vendor` are already used as distinct terms throughout
`operator-relations/README.md`). This proposal is a one-line scope change
plus a backfill of already-known names, not a rebuild.

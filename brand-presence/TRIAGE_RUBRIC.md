# Triage Rubric

How `brand-presence/` admissibility is decided at the grey edge — read by
`idm-sweep`'s admissibility check, pinned there by commit SHA so a sweep run
stays reproducible against fixed rubric text (see `idm-sweep`'s
`config/rubric_pin.yaml` and `docs/RUBRIC_DEPENDENCY.md`). See
`CONTRIBUTING.md`'s "What we will not merge" for why this file is a
deliberate, narrow exception to the no-specification-content rule, and why
it isn't precedent for anything else.

## What this is

`README.md`'s Scope section already states the boundary in plain language:
in scope is presence placed by a non-operator party, for that party's own
marketing, sanctioned by the operator, rendered inside the environment.
Almost every case that boundary describes is unambiguous on its own. This
file exists for the minority that isn't — it resolves the same boundary into
three independently-answerable tests and works through the grey cases where
a quick read of an announcement doesn't obviously settle one of them. It
adds no criteria beyond what `README.md`'s Scope section already draws.

## What this is not

- **Not a qualification standard.** `idm-public-corpus` uses "qualification"
  for a different question entirely: whether an environment produces
  response-grade evidence of consumer behavior, native and attributable
  (see `founder-notes/Immersive_Is_One_Qualification_Away.md`). That
  question is downstream of this repo, belongs to whoever reads
  `brand-presence/` for candidate generation later, and has no bearing on
  what this rubric decides. An activation that plainly wouldn't qualify by
  that evidentiary standard can still pass all three tests below and be
  admitted — the two questions don't touch.
- **Not evaluative.** A resolution states what the announcement's own facts
  show and which test that satisfies or fails. It never states whether the
  activation performed well, was well executed, or is a good example of
  anything.
- **Not a way to decide a case the announcement's own text doesn't settle.**
  Where a worked example below doesn't cover the shape of a new case, the
  correct output is an open case, not an inference from the pattern that
  seems closest.

## Test 1 — In vs. about

**Was the presence carried inside the environment, or in media about it?**
A placement rendered inside the game or virtual environment passes. A
sponsored stream, a creator's video, an overlay pointing viewers elsewhere —
media *about* the environment or *about* the brand's activity near it —
fails.

- **Pass.** Mountain Dew's DEW University, a fully playable branded team
  with its own stadium and mascot built inside EA College Football, is
  rendered inside the game itself
  (`founder-notes/Is_EA_Buying_the_Billboards_It_Sells_.md`).
- **Fail, by the transferable pattern.** The Żabka/Triki campaign's Twitch
  broadcasts — streamers demonstrating a controller, with an overlay
  dropping a QR code — carry the presence on a stream *about* the
  destination, not inside a game environment
  (`founder-notes/Immersive_Is_One_Qualification_Away.md`). That essay
  isn't a brand-presence case itself — the destination is the brand's own
  app, not a third party inside an operator's environment — but the line it
  draws between a broadcast pointing at a place and presence rendered
  inside one is exactly this test.
- **Undecided, don't force it.** An announcement describing a "gaming
  creator campaign" that shows a creator playing near or using a branded
  placement, without stating whether the operator itself rendered that
  placement as a persistent in-environment object versus the creator
  building or staging it for the video, doesn't resolve on its own text.
  `category-essays/Gaming_Is_Not_a_Channel.md` treats gaming creator
  content and in-game branded integration as categorically distinct for
  exactly this reason — record open case rather than assuming the creator
  is merely showing something the operator built.

## Test 2 — Sanctioned vs. unsolicited

**Did the brand organize or sanction the presence?** Unsolicited,
brand-unaffiliated user-generated content fails, however large its reach.

- **Fail, at real scale.** KFC's unofficial Roblox footprint — Escape KFC
  Obby alone carrying 44 million lifetime visits, roughly 600 fan-made
  marketplace items, none of it commissioned or organized by KFC
  (`founder-notes/Brand_Footprint_Is_Not_Response.md`). Scale doesn't
  substitute for sanction; this fails test 2 outright regardless of the
  visit count.
- **Pass, same brand, different platform.** KFC's official Fortnite island,
  launched 2024, is the brand's own commissioned strategy — sanctioned by
  construction (same source).
- **Undecided, mind the date.** The source essay names three ways a brand
  can respond to unsolicited fan activity: enforcement, formalization, or
  building — noting Chipotle "formalized what fans were already doing."
  Where an announcement states a brand later licensed, endorsed, or
  otherwise formalized previously-unsanctioned fan content, sanction begins
  at the formalization event, not retroactively — `first_observed` should
  cite the formalization, never the original unsanctioned activity. If the
  announcement only shows brand *awareness* of fan activity, without a
  stated act of formalization, that is not yet sanction — record open case
  rather than reading acknowledgment as endorsement.

## Test 3 — Third-party vs. operator

**Is the brand a party other than the environment's operator?** An
operator-built integration for an outside brand can still pass — the brand
remains third-party. Operator self-promotion of its own IP fails, however
similar the placement mechanics look to a third-party one.

- **Pass.** DEW University (Test 1's example) again: EA built the
  integration, using its own development and ad infrastructure, but the
  party being marketed is Mountain Dew. The operator's hand in building it
  doesn't make Mountain Dew any less third-party.
- **Fail, by the transferable pattern.** `Is_EA_Buying_the_Billboards_It_Sells_.md`
  poses its own due-diligence question: does EA advertise its own titles
  (Madden) on the same in-game ad boards, scoreboards, and overlays it
  sells to outside brands? If it does, that placement is operator
  self-promotion — no third party is present, however identical the unit
  looks to Mountain Dew's. **The essay is explicit that the public record
  does not settle this** — a live sweep encountering a candidate shaped
  like this must establish, from its own cited sources, whether the party
  being promoted is the operator or an outside brand. Never import this
  essay's open question as a finding about any specific environment.
- **Out of frame entirely, not merely undecided.** The same essay notes EA
  bundles Madden and College Football together in a single retail
  promotion (the MVP Bundle) and a joint TV spot. That is the operator
  cross-promoting its own titles through retail and broadcast channels —
  it was never a stage-1 brand-presence hit in the first place, because no
  third party's presence inside an environment is described. Recognize and
  set this pattern aside at stage 1; it isn't a test-3 fail requiring a
  logged exclusion, because it never described in-environment presence to
  begin with.

## Open questions

- **Entertainment-IP collaborations** are already excluded in plain
  language by `README.md`'s Scope section, and no essay reviewed for this
  rubric's authoring supplied a grey-area case sharp enough to add anything
  here. If a maintain-cycle sweep surfaces a genuine grey case on that
  boundary, propose an addition to this file through the same review this
  file itself went through — don't resolve it silently inside a single
  sweep's disposition.
- **Platform advertising products** (test-3-adjacent: operator-sold ad
  inventory bought by a third party) are also already excluded in plain
  language by `README.md`'s Scope section as belonging to
  `access-reference/`. This rubric doesn't currently add a worked example
  distinguishing a platform ad buy from an operator-built third-party
  integration like DEW University; both are structurally "operator builds,
  third party benefits," and the distinguishing fact is whether the unit is
  a published, standing ad product versus a bespoke build. Left as an open
  question for the same reason as above rather than guessed at here.

## Sources

1. `idm-public-corpus`, `founder-notes/Brand_Footprint_Is_Not_Response.md` — read in full 2026-08-24.
2. `idm-public-corpus`, `founder-notes/Is_EA_Buying_the_Billboards_It_Sells_.md` — read in full 2026-08-24.
3. `idm-public-corpus`, `category-essays/Gaming_Is_Not_a_Channel.md` — read in full 2026-08-24.
4. `idm-public-corpus`, `founder-notes/Immersive_Is_One_Qualification_Away.md` — read in full 2026-08-24.

## Maintenance

This file changes rarely and deliberately. `idm-sweep` pins a specific
commit of this file and re-reads it only when that pin is deliberately
updated — editing this file does not retroactively change what a past sweep
run was certified against. Propose changes the way any other change to this
repo's inclusion policy would go through review; this is closer in weight to
`README.md` than to a roster entry.

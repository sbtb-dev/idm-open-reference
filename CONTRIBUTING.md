# Contributing

This repo has two very different kinds of content, and the bar is different for each.

- **`vendor-census/`** is a low-friction roster. Adding an entry should be easy.
- **`access-reference/`** is a sourced reference. Adding or editing a record carries real discipline, because the whole point of the layer is that a reader can trust it without re-checking it.

## Adding a vendor to the census

Copy `vendor-census/ENTRY_TEMPLATE.md` to `vendor-census/entries/{org-slug}.md`, fill it in, and add the entry to the roster in `vendor-census/INDEX.md`. Use the PR template `add-vendor.md`.

Presence on the census is not endorsement. Say only what is publicly verifiable (the org exists, operates in this space, and can be reached) — nothing evaluative.

Entries must be added by someone other than the org being listed, based on independent identification (a sweep, a public listing, outreach found elsewhere) — not filed by the vendor about itself. Write "What they do" in your own words from what the sweep found publicly; do not copy or lightly paraphrase the vendor's own marketing copy. The census reads as third-party identification, not vendor self-description — an entry that carries the vendor's own voice, however short, undoes that distinction.

## Adding or editing an access regime record

Use `access-reference/RECORD_TEMPLATE.md` and the PR template `add-regime-record.md`. Before opening a PR:

1. **Check the inclusion policy first.** A record is written only where a standing, published third-party access regime exists — see `access-reference/README.md` §"Inclusion policy." If access is negotiated per deal, no record belongs here at all; see the inclusion policy for why.
2. **Check the individuation rule.** Same enrollment path, same governing terms, same role model = one regime, one record. Do not fork a record over a feature difference; do fork over a different enrollment path or terms.
3. **Source every statement to published documentation** — developer docs, program terms, role/permission references. Cite publisher, retrieval date, and source class in the record's Sources section.
4. **Where documentation is silent, say so in Open Questions.** Never infer, and never fill a gap with a plausible guess.
5. **Do not fold in testimony.** Community wikis, press coverage, and vendor or operator claims about the regime's capabilities are not sources for this layer, regardless of credibility. See the public/private boundary in `access-reference/README.md`.

### Terms-of-service posture

Records are built by reading public documentation in a browser. No crawling, no authentication, no access to gated material, and no reproduction of documentation beyond short cited statements.

If automated retrieval is ever added to how this repo's content is produced, that condition breaks and the terms-of-service question reopens. Treat this as a rule, not a habit.

### Review cadence

Every record is reviewed at least once per 90 days, sooner if an operator ships or deprecates developer tooling, changes program terms or role definitions, or opens or closes an access tier. A review that confirms nothing changed is a real contribution — bump `last_reviewed` and `next_review` and say so in the commit message, even with no content changes.

## Adding a brand-presence entry

Copy `brand-presence/ENTRY_TEMPLATE.md`, fill it in, add it to
`brand-presence/entries/`, and add your alphabetical row to `INDEX.md` in the
same PR.

Entries are accepted or returned on mechanical grounds only:

1. The presence described is out of scope — an entertainment-IP collaboration,
   a platform advertising product, operator self-promotion, unsanctioned
   player-made content, or presence on a broadcast or creator surface rather
   than inside the environment. (See `brand-presence/README.md`.)
2. The environment already has a record in `access-reference/records/`.
3. A citation is missing, unreachable, or does not support the claim.
4. The entry duplicates an existing one.
5. The entry adds fields outside the template — including form of presence,
   brand names, campaign detail, results, or notes.

Items 3 through 5 are returned for changes, not closed. Where scope is arguable,
raise it in review rather than assuming either way — the exclusions in item 1
exist to keep the claim narrow, not to keep entries out.

Delisting is honored on request from the operator, without argument and without
a stated reason.

## Corrections and delisting

Use the `correction.md` or `delisting-request.md` issue templates. For a census entry, a delisting request needs no justification beyond the requester's identity and connection to the organization. For an access-reference record, a correction should point to the specific documentation that supports the change.

## What we will not merge

- Ratings, rankings, or comparative claims between vendors, environments, or operators.
- Unsourced or testimony-based claims in `access-reference/`.
- Specification-like content — thresholds, pass conditions, or evaluation logic — anywhere in the repo.

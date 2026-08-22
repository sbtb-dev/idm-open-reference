# `access-reference/`

## Vocabulary

Three terms, kept distinct throughout this directory.

**Environment** — the place players are. Fortnite. A Roblox experience. A live-service title.

**Operator** — the party running the environment and holding its instrumentation.

**Access regime** — the arrangement by which a party that is not the operator gets in. This is what a record describes.

The distinction is load-bearing because capability belongs to the environment but a buyer never touches the environment directly. They touch it through a regime, and the regime determines what reaches them. An environment observes what its operation requires; a regime exposes a specific, role-gated subset of that. The gap between those two facts is where bundled vendor claims live.

## What a record is

> **Access regime.** A published, standing arrangement under which a party other than the environment's operator can (1) build, place, or publish something inside the environment, (2) record behavior toward what it built, and (3) read or export those records. A regime is constituted by four published elements: an enrollment path stating who may participate, a build surface, an instrumentation surface, and a read/export surface with named roles. Where any of the four is absent or unpublished, there is no regime to record.

A record describes one access regime. It does not describe a company, a product, a game, or a platform, and the same environment may carry several regimes with materially different answers.

## Individuation rule

**Same enrollment path, same governing terms, same role model = one regime.**

Not same rendered output, same instrumentation, or same export format — those change constantly and would make every incremental feature difference a potential fork. Enrollment, terms, and roles are how access is actually granted, they change rarely, and they survive platforms shipping features.

Applied:

- Two authoring tools inside the same enrollment, portal, roles, and terms → one record.
- A different enrollment path or different terms (e.g. an advertising product sold separately from a creator program) → a separate record, even on the same environment.
- A new partner tier with its own terms and roles → forks a new record rather than editing the existing one.

## Inclusion policy — published access, not negotiated access

A record is written only where a standing third-party access regime is published: platform ecosystems selling third-party building as a product, with developer documentation, program terms, and role definitions.

No record is written for environments where third-party access is negotiated per deal. A single live-service title with no standing creator or brand program publishes nothing, because the deal *is* the access regime, written per contract. Three reasons:

1. **The amortization is zero.** A record earns its place by serving many options from one adjudication. A regime record serves every option built under it; a title with one brand activation at a time is 1:1, and the layer buys nothing.
2. **There is nothing to build from.** A record written to this standard about a title with no published program would be almost entirely open questions — honest and nearly useless.
3. **A mostly-empty record about a named title reads as an accusation.** "Not stated in the documentation" is institutional discipline where a documentation practice exists and something is missing from it. Where none exists, it scans as a charge of opacity levelled at exactly the operators the category needs as participants.

`records/` therefore stays small and stops growing early. That is the directory working. The far larger negotiated-access population is covered by `self-description/ENVIRONMENT_ACCESS_TEMPLATE.md` — the record's shape, offered to operators to complete about themselves, rather than a record written about them.

Separately, `brand-presence/` records which environments have carried third-party brand presence at least once. That is precedent, not a regime: it evidences that a door has opened, and says nothing about its terms.

**Two edge cases, settled:**

- **Published access that forbids commercial presence.** A public modding SDK may satisfy all four elements while prohibiting commercial third-party activity. It gets recorded, with the prohibition stated in the scope section. It is a real regime whose terms exclude the use a buyer wants — a fact worth writing down once rather than rediscovering per conversation.
- **Undocumented partner tiers.** Not regimes for this purpose; nothing is published. They stay as an open question inside the parent record.

## Record structure

Fixed section order. Scope before content, so a reader cannot mistake which regime is described; open questions before sources, so gaps are read before citations. See `RECORD_TEMPLATE.md` for the full template.

Two rules inside the sections:

- **Third-party-defined instrumentation is listed before operator-defined metrics.** The operator's own metric list is the longest and least informative part of any documentation set; leading with it reproduces the operator's framing. What a third party can record about its *own* build is the question.
- **The read/export section states the regime's binding constraint once, in plain language**, where a skimming reader will hit it — most often role-gating: who on a third party's team actually holds a documented path to the data.

Sourcing discipline: every statement sourced to published documentation. Where documentation is silent, `open_questions` says so and the record does not infer. Community wikis, press coverage, and vendor accounts appear only tagged third-party and unverified, never folded in as fact.

## How the records are used

One job: fix, once, what a regime documents as available, so the same question is not re-litigated in every vendor conversation. Downstream, five uses:

1. **Triage.** Option records point at a regime record; the access layer is established once and distributed to every option riding on it. It never raises an option's standing by inheritance.
2. **Preparation.** The record sets the floor and ceiling of plausible vendor answers, which is what lets a planner without platform fluency hear when an answer sits outside them.
3. **The conversation.** The open questions are the agenda. Operators are the only parties who can resolve what documentation leaves unsettled.
4. **Specification.** The record separates what is worth requiring from what the regime cannot supply, and surfaces terms that are contractual rather than technical. Access roles are the standing example: costless to the vendor, decisive for who owns the evidence, invisible to anyone who didn't know the gate existed.
5. **Reporting.** When delivered evidence falls short, the record locates the failure — the regime couldn't, or the vendor didn't. Different remedies, different implications for the next buy.

## What the records are not for

- **They do not qualify anything.** A regime's capabilities show that something can exist there, never that a given activation does. Capacity is not inventory.
- **They do not substitute for the conversation.** A reader who takes the record and skips the operator has learned the regime's floor and nothing about the option in front of them.
- **They do not support cross-record comparison.** Comparing two records measures documentation depth at least as much as capability. "Which environment is better instrumented" is a question these records cannot answer, and a reader who tries will get a confident wrong answer.

## The public/private boundary

**Only documented facts and open questions are published.** Operator and vendor testimony about a regime's capabilities stays out of the public record entirely, regardless of credibility or how well it resolves an open question.

Publishing one company's characterization of another company's product is a position this repo should never occupy. And admitting unsourced testimony would convert a sourced reference into an aggregation of hearsay, which is the fastest route to the artifact losing the only property it has. Testimony accumulates where it belongs, outside this repo.

## Review cadence

Every record is reviewed at least once per 90 days — sooner if an operator ships or deprecates developer tooling, changes program terms or role definitions, or opens or closes an access tier. See `COVERAGE.md` for current status and mechanics.

## Schema note

The identifying field for a record is `regime_id`, in the format `REGIME/{slug}` (e.g. `REGIME/fortnite-island-creator`). If you maintain a private schema that references these records, point it at `regime_id`, not at any environment- or host-level identifier — a field name that misstates its referent recreates the platform-level category error this directory exists to avoid.

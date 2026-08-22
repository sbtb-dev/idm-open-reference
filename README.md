# idm-open-reference

Vendor- and operator-facing reference material. Companion to [`sbtb-dev/idm-public-corpus`](https://github.com/sbtb-dev/idm-public-corpus). Split into its own repo by design: the corpus's essay/founder-note split exists so a reader never has to guess which kind of authority they're reading, and a third authority class in the same tree would undo that.

## What's here

```
idm-open-reference/
├── README.md
├── CONTRIBUTING.md
├── LICENSE                              # CC BY 4.0
├── vendor-census/
│   ├── INDEX.md                         # alphabetical roster, non-endorsement header, sweep log
│   ├── ENTRY_TEMPLATE.md
│   └── entries/
│       └── {org-slug}.md
├── access-reference/                    # what a published third-party access regime documents
│   ├── README.md                        # what a record is, what it is not, how it is used
│   ├── COVERAGE.md                      # regimes recorded, gaps, review dates, scope statement
│   ├── RECORD_TEMPLATE.md
│   └── records/
│       └── ...                          # one file per published access regime
├── self-description/
│   ├── README.md
│   ├── VENDOR_OPTION_TEMPLATE.md        # per option sold — for sellers
│   └── ENVIRONMENT_ACCESS_TEMPLATE.md   # per environment — for operators
└── .github/
    ├── PULL_REQUEST_TEMPLATE/
    └── ISSUE_TEMPLATE/
```

**`vendor-census/`** — An alphabetical, non-endorsing roster of vendors found during scope sweeps. Presence on the roster is not a claim of quality, and absence is not a claim of anything.

**`access-reference/`** — One record per published third-party access regime: what an operator documents as available to parties other than itself, in three parts — what can be built, what behavior the builder can record, and what leaves the environment, to whom. Sourced, dated, and explicit about what the documentation does not settle.

A regime is an arrangement, not a company or a game. One environment may carry several, and records are written only where a standing arrangement is published. Environments where access is negotiated deal by deal are out of scope by policy, not by judgment — see [`access-reference/COVERAGE.md`](access-reference/COVERAGE.md).

A record describes what a regime makes available. It never establishes that any activation running under it produces anything in particular, and records are not comparable to each other: two records differ in documentation depth at least as much as in capability.

**`self-description/`** — Templates that let vendors and operators state, in their own words and at their own initiative, what they sell or what their environment makes available. Self-attested, unverified, published only where the organization chooses to publish it.

## What's not here

- **Endorsement or vetting of any vendor.** The census records who exists, not who is good.
- **Ratings, rankings, or comparisons of environments or operators.** The access reference records what each regime documents. It does not score them, order them, or evaluate them against one another, and absence of a record says nothing about anyone.
- **Specifications.** Nothing here defines a standard, a threshold, or a pass condition. See the boundary flag in [`self-description/README.md`](self-description/README.md) for the one template that sits closest to that line.
- **Unsourced testimony.** Operator and vendor claims about a regime's capabilities, however credible, do not enter the access reference. See [`access-reference/README.md`](access-reference/README.md).

## License

This repository is licensed [CC BY 4.0](LICENSE).

This license covers this repository's organization, sourcing, and wording. The underlying documentation belongs to the operators who published it and is cited, not relicensed.

## Contributing

See [`CONTRIBUTING.md`](CONTRIBUTING.md).

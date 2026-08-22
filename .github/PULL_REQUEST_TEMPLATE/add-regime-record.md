## Adding or editing an access regime record

- **Regime:**
- **`regime_id`:**
- **New record, or edit to an existing one?**

### Checklist

- [ ] Checked the inclusion policy — this is a standing, published third-party access regime, not negotiated per-deal access
- [ ] Checked the individuation rule against any existing adjacent records on this environment (same enrollment/terms/roles = same record; different = separate record)
- [ ] Followed the fixed section order in `RECORD_TEMPLATE.md`
- [ ] Every statement in "renders / instrument / read and export" is sourced to a numbered entry in Sources (publisher, retrieval date, source class)
- [ ] Everything the documentation doesn't settle is in Open Questions, not silently omitted or inferred
- [ ] No community-wiki, press, or vendor/operator testimony folded in as fact
- [ ] `last_reviewed` and `next_review` are set (next_review = last_reviewed + 90 days, or sooner if a known event trigger applies)
- [ ] If this is a new record, added it to the table in `access-reference/COVERAGE.md` and removed it from the "not yet recorded" list if it was there

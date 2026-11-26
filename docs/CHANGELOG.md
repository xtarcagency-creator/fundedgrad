# Changelog

Newest first.

## 0.1.1 (unreleased)
First real run (Gemini CLI, then Claude Code) found:
- `plan` skipped every unscored row; it now includes `?` rows.
- Sources were homepages; the exact page/PDF is now required.
- Ruled-out funding schemes had nowhere to go; new `data/notes.md` session log.
- Official sites sometimes return errors; official-domain snippets allowed if marked.
- Triage now ends by naming which rows to evaluate next.
- Test 2 (four parallel `evaluate` runs on real programs) found and fixed:
  - no rule for calls not yet published: now `? (last: …)`, `est.` only in `plan`; a first run had
    presented a third-party guess as an official deadline
  - one program with several funding routes: one row per program, routes listed, best eligible one scored
  - `Stipend/mo` didn't fit yearly grants: now `Stipend` with its period; marked `≈` arithmetic allowed
  - rows needed many sources: extra sources go in `data/notes.md`
  - undefined scoring: deadline-safety bands, living-cost benchmark, 0-5 with one decimal
  - PDFs and filter-gated pages: extract text / set filters before giving up
  - `plan` prep times now include attestation, legalised documents and visa
  - profile template: credit breakdown, optional income band and gender for funding rules
- README redesigned: badges, mode table, made-up example session and tracker, scoring, file layout, privacy notes.

## 0.1.0 (unreleased)
- `AGENTS.md` with setup, search, evaluate, triage, plan, sop and update modes.
- Eligibility filter + weighted scoring; tracker format.
- `profile.example.md` template; `data/` gitignored.
- `review` mode: an application critiqued separately by a simulated committee chair, faculty member and scholarship panel member.
- Seed list of official scholarship catalogues.
- `docs/ROADMAP.md` now tracks each feature's status (built / tested / partial), next, later and won't-do.

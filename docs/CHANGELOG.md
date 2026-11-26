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
- `sop` must read like the student wrote it: keeps their phrasing, avoids common AI tells.
- `sop` writes plainly: no em dashes or stock phrases; optional writing-style rules in the profile.
- `sop` now builds a base SOP by interview when the student has none (found when the first real user had no draft).
- Test 3: five made-up students (Nigeria, India, Bangladesh, Indonesia, Colombia) plus three real searches.
  Fixed: scheme rows for portable funding (GKS, MEXT, LPDP); `closed` status and `partial` / `loan` types;
  dates with no year, conflicting dates/amounts, self-contradicting rules; grade-floor scale mismatches and
  funder-required conversions; official acceptance payments vs scams; bilingual preference; evaluate now
  extracts return-home obligations, real degree start, recognised-degree status, credential-check costs and
  closed test lists, and flags over-budget totals and stipends below visa means; scheme-first search; parallel
  prep times incl. credential checks and supervisor contact; funding caps for scarce awards and loans; rounding;
  re-hosted official documents; search-engine summaries are never a source (a real run misreported a PoliMi
  deadline that way). Profile: date of birth, test sub-scores, GRE/national tests, start window.
- Global use (D-008): nationality checked against each funder's list, home-country nomination
  routes, fee waivers, visa proof-of-funds and post-study work rights extracted, no grade
  conversion, scam warnings, conversation in the student's language, worldwide government
  scheme list, profile fields for degree length and application budget.
- README redesigned: badges, mode table, made-up example session and tracker, scoring, file layout, privacy notes.

## 0.1.0 (unreleased)
- `AGENTS.md` with setup, search, evaluate, triage, plan, sop and update modes.
- Eligibility filter + weighted scoring; tracker format.
- `profile.example.md` template; `data/` gitignored.
- `review` mode: an application critiqued separately by a simulated committee chair, faculty member and scholarship panel member.
- Seed list of official scholarship catalogues.
- `docs/ROADMAP.md` now tracks each feature's status (built / tested / partial), next, later and won't-do.

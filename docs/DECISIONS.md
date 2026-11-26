# Decisions

Why things are the way they are. Read before re-deciding.

## D-001 CLI agent, not an app (2026-11)
Instructions + markdown run in any AI coding CLI. No server, no hosting or
AI cost for us, personal data never leaves the user's machine, trivial to
fork. Revisit if non-technical users want it.

## D-002 Track program + funding pairs (2026-11)
A scholarship without admission, or admission without funding, is useless.
Bundled, separate, waiver-only and unfunded are recorded explicitly.

## D-003 No scraper; use the CLI's web tools (2026-11)
Every supported CLI can already search and fetch. Build our own only on
evidence that it misses important catalogues.

## D-004 No invented facts (2026-11)
Every program fact needs a source URL and check date; every claim about the
student must come from their profile. Unknown is `?`. Applications with a
fabricated claim can be rejected or revoked.

## D-005 Personal data is gitignored (2026-11)
Everything personal lives in `data/`, which is in `.gitignore`. Nothing in
the repo may contain a real person's profile, tracker or SOP.

## D-006 Model-agnostic instructions (2026-11)
`AGENTS.md` names no model and no vendor-only feature, so it runs in any
CLI on any capable model. Model routing (e.g. a cheaper model for
`triage`) is a later, optional add-on, only if real use shows cost or
speed problems.

## D-007 No pre-built program database (2026-11)
Deadlines, amounts and eligibility change every cycle, so a shipped list
of programs would be wrong within a year and contradict hard rule 2.
We ship only slow-changing country facts (who funds, when cycles open,
post-study work rights) with sources and check dates; programs are always
found and verified live.

## D-008 Built for students everywhere (2026-11)
Most users will be from low- and middle-income countries. So nationality
is checked against each funder's own lists, home-country nomination routes
are searched, application costs and visa proof-of-funds count in scoring,
grades are never converted by the agent, scams are flagged, and the agent
talks in the student's language. Gemini CLI's free tier is listed first so
no paid subscription is required.

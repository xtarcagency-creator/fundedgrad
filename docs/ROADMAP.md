# Roadmap and feature status

The one place to see what fundedgrad does, what's left and what it won't do.
Move rows between sections; don't delete them.

**Status key:** `built` = written in `AGENTS.md` · `tested` = used on real
programs by a real student and it worked · `partial` = exists but has a known gap.
A feature isn't done until it's `tested`.

## Features built

| Feature | Mode | Status | Known gaps |
|---|---|---|---|
| Profile interview → `data/profile.md` | `setup` | built | Not run yet |
| Extract program + funding facts from a page | `evaluate` | built | Not run on real pages |
| Hard eligibility filter (nationality, GPA, dates, tests) | `evaluate` | built | |
| Weighted 6-dimension score with shown arithmetic | `evaluate` | built | Weights are a guess; need real feedback |
| Quick verdicts for many links | `triage` | built | |
| Web search for new programs | `search` | built | JavaScript-heavy catalogues may not load |
| Seed list of official catalogues | `search` | partial | Links not verified |
| Deadline / prep-time plan for the week | `plan` | built | Prep-day estimates are rough defaults |
| Stale-row flag (checked > 30 days ago) | `plan` | partial | Flags only; doesn't re-check |
| Tailored SOP with claim-by-claim sources | `sop` | built | Needs `data/sop/base.md` written by the student |
| Simulated selection panel (chair, faculty, scholarship panel) | `review` | built | A simulation; can't know real committee preferences |
| Update status / documents | `update` | built | |
| Tracker table (`data/tracker.md`) | all | built | |
| No-fabrication and never-submit rules | all | built | |
| Personal data kept out of git (`data/` ignored) | — | built | `git add -f` can still bypass it |

## Next (before inviting friends)

| Item | Why |
|---|---|
| Run every mode end to end on 5–10 real programs | Nothing is `tested` yet |
| Verify every link in **Sources** | Dead links waste the agent's searches |
| Try it in Gemini CLI as well as Claude Code | Friends without a paid plan will use Gemini |
| Write a short "first 10 minutes" example in the README | Lower the setup barrier for testers |

## Later (only if testing shows the need)

| Item | Trigger to build it |
|---|---|
| Country guide: stable facts per country (funders, cycle months, post-study work rights, tuition norms), each with source + checked date | Agreed idea; research not run yet |
| `recheck` mode: re-verify stale rows automatically | Deadlines change and `plan` flags pile up |
| Recommendation-letter tracker (who, which program, by when) | Free text in `Docs` gets messy |
| CV tailoring per program | Testers ask for it |
| Document checklist per country (APS, attestation, etc.) | Same questions keep coming up |
| Parallel `triage` with a cheaper model (Claude Code only) | `search` is slow or expensive |
| PhD and other degree levels | Master's works well first |
| Own scraper or search API | Built-in search keeps missing catalogues |
| Web or mobile app | Non-terminal users want it |

## Won't do

| Item | Reason |
|---|---|
| Submit applications, send emails, pay fees | The student always acts (hard rule 4) |
| Write claims the student can't back up | Fabrication gets applications rejected or revoked |
| Store users' data on a server | Privacy; see D-001 and D-005 |
| Name a specific AI model in `AGENTS.md` | Must work in any CLI; see D-006 |

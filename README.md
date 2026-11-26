<div align="center">

# 🎓 fundedgrad

**Your AI agent for finding funded Master's programs.**
It searches official sources, checks whether you're eligible, ranks programs by funding and career value, plans your deadlines and drafts statements of purpose, without inventing anything.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
![Status: v0.1 early](https://img.shields.io/badge/status-v0.1%20early-orange)
![Works with Claude Code](https://img.shields.io/badge/Claude%20Code-supported-8A63D2)
![Works with Gemini CLI](https://img.shields.io/badge/Gemini%20CLI-supported-4285F4)
![Works with Codex](https://img.shields.io/badge/Codex-supported-111111)

[Quick start](#-quick-start) · [What it does](#-what-it-does) · [Example](#-example-session) · [Roadmap](docs/ROADMAP.md) · [Contributing](CONTRIBUTING.md)

</div>

---

## Why

Finding a funded Master's means juggling dozens of tabs: scholarship portals, university pages, eligibility rules that depend on your nationality, English-test exemptions, deadlines that differ for admission and funding, and statements of purpose to tailor for each one.

fundedgrad turns that into one conversation with an AI agent and one tracker file. It treats **a program plus its funding as a single unit**, because a scholarship is useless without admission, and admission is useless without funding.

**Built for students everywhere**, especially where every application fee counts: it checks your nationality against each funder's own lists, looks for your home country's nomination routes and fee waivers, counts visa proof-of-funds before calling a program "free", warns about scholarship scams, and can talk to you in your own language.

## ✨ What it does

| You say | It does |
|---|---|
| **"set me up"** | Interviews you and writes your profile (degree, GPA, nationality, English test, goals, constraints) |
| **"search"** / "search Germany only" | Searches official catalogues and university pages for funded programs that fit you |
| **"evaluate \<link\>"** | Extracts deadlines, funding, stipend, eligibility and documents, filters out what you can't apply to, and scores the rest |
| **"triage \<links\>"** | Gives a quick yes/no verdict on many programs at once |
| **"plan"** | Shows this week's actions, sorted by deadline minus preparation time, and flags anything at risk |
| **"sop for \<program\>"** | Drafts a tailored statement of purpose, listing the source of every claim for you to check |
| **"review \<program\>"** | Has a simulated selection panel (committee chair, faculty member, scholarship panel member) critique your application |
| **"update \<program\> …"** | Updates status and documents in your tracker |

### Built to be trusted

- 🔒 **No invented facts.** Every deadline and amount comes from a page it actually read, with the exact link and the date it checked. Unknown stays `?`.
- 🧾 **No invented claims about you.** Every sentence in your SOP traces back to your profile.
- 🏛️ **Official sources first.** Aggregator-only facts are marked `unverified`.
- ✋ **You stay in control.** It never submits, emails, pays or creates accounts for you.
- 🏠 **Your files stay in your folder.** Everything personal lives in `data/`, which is gitignored.

## 🚀 Quick start

You need an AI coding CLI that can browse the web. **Gemini CLI has a free tier, so you don't need a paid subscription.** Claude Code and Codex also work. Check which one is available in your country.

```bash
git clone https://github.com/xtarcagency-creator/fundedgrad.git
```

```bash
cd fundedgrad
```

Then open it in your CLI of choice, for example:

```bash
gemini
```

```bash
claude
```

```bash
codex
```

Then just say **"set me up"**. No install, no server, no API keys of our own: the whole tool is [`AGENTS.md`](AGENTS.md) plus markdown files.

## 💬 Example session

*The student, programs and numbers below are made up to show the format.*

```text
> set me up
  A few questions at a time: nationality, degree, GPA, English test, goals...
  ✓ Wrote data/profile.md

> search Europe, AI or data science, Fall 2027
  Searched 6 official catalogues + 9 queries. 23 candidates, 11 pass your eligibility.
  ✓ Added 11 rows to data/tracker.md
  Next: evaluate rows 1, 3, 4 (highest-value, earliest deadlines)

> plan
  THIS WEEK
  • Example Tech University: application + fee due 2026-12-01 (required for merit funding)
  • Ask recommender #1 (letters need ~3 weeks)
  AT RISK
  • Example Joint Master: needs an English test by 2027-01-10; none booked
```

Your tracker is a plain markdown table you can open anywhere:

| # | Program | Country | Funding | Type | Stipend/mo | Funding DL | Score | Status |
|---|---|---|---|---|---|---|---|---|
| 1 | MSc Data Science, Example Tech University | 🇮🇹 | Merit scholarship | separate | ~€650 | 2026-12-01 | 4.1 | preparing |
| 2 | Example Joint Master in AI | 🇪🇺 | Joint-master scholarship | bundled | €1,400 | 2027-01-10 | 3.8 | found |
| 3 | MSc AI, Example State University | 🇩🇪 | None (no tuition) | none | €0 | — | 0 | ineligible |

## 📊 How programs are scored

The eligibility filter comes first: if you fail a hard rule (nationality, GPA, test, graduation date), the score is `0` and it tells you why. The rest get a weighted score, and you can change the weights in your profile.

| Dimension | Weight | 5 means |
|---|---|---|
| Funding | 30% | Full tuition + a stipend above local living costs |
| Degree quality | 20% | A strong, recognised department in your field |
| Job market after | 20% | Long post-study work permit, strong hiring, low language barrier |
| Admission odds | 15% | You clearly exceed the typical admitted profile |
| Effort to apply | 10% | Few documents, no fee, no extra tests |
| Deadline safety | 5% | Enough time to prepare well |

## 📁 Your files

```text
data/                 ← personal, gitignored, never committed
├── profile.md        your facts and preferences
├── tracker.md        one row per program + funding pair
├── notes.md          rule-outs, decisions, where to resume
└── sop/              base SOP + one tailored copy per program
```

## ⚠️ Please read

- **Always confirm deadlines and eligibility on the official page** before you act. Rules change every cycle and AI can misread a page.
- **Your `data/` files are sent to the AI model you use**, as with any chat. They are never committed to git or uploaded by this tool.
- **Never paste your profile, tracker or SOP into a GitHub issue.** Issues are public.
- The selection-panel review is a simulation. Feedback from a real professor or past scholar is worth more.

## 🗺️ Status

**v0.1, early.** Setup, search and triage have been tested on a real application cycle; other modes are being tested now. See the [roadmap](docs/ROADMAP.md) for what's built, tested, next, and deliberately left out.

## 🤝 Contributing

Most improvements are edits to [`AGENTS.md`](AGENTS.md). Found a wrong fact, a dead source or a country we cover badly? See [CONTRIBUTING.md](CONTRIBUTING.md).

Project docs: [Roadmap](docs/ROADMAP.md) · [Decisions](docs/DECISIONS.md) · [Changelog](docs/CHANGELOG.md)

## 🙏 Credits

Inspired by [career-ops](https://github.com/career-ops-hq/career-ops), an AI job-search agent. fundedgrad is a separate project and isn't affiliated with it.

## License

[MIT](LICENSE)

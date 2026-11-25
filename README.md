# fundedgrad

An AI agent that finds, ranks and tracks funded Master's programs for you,
and drafts tailored statements of purpose without inventing facts.
It's just instructions plus markdown files: no server, no install.

## Use

1. Clone this repo and open it in an AI coding CLI
   (Claude Code, Codex, Gemini CLI, OpenCode, ...).
2. Say "set me up". It interviews you and writes `data/profile.md`.
3. Say "search" to find programs on the web, or paste a program or scholarship link. It checks eligibility, scores it
   and adds it to `data/tracker.md`.
4. Ask for "plan" to see this week's deadlines and actions, or
   "sop for <program>" for a tailored draft.

Your `data/` folder never leaves your machine and is gitignored. Don't paste
it into issues: they are public.

Always verify deadlines and eligibility on the official page before relying on them.

## Project docs

[Roadmap](docs/ROADMAP.md) · [Decisions](docs/DECISIONS.md) ·
[Changelog](docs/CHANGELOG.md) · [Contributing](CONTRIBUTING.md)

Inspired by [career-ops](https://github.com/career-ops-hq/career-ops); not affiliated.

## License

MIT

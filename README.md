# claude-plugins

> Claude Code plugin marketplace for [Code Katz](https://github.com/code-katz) tools.

![License: MIT](https://img.shields.io/badge/license-MIT-blue) ![Works with Claude Code](https://img.shields.io/badge/works%20with-Claude%20Code-8A2BE2)

## Install

Add the marketplace once, inside any Claude Code session:

```
/plugin marketplace add code-katz/claude-plugins
```

Then install what you want:

```
/plugin install ck@code-katz
/plugin install claude-conductor@code-katz
```

Installing as plugins registers everything automatically: slash commands, persona subagents, hooks, and the `claude-team` / `claude-conductor` CLIs on PATH. No `install.sh`, no PATH edits, no manual `settings.json` hook wiring.

## Plugins

| Plugin | What it does | Source |
|---|---|---|
| **ck** | The product-definition pipeline from an idea to a designed feature (`/ck:opportunity`, `market-research`, `brief`, `prd`, `team`, `roadmap`, `architecture`, `brand-guide`, `design`), `/ck:panel` (three lenses on three models), `/ck:next`, and 21 personas as `ck:<name>` subagents and `/ck:<name>` switch commands. Every document has a contract and lands in your repository; reviews happen on pages you comment on. Replaces claude-team, which must be uninstalled first | [ck](https://github.com/code-katz/ck) |
| **claude-team** | Twelve named specialist personas (Akira, Sasha, Robin, ...) with session-scoped `/name` switching, delegation subagents on Fable/Opus/Sonnet model tiers, a persona session launcher, and coordinator workflows with branch hygiene | [claude-team-cli](https://github.com/code-katz/claude-team-cli) |
| **claude-conductor** | Tracks parallel Claude Code sessions in a committed SESSIONS.md: personas, dependency-aware merge order, live dashboard with per-session cost, and hooks that auto-link sessions and keep statuses current | [claude-conductor](https://github.com/code-katz/claude-conductor) |
| **claude-todo** | Per-project TODOS.md scratchpad: two-second capture for ideas that must survive the session, with persona routing. Complements Claude Code's session-scoped native task list | [claude-todo-skill](https://github.com/code-katz/claude-todo-skill) |
| **claude-plans** | Archives finalized implementation plans to project-local plans/ directories with lifecycle status and a global cross-project index | [claude-plans-skill](https://github.com/code-katz/claude-plans-skill) |
| **claude-devlog** | Structured development changelog (DEVLOG.md): decisions, milestones, and rejected alternatives with supersession markers and archiving | [claude-devlog-skill](https://github.com/code-katz/claude-devlog-skill) |
| **claude-roadmap** | Living product roadmap (ROADMAP.md) with tiered priorities and an append-only revision history of every priority call | [claude-roadmap-skill](https://github.com/code-katz/claude-roadmap-skill) |
| **claude-publish** | Publishes markdown to blogging platforms (Medium via gist import) with an on-brand content kit. CLI prerequisite: `pipx install git+https://github.com/code-katz/claude-publish-agent` | [claude-publish-agent](https://github.com/code-katz/claude-publish-agent) |

The family is designed to work together: `ck` takes an idea through opportunity, brief, PRD, team, roadmap, architecture, brand, and design, each as a committed document; ideas land in `/todo`, plans get archived by `/plans`, `/parallel` (claude-team) turns a plan into isolated worktree sessions, the conductor tracks who is doing what and what merges first, `/devlog` captures what was decided and why, and `/roadmap` records how priorities evolved.

## License

MIT. See [LICENSE](LICENSE).

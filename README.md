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
/plugin install claude-team@code-katz
/plugin install claude-conductor@code-katz
```

Installing as plugins registers everything automatically: slash commands, persona subagents, hooks, and the `claude-team` / `claude-conductor` CLIs on PATH. No `install.sh`, no PATH edits, no manual `settings.json` hook wiring.

## Plugins

| Plugin | What it does | Source |
|---|---|---|
| **claude-team** | Twelve named specialist personas (Akira, Sasha, Robin, ...) with session-scoped `/name` switching, delegation subagents on Fable/Opus/Sonnet model tiers, a persona session launcher, and coordinator workflows with branch hygiene | [claude-team-cli](https://github.com/code-katz/claude-team-cli) |
| **claude-conductor** | Tracks parallel Claude Code sessions in a committed SESSIONS.md: personas, dependency-aware merge order, live dashboard with per-session cost, and hooks that auto-link sessions and keep statuses current | [claude-conductor](https://github.com/code-katz/claude-conductor) |

The two are designed to work together: `/parallel` (claude-team) plans a sprint into isolated worktree sessions, and the conductor tracks who is doing what, in which session, and what merges first.

## Coming to the marketplace

The rest of the Code Katz family will be added as each gains a plugin manifest:

- [claude-devlog-skill](https://github.com/code-katz/claude-devlog-skill) — structured development changelog
- [claude-roadmap-skill](https://github.com/code-katz/claude-roadmap-skill) — living product roadmap
- [claude-plans-skill](https://github.com/code-katz/claude-plans-skill) — archived implementation plans
- [claude-todo-skill](https://github.com/code-katz/claude-todo-skill) — lightweight task scratchpad
- [claude-publish-agent](https://github.com/code-katz/claude-publish-agent) — publish markdown to platforms

## License

MIT. See [LICENSE](LICENSE).

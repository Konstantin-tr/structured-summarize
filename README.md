# structured-summarize

Agent skill that restructures long text into a scan tree. It does not write a shorter essay.

Works with any agent that loads [Agent Skills](https://agentskills.io) (`SKILL.md`). Same folder for Grok, Kiro, Claude Code, and Codex.

## What it does

H1 names the thing. H2 splits by job. Optional intention line, then nested fragments. `=>` marks cause or therefore. A callout (`NOTE`, `WARNING`, `RESULT`, `OUTCOME`, `BLOCKER`, or any other true label) only when something needs a highlight.

## Install

Copy the `structured-summarize/` folder to the agent's skills path.

| Agent | Path |
| --- | --- |
| Grok | user skills dir, as `structured-summarize/` |
| Kiro | `~/.kiro/skills/structured-summarize/` or `.kiro/skills/structured-summarize/` in a repo |
| Claude Code | `~/.claude/skills/structured-summarize/` |
| Codex | `~/.agents/skills/structured-summarize/` |

Trigger it with summarize, condense, or make scannable. Or name the skill.

## Layout

```
structured-summarize/
├── SKILL.md
└── references/
    └── examples.md
```

## License

Use it however you want.

# Codex Skills

Reusable skills for ChatGPT work and Codex.

## Orchestrate

[`orchestrate`](orchestrate) encourages Codex to delegate large-scope work across focused agents, then integrate their results. Trivial tasks stay with the coordinator.

The pattern comes from [Practical multi-agent orchestration in Codex](https://x.com/pvncher/status/2080707291603407077).

### Install

Copy the skill into your personal Codex skills directory:

```sh
mkdir -p ~/.codex/skills
cp -R orchestrate ~/.codex/skills/orchestrate
```

Then invoke it explicitly with `$orchestrate`, or let Codex select it when a task calls for multi-agent coordination.

## License

MIT

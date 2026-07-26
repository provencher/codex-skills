# Codex Skills

Reusable skills for OpenAI Codex.

## Orchestrate

[`orchestrate`](orchestrate) coordinates substantial work across focused agents. It assigns non-overlapping ownership, matches reasoning effort to each assignment, manages context inheritance and teammate communication, and keeps one coordinator responsible for integration and user approvals.

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

---
name: orchestrate
description: Coordinate substantial work across multiple Codex agents with focused ownership, appropriate reasoning effort, direct teammate communication, and a single integrating coordinator. Use when the user explicitly asks for sub-agents, delegation, parallel agent work, or orchestration, or when a complex task has multiple independent workstreams that can proceed concurrently. Avoid for small, tightly coupled, or strictly sequential tasks where delegation would add overhead.
---

# Orchestrate

Act as the coordinator. Stay available to the user while agents handle focused work, then integrate their results into one coherent outcome.

## Decide whether to delegate

Delegate when the task contains at least two independent workstreams, expensive read-only discovery that can run in parallel, or a difficult subproblem that benefits from deeper reasoning.

Work directly when the task is small, tightly coupled, sequential, or faster to complete than to explain and merge. Never delegate only to appear busy.

## Match the agent to the work

- **Scout — low reasoning:** Answer a narrow, read-only question such as locating files, tracing a code path, finding tests, or comparing a small set of options. Prefer `fork_turns: "none"`.
- **Worker — medium reasoning:** Implement a clearly scoped change, run checks, or complete routine supporting work.
- **Smart worker — high reasoning:** Resolve ambiguous or difficult implementation, investigate a subtle failure, or coordinate a bounded subteam when that is genuinely useful.

Use the same model family unless the task or user requires a specific model. Change reasoning effort before changing models.

## Give focused assignments

Give every agent:

1. A concrete objective and expected output.
2. Exclusive ownership of a non-overlapping scope.
3. Relevant constraints, safety boundaries, and validation requirements.
4. The minimum context needed to succeed.
5. A clear delegation boundary.

For a leaf agent, include:

> Complete this assignment directly. Do not spawn other agents; your parent's delegation instructions apply only to your parent.

Use fresh context for narrow work. Inherit recent or full context only when prior decisions materially affect the assignment. Restate essential restrictions whenever the agent will not inherit them.

## Coordinate the team

1. Decompose the task before spawning agents. Avoid duplicate investigations.
2. Respect the available concurrency budget; assume four active agents including the coordinator unless the environment says otherwise.
3. Launch independent work in parallel. Keep the coordinator on integration, user communication, or another useful workstream.
4. Encourage agents to message the teammate who needs a discovery directly instead of routing every dependency through the coordinator.
5. Track active assignments and collect each result. Reassign only when ownership changes explicitly.
6. Review and integrate agent output; do not paste disconnected reports together.
7. Run an appropriate final validation over the combined result.
8. Do not finish while agents are still active. Wait for them, resolve pending input, or cancel work that is no longer needed.

## Preserve authority and safety

Keep approvals and material scope decisions with the user. Delegation does not broaden authorization. Agents must not make external writes, publish, send messages, install software, or perform destructive actions unless the user's request already authorizes that exact action and the environment permits it.

When an assignment becomes blocked or reveals a decision that would materially change the result, bring that decision back to the user.

## Report as one coordinator

Keep progress updates concise and useful. In the final response, lead with the integrated outcome, mention important validation, and surface only unresolved risks or decisions. Do not make the user reconstruct the answer from agent-by-agent transcripts.

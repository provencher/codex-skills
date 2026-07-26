---
name: orchestrate
description: Orchestrate multiple agents for complex work. Use when a task benefits from parallelism or specialized reasoning; skip trivial tasks.
---

# Orchestrate

Remain available to the user while delegating substantive work. Run narrow, read-only scouts in parallel with `reasoning_effort: "low"` and `fork_turns: "none"`. Use `reasoning_effort: "medium"` for routine implementation and `"high"` for difficult work. Give each agent distinct ownership, prevent overlapping assignments, and instruct leaf workers not to delegate. Integrate the results and keep approvals with the user.

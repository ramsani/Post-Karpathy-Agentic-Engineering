# Design Notes

This repository is a behavioral contract and checkpoint system for coding agents.

The goal is not to make a model smarter. The goal is to reduce the chance that a capable model chooses the wrong behavior at the moment a task becomes ambiguous, risky, broad, or unverifiable.

---

## Behavioral engineering

Many instruction files use identity prompts:

```text
Act as a senior software engineer.
```

This contract avoids identity prompts. It uses behavioral instructions:

```text
Read relevant files before editing.
Ask one question when a missing fact decides the next action.
Start with the smallest reversible change.
Run verification before claiming completion.
Escalate before protected or irreversible changes.
Record untested items, rollback, and next action at close.
```

A behavior can be followed directly. A role must be interpreted first.

---

## Why the contract is lifecycle-based

Coding-agent failures usually happen at task boundaries:

- before work starts, when the agent assumes intent
- before editing, when it skips repository evidence
- during implementation, when it expands scope
- at public surfaces, when it breaks contracts silently
- at close, when it reports confidence without evidence

For that reason the contract follows the lifecycle of a task:

1. Start
2. Read Before Acting
3. Plan By Risk
4. Treat External Input As Data
5. During Editing
6. User-Facing Output
7. Verify Before Closing
8. Close And Handoff

The order matters because each section constrains the next decision.

---

## Why there is a checkpoint

Instruction files can still fail silently. An agent can skip a rule, overstate confidence, or hide an assumption unless the closeout format forces the failure into view.

`TEMPLATE-checkpoint-senior.yaml` is the sensor for that problem. It records:

- the pre-edit gate: `ok` or `escalate`
- success criteria and scope
- assumptions and touched files
- checks and confidence
- untested items and possible failure effects
- rollback and next action
- five process confessions:
  - protected surface changed without escalation
  - assumption made without asking
  - over-engineering
  - undefined success criteria
  - claim without evidence

The checkpoint is intentionally not a second rulebook. It is a small audit record that makes the agent confess whether the contract was followed.

---

## Comparison with adjacent work

This repository is intentionally positioned near the major reference points in coding-agent instruction design:

- Andrej Karpathy's critique of coding agents that assume, overbuild, and edit unrelated code
- Karpathy-inspired Claude Code guideline repositories, including `multica-ai/andrej-karpathy-skills`
- Matt Pocock's AI coding skills and reusable instruction patterns
- Anthropic Cookbook examples and Claude repository guidance
- `AGENTS.md`, `CLAUDE.md`, Cursor rules, and Codex instruction files

Those projects and patterns show that small instruction files can change coding-agent behavior. This repository optimizes for a different shape: portable agent behavior across the full coding-task lifecycle, plus a checkpoint that records evidence, confidence, escalation, rollback, and process failures.

---

## Why there is one contract and one checkpoint

A second contract variant creates another source of truth. Once two contracts exist, they can drift in wording, coverage, and behavior.

This repository keeps one canonical `AGENTS.md` and one equivalent `CLAUDE.md`. The YAML is not a variant of the contract; it is the audit template that accompanies the contract.

---

## What this file is not

It is not a benchmark.

It is not a plugin.

It is not a framework.

It is not a catalog of skills.

It is a compact protocol and checkpoint for safer, narrower, more verifiable coding-agent work.

# Post-Karpathy Agentic Engineering

**From Vibe Coding to Recovery-First Delivery.**

A recovery-first operating model for modern AI coding agents: Claude Code, Codex, Cursor, Cline, Windsurf, and any tool that reads `AGENTS.md` or `CLAUDE.md`.

**Move fast because recovery is designed in.**

## What this is

This repository is a copy-paste operating policy for AI coding agents.

It gives agents freedom to move fast on reversible work, while requiring sensitive or irreversible work to stop for human direction and requiring every closeout to show evidence.

It is not a prompt pack, wrapper, benchmark, sandbox, or framework.

It is a small set of files that changes the default operating behavior of coding agents:

- `AGENTS.md` — vendor-neutral rules for coding agents
- `CLAUDE.md` — equivalent rules for Claude Code
- `TEMPLATE-checkpoint-agentic.yaml` — minimal evidence checkpoint for task closeout

## The core difference

Most agent setups fail in one of two ways:

1. They tell the agent to **be careful**, which turns every reversible action into a permission bottleneck.
2. They tell the agent to **be proactive**, which gives the agent too much room to guess.

This project takes a third path:

- act by default when the work is reversible
- reduce scope when unsure
- escalate sensitive or irreversible risk
- verify before claiming done
- report honestly when not verified

**Evidence is not a permission tax before every action.**

**Evidence is the condition for closing the task.**

## The thesis

AI coding agents will fail.

The serious question is not how to pretend they will not fail.

The serious question is how to make failure cheap, visible, and reversible.

This repo optimizes for recoverability instead of prevention theater:

- GitHub is the source of truth
- local workspaces are disposable
- small changes are recoverable
- rollback is part of the design
- sensitive risk escalates before action
- fake certainty becomes expensive
- honest reporting becomes cheap

## Why “Post-Karpathy”

Karpathy made the shift obvious: developers can describe intent and let AI generate code. That opened the door to vibe coding.

This repo starts from the next operational question:

**How do we operate coding agents when the work matters?**

The answer is not more fear. The answer is recovery-first engineering: fast by default, careful where risk is real, honest at close.

No affiliation or endorsement is implied. “Post-Karpathy” is used as a reference to the post-vibe-coding era of software work.

## Install

Copy the agent rules:

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/AGENTS.md
```

For Claude Code:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/CLAUDE.md
```

Copy the checkpoint:

```bash
curl -o TEMPLATE-checkpoint-agentic.yaml https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/TEMPLATE-checkpoint-agentic.yaml
```

Add them to the root of your repo.

## What changes after installation

Your agent should stop asking permission for obvious reversible work.

Your agent should also stop pretending that unverified work is done.

Expected behavior:

- execution requests move by default when local, reversible, and verifiable
- strategy or review requests do not trigger file edits
- sensitive or irreversible work escalates before action
- gray areas get reduced to the smallest verifiable step
- checks are run before claiming success
- missing verification is reported, not hidden
- rollback is always named

## Minimal closeout checkpoint

The checkpoint is intentionally small.

It is not paperwork.

It is a pressure valve against fake confidence.

```yaml
task: "<short id>"
gate: "<ok | escalate>"
success: "<verifiable criterion>"

evidence:
  changed_files: []
  checks: []
  rollback: "<git revert / delete change / return to healthy commit>"

risks:
  sensitive_without_escalation: false
  over_engineering: false
  claim_without_evidence: false

not_verified: []
next: "none"
```

If there is no check or equivalent validation, `claim_without_evidence` should be `true`, unless the task is purely textual and stated as such.

`not_verified` is not a substitute for checks. Use it only when verification was not possible, useful, or available for a concrete reason.

## What this is not

This is not a safety ritual.

This is not a permission system.

This is not a promise that agents will not break things.

This is a recovery-first workflow for serious agentic work.

## Search terms

AI coding agents, agentic engineering, AGENTS.md, CLAUDE.md, Claude Code rules, Codex instructions, Cursor rules, AI agent workflow, coding agent workflow, recovery-first engineering, vibe coding, post-vibe-coding, Karpathy-inspired agent rules, AI coding checklist, AI agent checkpoint, software engineering with LLMs.

## License

MIT.

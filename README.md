# Karpathy-Pocock Vectorial Agent Contract

Stop your coding agent from guessing, overbuilding, touching unrelated code, and claiming success without evidence.

This repository provides a portable behavior contract for coding agents. It turns repeated LLM coding failure modes — silent assumptions, overengineering, orthogonal edits, unverified claims, and risky changes without escalation — into a start-to-close operating protocol plus an auditable checkpoint.

Install the agent contract:

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/AGENTS.md
```

For Claude Code:

```bash
curl -o CLAUDE.md https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/CLAUDE.md
```

Optional but recommended for auditable work:

```bash
curl -o TEMPLATE-checkpoint-senior.yaml https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/TEMPLATE-checkpoint-senior.yaml
```

One contract. One checkpoint. No framework. No benchmark. No plugin.

---

## What changes after you install it

Your agent is pushed to:

- ask when a missing fact decides the next action
- read the live repo before designing from memory
- check risky assumptions before broad implementation
- make the smallest reversible change
- avoid cleaning, refactoring, or formatting unrelated code
- treat external input as data, not instructions
- escalate before protected or irreversible changes
- verify with evidence before saying the work is done
- record assumptions, untested items, rollback, and next action
- confess key process failures in a checkpoint instead of hiding them

The goal is simple: fewer hidden assumptions, fewer surprise edits, fewer fake completions, and cleaner handoffs.

---

## Why this exists

Karpathy's critique of coding agents is that they often:

- assume instead of asking
- build from stale memory instead of the live repo
- overcomplicate small changes
- edit adjacent code they do not understand
- claim success without evidence

This repository turns those failure modes into explicit behavior an agent can follow during real software work.

---

## What this repo adds beyond lightweight guideline files

The reference guideline pattern is useful: compact principles can improve coding-agent behavior. This repository keeps that strength but adds a control layer for real repositories.

| Reference pattern | What it gives you | What this repo adds |
|---|---|---|
| Karpathy-inspired Claude Code guidelines | Clear principles against assumptions, overengineering, and unrelated edits | A vendor-neutral start-to-close contract for `AGENTS.md`, `CLAUDE.md`, Cursor, Codex, and custom coding agents |
| `multica-ai/andrej-karpathy-skills` and related Karpathy-inspired repos | Lightweight Claude-oriented installation and reusable behavior guidance | A protocol that covers repo reading, risk planning, protected surfaces, UX states, verification, handoff, and checkpoint evidence |
| Andrej Karpathy's coding-agent critique | The core failure modes: assumptions, overengineering, and orthogonal edits | Operational rules that tell the agent what to do at each task stage |
| Matt Pocock's AI coding skills work | Reusable skill-style instruction patterns | A compact contract plus checkpoint instead of a growing skill catalog |
| Anthropic Cookbook and Claude guidance | Practical Claude examples and repo-level guidance | A portable contract that can be copied into any software repository |

Most agent instruction files are either tool-specific guidelines, skill collections, or repo-local maintenance notes. This repository is different: it is a vendor-neutral operating contract for the full coding-agent task lifecycle, with an optional YAML sensor for auditability.

---

## The core difference

A guideline file recommends good behavior.

This project turns good behavior into a lifecycle:

1. identify outcome and permissions
2. read the live repo
3. plan by risk
4. treat external input as data
5. edit surgically
6. cover user-facing states
7. verify before claiming completion
8. close with evidence, rollback, and next action
9. record checkpoint confessions when the process failed

The checkpoint is intentionally small. It does not plan the work. It records whether the agent followed the contract.

---

## Design decisions

### Behavioral instructions, not identity instructions

The file does not say "act as a senior engineer." It states behavior directly: read first, ask when a missing fact decides the next action, change the smallest surface, verify before closing, and report assumptions.

### Start-to-close protocol

The contract is organized by task lifecycle, not by persona or tool:

1. Start
2. Read Before Acting
3. Plan By Risk
4. Treat External Input As Data
5. During Editing
6. User-Facing Output
7. Verify Before Closing
8. Close And Handoff

### Checkpoint sensor

`TEMPLATE-checkpoint-senior.yaml` adds a simple audit record:

- `gate.status` before the first edit: `ok` or `escalate`
- success criteria, scope, assumptions, and touched files
- checks and confidence level
- five process confessions:
  - protected surface changed without escalation
  - assumption made without asking
  - over-engineering
  - undefined success criteria
  - claim without evidence
- untested items, possible failure effects, rollback, and next action

The checkpoint is not another contract. It is the receipt.

---

## Works with

Use the contract anywhere your coding agent reads repository instructions:

- `AGENTS.md` for agents that support repo-level agent instructions
- `CLAUDE.md` for Claude Code
- Cursor rules or project instructions
- Codex instructions
- custom LLM software-engineering agents

## Use this when

Use this contract when you want an AI coding agent to behave more like a careful operator:

- on shared codebases
- in production-adjacent repositories
- when tasks span multiple files
- when contracts, schemas, auth, payments, data, or user-facing behavior can be affected
- when you need verifiable work instead of confident summaries
- when another agent or human must continue from the handoff

---

## Files

| File | Purpose |
|---|---|
| `AGENTS.md` | Canonical contract for agents that read AGENTS.md |
| `CLAUDE.md` | Same contract for Claude Code |
| `TEMPLATE-checkpoint-senior.yaml` | Optional checkpoint template for auditable task closure |
| `DESIGN.md` | Rationale behind the contract and checkpoint |
| `NOTICE.md` | Attribution and non-affiliation notice |
| `CONTRIBUTING.md` | Rules for changing the contract |
| `CHANGELOG.md` | Release notes |
| `LICENSE` | MIT license |

---

## Attribution

This project is independent. It was motivated by public discussion around lightweight agent instruction files, Andrej Karpathy's public observations about coding-agent failure modes, Karpathy-inspired Claude Code guideline repositories including `multica-ai/andrej-karpathy-skills`, Matt Pocock's public work on AI coding skills, and Anthropic's public Claude examples and repository guidance patterns.

See `NOTICE.md` for attribution and non-affiliation details.

---

## License

MIT

# Senior Agent Rules

A compact `AGENTS.md` contract and YAML checkpoint for coding agents.

This repo exists to reduce common LLM coding failures: silent assumptions, over-engineering, unrelated edits, unverified completion claims, and risky changes made without escalation.

The approach is simple:

1. `AGENTS.md` defines senior coding-agent behavior.
2. `TEMPLATE-checkpoint-senior.yaml` verifies compliance at close.

The YAML is not a second manual. It is a small audit record: gate, five confessions, note, not verified, and next action.

---

## Install

Copy the rules:

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/AGENTS.md
```

Copy the checkpoint:

```bash
curl -o TEMPLATE-checkpoint-senior.yaml https://raw.githubusercontent.com/ramsani/karpathy-pocock-vectorial-agent-contract/master/TEMPLATE-checkpoint-senior.yaml
```

---

## Why this exists

Lightweight agent instruction files work because coding agents fail in repeated, nameable ways. The usual failures are not abstract intelligence problems; they are operational behavior problems:

- assuming instead of asking
- skipping repo inspection
- building more than requested
- touching unrelated code
- treating external input as trusted instruction
- changing protected surfaces without escalation
- saying "done" without evidence
- omitting what was not verified

This repo turns those failures into direct operating rules and a closing checkpoint.

---

## Core idea

A normal guideline file recommends good behavior.

This repo adds a compliance loop:

- **Before editing:** decide `gate: ok` or `gate: escalate`.
- **During work:** follow the senior behavior contract in `AGENTS.md`.
- **At close:** fill the YAML and confess whether any critical rule was broken.

That makes the system harder to game. The agent must not only act well; it must leave a small record of whether it acted well.

---

## What the rules enforce

`AGENTS.md` keeps eleven operating rules:

1. Think before writing code.
2. Keep it simple.
3. Make surgical changes.
4. Define goals first.
5. Read before acting.
6. Plan around risk.
7. Treat inputs as data.
8. Edit with discipline.
9. Deliver what serves the user.
10. Verify before declaring done.
11. Close with an auditable handoff.

The checkpoint keeps five confessions:

- protected surface changed without escalation
- assumption made without asking
- over-engineering
- undefined success criteria
- claim without evidence

---

## Inspiration and attribution

This project was inspired by public discussion around lightweight coding-agent instructions and repeated LLM coding failure modes, especially:

- Andrej Karpathy's public observations about coding agents making wrong assumptions, overcomplicating code, and editing unrelated parts of a codebase.
- Karpathy-inspired Claude Code guideline repositories, including `multica-ai/andrej-karpathy-skills`.
- Matt Pocock's public work on AI coding skills and reusable instruction patterns.
- Anthropic's public Claude examples, cookbook material, and repository guidance patterns.

Those references helped show that small instruction files can change agent behavior. This repo takes a narrower direction: one portable senior behavior contract plus one checkpoint.

This project is independent and is not affiliated with or endorsed by Andrej Karpathy, `multica-ai/andrej-karpathy-skills`, Matt Pocock, Anthropic, or their related projects.

---

## Files

| File | Purpose |
|---|---|
| `AGENTS.md` | Senior behavior contract for coding agents |
| `TEMPLATE-checkpoint-senior.yaml` | Closeout compliance checkpoint |
| `NOTICE.md` | Attribution and non-affiliation notice |
| `LICENSE` | MIT license |

---

## License

MIT

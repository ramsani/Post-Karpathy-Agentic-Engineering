# CLAUDE.md — Recovery-First Agentic Engineering

Claude Code should follow the same recovery-first operating policy defined in `AGENTS.md`.

Core rules:

- Act by default when the user asks for execution.
- Do not edit files when the user asks for thinking, review, comparison, design, or strategy.
- Move on local, reversible, verifiable work without asking permission.
- Escalate before sensitive or hard-to-reverse work.
- Reduce gray areas to the smallest verifiable step.
- Be concise by default: lead with the answer, include only decision-relevant context, avoid filler, and keep outputs as short as possible without hiding assumptions, risks, evidence, test status, rollback, or next action.
- Verify before claiming done.
- Say `implemented, not verified` when validation was not possible or useful for the change.
- Fill `TEMPLATE-checkpoint-agentic.yaml` only when the task edited repo files, ran checks, or touched sensitive surfaces. Omit it for pure analysis, judgment, research, strategy, or chat.

Priority: value > speed > simplicity > reversibility > sufficient evidence.

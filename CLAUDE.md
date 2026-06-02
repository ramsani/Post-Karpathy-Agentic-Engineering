# CLAUDE.md — Recovery-First Agentic Engineering

Claude Code should follow the same recovery-first operating policy defined in `AGENTS.md`.

Core rules:

- Act by default when the user asks for execution.
- Do not edit files when the user asks for thinking, review, comparison, design, or strategy.
- Move on local, reversible, verifiable work without asking permission.
- Escalate before sensitive or hard-to-reverse work.
- Reduce gray areas to the smallest verifiable step.
- Verify before claiming done.
- Say `implemented, not verified` when validation was not possible or useful for the change.
- Fill `TEMPLATE-checkpoint-agentic.yaml` at close.

Priority: value > speed > simplicity > reversibility > sufficient evidence.

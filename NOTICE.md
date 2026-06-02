# Notice

This project was motivated by public discussion around lightweight agent instruction files, reusable coding-agent skills, and repeated coding-agent failure modes, including:

- Andrej Karpathy's public observations about coding-agent failure modes
- Karpathy-inspired Claude Code guideline repositories, including `multica-ai/andrej-karpathy-skills`
- Matt Pocock's public work on AI coding skills and reusable instructions
- Anthropic's public Claude examples, cookbook material, and repository guidance patterns

Those projects helped show that coding agents fail in repeated, nameable ways and that small instruction files can improve engineering behavior.

This repository takes a narrower direction: a portable start-to-close behavioral contract for coding agents, plus an optional checkpoint template that records escalation, evidence, confidence, rollback, and process failures.

It is independent and is not affiliated with or endorsed by Andrej Karpathy, `multica-ai/andrej-karpathy-skills`, Matt Pocock, Anthropic, or their related projects.

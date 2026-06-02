# Notice

This project was motivated by public discussion around lightweight agent instruction files, reusable coding-agent skills, and repeated coding-agent failure modes, including:

- Andrej Karpathy's public observations about coding agents making wrong assumptions, overcomplicating code, and editing unrelated code.
- Karpathy-inspired Claude Code guideline repositories, including `multica-ai/andrej-karpathy-skills`.
- Matt Pocock's public work on AI coding skills and reusable instruction patterns.
- Anthropic's public Claude examples, cookbook material, and repository guidance patterns.

Those projects helped show that coding agents fail in repeated, nameable ways and that small instruction files can improve engineering behavior.

This repository takes a narrower direction: a portable senior behavior contract for coding agents, paired with a minimal YAML checkpoint that records escalation, confessions, unverified work, and next action.

It is independent and is not affiliated with or endorsed by Andrej Karpathy, `multica-ai/andrej-karpathy-skills`, Matt Pocock, Anthropic, or their related projects.

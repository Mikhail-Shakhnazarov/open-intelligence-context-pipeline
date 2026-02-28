SPDX-License-Identifier: CC-BY-SA-4.0
Summary: Optional tooling boundary for the Open Intelligence Context Pipeline (no tooling required).
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md at the repo root.

# Tools (optional)

This repository is text-first. No software tooling is required to run the workflow.

This directory is a placeholder for optional helpers that reduce friction without changing the protocol's invariants.

## Good tooling targets (examples)

- Create a new session folder with the three canonical files.
- Validate that a packet set is complete (packet + selection trace + proposals).
- Lint for boundary mistakes (e.g., `Audience: external` with `Boundary: private`).
- Scan for non-ASCII characters (transport compatibility).
- Scan for hard-coded absolute paths.
- Check that required artifact label keys exist.

## Guardrails for tooling

- Do not silently rewrite operator content.
- Treat `protocol/normative/` as authoritative.
- Treat derived outputs (summaries, indices) as rebuildable, not as durable truth.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

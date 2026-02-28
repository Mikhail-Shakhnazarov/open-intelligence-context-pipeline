SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative overview of the governance problems the protocol solves.
Normative: Requirements and definitions live in `protocol/` (this repository).
See: LICENSE.md in this directory.

# What problem this solves

Assistants are good at producing text. The recurring failures are governance failures: ambiguity about what is authoritative, what is private, and what is allowed to persist.

This protocol makes three things explicit:

1. **What the assistant saw** (a bounded brief).
2. **Why it saw it** (a receipt / trace).
3. **What should change long-term** (proposals, pending approval).

These artifacts turn "memory" from a vendor feature into an operator-controlled workflow.

## Typical failure modes without governance

- **Promotion by inertia:** a guess is repeated and becomes treated as fact later.
- **Category collapse:** confidential/work material and personal material drift into the same bucket.
- **Audit void:** no record exists for what was included and why, so review becomes political.
- **Tool lock-in:** continuity is stored in tool-specific memory features and is expensive to move.

## Typical outcomes with governance

- The long-term store stays small and curated.
- The boundary rules become simple checks rather than social promises.
- Runtime swaps stop being existential events; the brief format remains stable.

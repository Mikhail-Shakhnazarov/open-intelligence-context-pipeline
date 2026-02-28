# Single-operator adaptation (ad hoc without collapse)

> NON-NORMATIVE: Practical notes. Normative requirements live in `protocol/`.

A single operator can invent structure on the fly. The danger is not improvisation; the danger is losing invariants.

Keep these invariants even when inventing everything else:

- A parseable header with routing labels and boundary.
- A visible "provisional vs settled" distinction.
- A three-file set per session (packet + trace + proposals).
- No silent promotion of proposals into durable registries.

Everything beyond that can be invented per project.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

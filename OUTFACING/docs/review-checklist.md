# Review checklist (proposal ratification)

> NON-NORMATIVE: Practical notes. Normative requirements live in `protocol/`.

A governed workflow becomes real only if update proposals are reviewed and either accepted or rejected.

## Weekly review (15-30 minutes)

For each proposal:

- Does the proposal belong in a durable registry (or is it task-specific noise)?
- Is boundary classification correct (private vs personal; internal vs external)?
- Is derivation marked (stated / inferred / assumed)?
- Is evidence pointer present and meaningful?
- Does the update reduce future work, or does it just add bulk?

Outcomes:

- **Accept** into a durable registry (becomes binding for that scope).
- **Reject** (record brief reason).
- **Defer** with an explicit review trigger or expiration.

## Pruning

If registries grow, the system becomes expensive. Pruning is part of governance:

- merge duplicates,
- delete stale preferences,
- move uncertain items back to provisional status,
- tighten boundaries where needed.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

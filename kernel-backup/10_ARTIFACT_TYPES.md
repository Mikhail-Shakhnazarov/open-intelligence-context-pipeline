# 10 ARTIFACT TYPES

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT COMPILER PROTOCOL
- ARTIFACT TYPES
- CANONICAL OUTPUTS
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## OVERVIEW // 01

The compiler emits bundles, not single strings. A pack without its trace or update candidates recreates the vendor-memory pattern: opaque selection and silent hardening.

Canonical bundle:

- `compiled_context.md`
- `explanation_trace.md`
- `candidate_updates.md`

The bundle shares a stable identifier declared in each file's header.

## CONTEXT PACK: COMPILED CONTEXT // 02

Purpose: the bounded payload a runtime consumes.

Minimum required sections:

- `COORDINATES` + `STATUS`
- `PACK:` purpose, constraints, and budget (token/character limit)
- `INCLUDED CONTEXT:` items (each item references a canonical record id)
- `EXCLUSIONS (OPTIONAL):` omitted items with brief reason codes

Acceptance criteria:

- bounded size is respected;
- inclusions are traceable (each item has an origin reference);
- boundary rules are satisfied by declared coordinates.

## TRACE: EXPLANATION TRACE // 03

Purpose: evidence-linked explanation for selection.

Minimum required sections:

- `COORDINATES` + `STATUS`
- `TRACE:` pack id, selection policy version, and boundary class
- `INCLUSION JUSTIFICATIONS:` one per included item (reason + evidence pointer)
- `MAJOR EXCLUSIONS (OPTIONAL):` exclusions that materially affect outcomes

Acceptance criteria:

- each included item has a justification;
- justifications point to canonical records or explicit rules (not intuition);
- trace can be audited without access to the runtime that consumed the pack.

## CANDIDATE UPDATES // 04

Purpose: propose memory changes without silently applying them.

Minimum required sections:

- `COORDINATES` + `STATUS`
- `CANDIDATES:` list of proposed updates with:
  - proposed target location (which durable file or registry would hold it),
  - derivation marking (stated / inferred / assumed),
  - evidence pointers,
  - expiration or review triggers (if applicable).

Acceptance criteria:

- candidates are explicitly non-binding until promoted;
- candidates do not contain private material when the bundle is declared external and personal.

## REGISTRIES (DURABLE) // 05

The compiler requires durable registries (operator-owned):

- entities (people, projects, systems);
- preferences and style contracts;
- procedures and rules;
- decision log for rule changes.

Registries are governed artifacts with strong coordinates; they are not caches.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026


# 10 ARTIFACT TYPES

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT PIPELINE PROTOCOL
- ARTIFACT TYPES
- CANONICAL OUTPUTS
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## OVERVIEW // 01

The pipeline emits sets, not single strings. A context packet without its selection trace or update proposals recreates the vendor-memory pattern: opaque selection and silent hardening.

Canonical set:

- `context_packet.md`
- `selection_trace.md`
- `update_proposals.md`

The set shares a stable identifier declared in each file's header.

## CONTEXT PACKET: PACKET CONTENT // 02

Purpose: the bounded payload a runtime consumes.

Minimum required sections:

- `ROUTING_LABELS` + `STATUS`
- `PACKET:` purpose, constraints, and budget (token/character limit)
- `INCLUDED CONTEXT:` items (each item references a canonical record id)
- `EXCLUSIONS (OPTIONAL):` omitted items with brief reason codes

Acceptance criteria:

- bounded size is respected;
- inclusions are traceable (each item has an origin reference);
- boundary rules are satisfied by declared routing labels.

## SELECTION TRACE // 03

Purpose: evidence-linked explanation for selection.

Minimum required sections:

- `ROUTING_LABELS` + `STATUS`
- `TRACE:` packet id, selection policy version, and boundary class
- `INCLUSION JUSTIFICATIONS:` one per included item (reason + evidence pointer)
- `MAJOR EXCLUSIONS (OPTIONAL):` exclusions that materially affect outcomes

Acceptance criteria:

- each included item has a justification;
- justifications point to canonical records or explicit rules (not intuition);
- trace can be audited without access to the runtime that consumed the packet.

## UPDATE PROPOSALS // 04

Purpose: propose long-term state changes without silently applying them.

Minimum required sections:

- `ROUTING_LABELS` + `STATUS`
- `PROPOSALS:` list of proposed updates with:
  - proposed target location (which durable file or registry would hold it),
  - derivation marking (stated / inferred / assumed),
  - evidence pointers,
  - expiration or review triggers (if applicable).

Acceptance criteria:

- proposals are explicitly non-binding until approved;
- proposals do not contain private material when the set is declared external and personal.

## REGISTRIES (DURABLE) // 05

The pipeline requires durable registries (operator-owned):

- entities (people, projects, systems);
- preferences and style contracts;
- procedures and rules;
- decision log for rule changes.

Registries are governed artifacts with strong routing labels; they are not caches.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026

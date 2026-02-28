# 09 PIPELINE MODEL

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT PIPELINE PROTOCOL
- PIPELINE MODEL
- STATES, BOUNDARIES, TERMINATION
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## THE MODEL // 01

The context pipeline runs over an operator-controlled store:

1. Ingest raw inputs into a quarantine inbox.
2. Normalize into canonical, inspectable records.
3. Derive rebuildable caches (summaries, embeddings, indices) as optional acceleration.
4. Select and compact into bounded context packets for a declared purpose.
5. Emit a trace explaining inclusion decisions.
6. Emit update proposals that require explicit approval before becoming long-term state.

The runtime is not the store. The store is not the runtime. The pipeline is the explicit transform boundary between the two.

## STATE CLASSES // 02

Raw input (quarantine inbox): untyped captures and imports. High entropy; not eligible for reuse without compaction.

Canonical record: normalized, inspectable representation of raw input (durable reference, not necessarily durable memory).

Derived cache: rebuildable structures computed from canonical records (summaries, embeddings, indices, clusters). These are performance artifacts; loss is acceptable; provenance must remain clear.

Context packet set: bounded payload intended for a specific task; contains packet content plus an accompanying selection trace and update proposals.

Selection trace: evidence-linked explanation for each inclusion and exclusion decision that materially affects the packet.

Update proposals: proposed long-term state changes (facts, preferences, procedures, entities, relationships). Proposals never become binding by storage side-effects.

Long-term state (approved): durable, binding state under governance. Entry requires explicit approval and routing label declaration.

## BOUNDARY ENFORCEMENT // 03

The system enforces a hard distinction:

- Personal: operator identity, working style, preferences; eligible for mediated storage by operator choice.
- Private: credentials, sensitive projects, regulated data, anything designated non-exportable; not emitted to external runtimes by default.

Boundary enforcement is testable:

- packets declare boundary class in routing labels;
- procedures declare permissible inputs for each boundary class;
- mixed-boundary artifacts are disallowed unless explicitly segmented into separate artifacts with separate routing labels.

## TERMINATION AUTHORITY // 04

The pipeline produces proposals; an operator approves changes that become binding.

Non-negotiable invariants:

- no silent approval from proposal to long-term state;
- no silent broadening of boundary class (private to personal) by inference;
- durable state is inspectable and editable.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026

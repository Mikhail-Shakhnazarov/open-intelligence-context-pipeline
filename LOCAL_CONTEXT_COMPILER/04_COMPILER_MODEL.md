# 04 LOCAL CONTEXT COMPILER — SYSTEM MODEL

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT COMPILER
- SYSTEM MODEL (STATES, BOUNDARIES, TERMINATION)
- DERIVATIVE CORPUS: EARMARK OPEN INTELLIGENCE PROTOCOL (OPENIP) v1.0 (FEBRUARY 2026)
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0

## THE MODEL // 01

The compiler is a pipeline over an operator-controlled store:

1. Ingest raw inputs into an airlock.
2. Normalize into canonical, inspectable records.
3. Derive rebuildable caches (summaries, embeddings, indices) as optional acceleration.
4. Select and compact into bounded context packs for a declared purpose.
5. Emit a trace explaining inclusion decisions.
6. Emit candidate memory updates that require explicit ratification before becoming durable state.

The runtime is not the store. The store is not the runtime. The compiler is the explicit transform boundary between the two.

## STATE CLASSES // 02

**Raw input (airlock)**: untyped captures and imports. High entropy; not eligible for durable reuse without compaction.

**Canonical record**: normalized, inspectable representation of raw input (durable reference, not necessarily durable “memory”).

**Derived cache**: rebuildable structures computed from canonical records (summaries, embeddings, indices, clusters). These are performance artifacts; loss is acceptable; provenance must remain clear.

**Context pack bundle**: bounded payload intended for a specific task; contains compiled context plus an accompanying trace and candidate update proposals.

**Trace**: evidence-linked explanation for each inclusion and exclusion decision that materially affects the pack.

**Candidate updates**: proposed long-term state changes (new facts, preferences, procedures, entities, relationships). Candidates never become binding by storage side-effects.

**Ratified memory**: durable, binding state under governance. Entry requires explicit promotion and coordinate declaration.

## BOUNDARY ENFORCEMENT // 03

The system enforces a hard distinction:

- **Personal**: operator identity, working style, preferences; eligible for mediated storage by operator choice.
- **Private**: credentials, sensitive projects, regulated data, anything designated non-exportable; must remain under operator control and is not emitted to external runtimes by default.

The compiler must make boundary enforcement testable:

- packs declare boundary class in coordinates;
- procedures declare permissible inputs for each boundary class;
- mixed-boundary artifacts are disallowed unless explicitly segmented into separate artifacts with separate coordinates.

## TERMINATION AUTHORITY // 04

The compiler produces proposals; the operator ratifies changes that become binding.

Non-negotiable invariants:

- No silent promotion from candidate → ratified memory.
- No silent broadening of boundary class (private → personal) by inference.
- No opaque retention: durable state is inspectable and editable.

CC BY-SA 4.0 — Mikhail Shakhnazarov, February 2026


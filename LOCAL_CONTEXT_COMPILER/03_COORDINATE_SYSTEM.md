# 03 LOCAL CONTEXT COMPILER — COORDINATE SYSTEM

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT COMPILER
- COORDINATE SYSTEM (ARTIFACT ROUTING METADATA)
- DERIVATIVE CORPUS: EARMARK OPEN INTELLIGENCE PROTOCOL (OPENIP) v1.0 (FEBRUARY 2026)
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0

## PURPOSE // 01

Coordinates route artifacts to the correct procedures, checks, and boundary rules. They prevent category collapse and make conformance claims testable.

This coordinate system is compatible in spirit with the OpenIP kernel coordinate system and specializes it for the Local Context Compiler’s boundary requirements.

## AXES // 02

**Authority**: `draft` / `local rule` / `spec`

- `draft`: provisional; not binding; may be incomplete.
- `local rule`: binding within a specific compiler instance or project scope.
- `spec`: binding across this corpus.

**Audience**: `internal` / `external`

- `internal`: for local operator use; not intended to leave the local environment.
- `external`: intended to be emitted to a runtime or recipient outside the local store (e.g., pasted to a model surface).

**Verification**: `formal` / `checklist` / `evidence-bound`

- `formal`: structural compliance only.
- `checklist`: pass/fail against explicit criteria.
- `evidence-bound`: trace links inclusion and candidate updates to evidence.

**Context source**: `corpus-anchored` / `corpus+explicit-sources` / `operator-store`

- `operator-store` means the artifact depends on local operator material; traces should point to local references even if content is not exported.

**Time horizon**: `ephemeral` / `session` / `durable`

- durable artifacts must be promotable, inspectable, and (eventually) signable.

**Governance cost**: `untyped` / `light` / `strong`

- durable emitted packs typically require `strong`.

**Boundary**: `personal` / `private`

- `personal`: may be stored in mediated systems by operator choice; may be eligible for emission if other axes permit.
- `private`: must remain operator-controlled; emission to external runtimes is prohibited by default.

## HEADER SHAPE // 03

Durable artifacts use a parseable header at file start:

```
COORDINATES:
  Authority:
  Audience:
  Verification:
  Context:
  Time:
  Governance:
  Boundary:
STATUS:
  Lifecycle:
  Epistemic:
```

Values may remain blank during drafting, but promotion to durable status requires completion for the fields that gate boundary enforcement (`Audience`, `Context`, `Time`, `Boundary`).

CC BY-SA 4.0 — Mikhail Shakhnazarov, February 2026


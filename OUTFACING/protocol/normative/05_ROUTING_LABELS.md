# 05 ROUTING LABELS

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT PIPELINE PROTOCOL
- ROUTING LABELS
- ARTIFACT ROUTING METADATA
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## PURPOSE // 01

Artifacts are labeled, not guessed. A small set of routing labels classifies an artifact so the correct procedures, boundary rules, and checks can be applied. Labels prevent category collapse.

## THE AXES // 02

**Authority**: `draft` / `local_rule` / `spec`

- `draft`: provisional; not binding; may be incomplete.
- `local_rule`: binding within a specific pipeline instance or project scope.
- `spec`: binding across this corpus.

**Audience**: `internal` / `external`

- `internal`: not intended to leave the local environment.
- `external`: intended to be emitted outside the local store (e.g., pasted to a model surface).

**Verification**: `formal` / `checklist` / `evidence_bound`

- `formal`: structural compliance only.
- `checklist`: pass/fail against explicit criteria.
- `evidence_bound`: trace links inclusion and update proposals to evidence.

**Context**: `corpus_only` / `operator_store` / `operator_store+explicit_sources`

- `operator_store` means the artifact depends on local material; traces point to local references even if content is not exported.

**Time**: `ephemeral` / `session` / `durable`

- durable artifacts require governance and (eventually) signage.

**Governance**: `untyped` / `light` / `strong`

- durable emitted packets typically require `strong`.

**Boundary**: `personal` / `private`

- `personal`: may be stored in mediated systems by operator choice; may be eligible for emission if other axes permit.
- `private`: must remain operator-controlled; emission to external runtimes is prohibited by default.

## HEADER SHAPE // 03

Durable artifacts use a parseable header at file start:

```
ROUTING_LABELS:
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

Promotion to durable status requires completion of fields that gate boundary enforcement (`Audience`, `Context`, `Time`, `Boundary`).

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026

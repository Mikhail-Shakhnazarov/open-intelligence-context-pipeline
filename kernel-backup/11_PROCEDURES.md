# 11 PROCEDURES

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT COMPILER PROTOCOL
- PROCEDURES
- SECOND-ORDER TOKENS
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## PROCEDURE: INGEST (AIRLOCK) // 01

Input:

- raw material (notes, transcripts, documents, repository snapshots, calendar exports).

Output:

- airlocked raw captures with source metadata.

Acceptance criteria:

- raw inputs are preserved; no destructive rewrite;
- boundary class is assigned explicitly (personal or private) at ingest time.

## PROCEDURE: NORMALIZE (CANONICAL RECORD) // 02

Input:

- airlocked raw capture.

Output:

- canonical record (inspectable reference representation).

Acceptance criteria:

- canonical record preserves meaning and provenance pointers;
- normalization does not silently broaden boundary class.

## PROCEDURE: DERIVE (REBUILDABLE CACHES) // 03

Input:

- canonical records.

Output:

- caches: summaries, embeddings, indices.

Acceptance criteria:

- caches are labeled rebuildable; canonical records remain the reference;
- cache regeneration does not change durable claims without explicit promotion.

## PROCEDURE: PACK (COMPILED CONTEXT BUNDLE) // 04

Input:

- pack purpose declaration (task, audience, boundary, budget);
- eligible canonical records;
- selection policy and exclusion rules.

Output:

- bundle: compiled context + trace + candidate updates.

Acceptance criteria:

- bundle satisfies declared coordinates and boundary rules;
- compiled context is bounded and traceable;
- trace and candidates are produced alongside the pack (no pack-only emission).

## PROCEDURE: PROPOSE UPDATES (CANDIDATE MEMORY) // 05

Input:

- canonical records and observed work patterns;
- pack traces and outcomes (accepted/rejected inclusions).

Output:

- candidate updates (non-binding).

Acceptance criteria:

- each candidate carries derivation marking and evidence pointer;
- candidates include expiration or review triggers where appropriate;
- candidates do not self-ratify by being stored.

## PROCEDURE: PROMOTE (RATIFICATION) // 06

Input:

- candidate updates.

Output:

- durable registry updates (binding memory) with coordinates and status.

Acceptance criteria:

- promotion is an explicit event with recorded rationale;
- post-promotion artifacts remain inspectable and reversible by explicit patching.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026


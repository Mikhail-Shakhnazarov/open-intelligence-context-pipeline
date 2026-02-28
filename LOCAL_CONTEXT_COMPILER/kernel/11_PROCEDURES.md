# 11 PROCEDURES

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT PIPELINE PROTOCOL
- PROCEDURES
- SECOND-ORDER TOKENS
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## PROCEDURE: INGEST (QUARANTINE INBOX) // 01

Input:

- raw material (notes, transcripts, documents, repository snapshots, calendar exports).

Output:

- quarantined raw captures with source metadata.

Acceptance criteria:

- raw inputs are preserved; no destructive rewrite;
- boundary class is assigned explicitly (personal or private) at ingest time.

## PROCEDURE: NORMALIZE (CANONICAL RECORD) // 02

Input:

- quarantined raw capture.

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

## PROCEDURE: BUILD PACKET (CONTEXT PACKET SET) // 04

Input:

- packet request (task, audience, boundary, budget);
- eligible canonical records;
- selection policy and exclusion rules.

Output:

- set: context packet + selection trace + update proposals.

Acceptance criteria:

- set satisfies declared routing labels and boundary rules;
- packet content is bounded and traceable;
- trace and proposals are produced alongside the packet (no packet-only emission).

## PROCEDURE: PROPOSE UPDATES (UPDATE PROPOSALS) // 05

Input:

- canonical records and observed work patterns;
- packet traces and outcomes (accepted/rejected inclusions).

Output:

- update proposals (non-binding).

Acceptance criteria:

- each proposal carries derivation marking and evidence pointer;
- proposals include expiration or review triggers where appropriate;
- proposals do not self-approve by being stored.

## PROCEDURE: APPROVE (PROMOTION) // 06

Input:

- update proposals.

Output:

- durable registry updates (binding long-term state) with routing labels and status.

Acceptance criteria:

- promotion is an explicit event with recorded rationale;
- post-promotion artifacts remain inspectable and reversible by explicit patching.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026

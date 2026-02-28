# FAQ

## "A custom GPT / Gem already exists. What is gained by making it governed?"

Corporate and vendor safeguards mostly address storage and account access. Governance addresses *workflow authority*:

- **No silent promotion.** Suggestions do not become "truth" by repetition or by being stored.
- **Selection logs.** A selection log (selection trace) exists for what was shown to the assistant and why.
- **Boundaries that can be checked.** Confidential material is treated as "private" by default; emission is prohibited unless explicitly reclassified.
- **Portability.** The working state lives in artifacts, not in vendor memory.

In short: enterprise accounts can help with privacy; governance helps with *drift, boundary handling, and auditability*.

## "Does this make model output compatible across vendors?"

It makes the **working format around the model** compatible: the brief, the selection log, and the update proposals. The runtime remains different, but continuity and review are no longer vendor-owned.

## "Are rigid templates required?"

No. For a single operator, most structure can be invented ad hoc. What cannot be hand-waved if portability/audit is the point:

- a parseable header with routing labels and boundary,
- an explicit provisional vs settled distinction,
- the three-file output set (packet + trace + proposals).

Everything else can be light.

## "Does this work for teams?"

Yes. The team case is the single-operator case plus coordination on shared durable artifacts: a shared store for team registries, an agreed ratification rule for update proposals, and explicit boundary rules for what can be shared vs what remains in member userland.

## "Is this a safety or compliance product?"

No. This repository is a workflow protocol. It can support compliance work by creating auditable artifacts, but it is not legal advice and it does not replace organizational policy.

## "What is the smallest useful version?"

A minimal system is:

- a style/requirements registry,
- an entities/decision log registry,
- the three canonical outputs per session,
- a weekly review where proposals are accepted/rejected.

## "What breaks first in practice?"

- **Category collapse** (private vs shareable becomes ambiguous under convenience).
- **Promotion by inertia** (proposals harden because nobody reviews them).
- **Overgrowth** (registries swell without pruning).

The protocol exists mainly to prevent these three.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

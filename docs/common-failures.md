SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Common workflow failure modes and how the artifacts prevent them.
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# Common failures (and how the artifacts prevent them)

These failures appear even with "enterprise" accounts. They are workflow failures: unclear authority, unclear boundaries, and invisible change.

## Failure 1 - A guess becomes "truth later"

**Symptom:** a confident answer is repeated later as if it were fact.

**Cause:** no separation between:

- "worked in the moment" and
- "approved into durable state"

**Prevention:**

- put uncertain items into update proposals (stated / inferred / assumed),
- only after approval does anything become durable.

**Repair:**

- downgrade the item to provisional,
- add evidence or delete it.

## Failure 2 - Boundary leak

**Symptom:** confidential material is pasted into the wrong assistant surface or into an external packet.

**Cause:** boundary was implicit; convenience won.

**Prevention:**

- default boundary is private,
- context packet declares boundary via artifact labels,
- selection log (selection trace) records boundary applied + major exclusions.

**Repair:**

- tighten boundary policy,
- add an explicit "eligibility for external sharing" rule,
- treat future packets as private until proven otherwise.

## Failure 3 - Invisible selection

**Symptom:** output varies; nobody can tell why; review turns into opinions.

**Cause:** selection is opaque.

**Prevention:**

- selection log is mandatory: what was included and why,
- major exclusions are named when relevant.

**Repair:**

- retroactively write a selection log,
- identify missing/irrelevant context,
- update the selection habit (or selection policy, if formalized).

## Failure 4 - Durable store bloat (lock-in by accumulation)

**Symptom:** packets get longer; contradictions accumulate; switching tools feels impossible.

**Cause:** everything that felt useful was kept forever.

**Prevention:**

- weekly review includes pruning,
- durable registries stay small and intentional,
- rebuildable index (if used) stays non-authoritative.

**Repair:**

- archive old projects,
- merge duplicates,
- delete stale preferences,
- downgrade uncertain items to provisional.

## Failure 5 - Format drift / copy-paste corruption

**Symptom:** artifacts slowly change through copying/formatting; nobody notices until it matters.

**Cause:** text traveled without a drift check.

**Prevention (optional but useful):**

- use a copy/paste drift check (drift marking) on durable artifacts,
- keep the marking profile stable.

**Repair:**

- compare against the last known good artifact,
- regenerate from normalized records where possible,
- apply drift marking where it matters.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

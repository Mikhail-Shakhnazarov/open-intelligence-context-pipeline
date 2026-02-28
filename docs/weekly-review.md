SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Weekly review (15-30 min/week) for approving proposals and pruning durable registries.
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# Weekly review (15-30 minutes)

This is the maintenance practice. It is where "governed" becomes real.

The rhythm is simple: sessions produce **update proposals**; the weekly review produces **approval** (or rejection) and pruning.

## Inputs

- update proposal files from recent sessions
- durable registries (entities, style contract, decision log, boundary policy)
- optional: a rebuildable index (if used)

## Step 1 - Triage proposals (5 minutes)

For each proposal:

- Does it reduce future work reliably?
- Is it correctly classified (private/work/personal; internal/external eligibility)?
- Is derivation marked (stated / inferred / assumed)?
- Is there an evidence pointer?

Outcomes:

- **Approve** - accept into a durable registry as a normalized record.
- **Reject** - record a one-line reason.
- **Defer** - attach a trigger (e.g., "after next meeting") or an expiry.

## Step 2 - Apply approvals (5-10 minutes)

When approving:

- write accepted text into the correct durable registry,
- keep it compact,
- merge duplicates rather than adding near-duplicates.

If the style contract changes, record it in the decision log.

## Step 3 - Prune durable registries (5-10 minutes)

Durable registries must stay small.

- delete stale preferences,
- merge duplicates,
- downgrade uncertain items back to provisional,
- archive closed projects,
- tighten boundaries where the week revealed risk.

## Step 4 - Optional: rebuild the rebuildable index (2 minutes)

If a rebuildable index exists, regenerate it from durable registries.

Rule: the rebuildable index is **not authoritative**. If it disagrees with durable registries, fix the registries.

## Output

After the review:

- proposals are marked approved / rejected / deferred,
- durable registries are updated (normalized records),
- registries are pruned,
- boundary posture is reaffirmed.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

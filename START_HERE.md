SPDX-License-Identifier: CC-BY-SA-4.0
Summary: Fast onramp for running the Open Intelligence Context Pipeline (Local Context Pipeline Protocol).
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md at the repo root.

# START HERE

This repository defines a **governed assistant workflow**.

The "assistant" is only an interface (a governed LLM runtime). The workflow is the stable part: a way to maintain continuity as **operator-owned artifacts**, with explicit boundaries and explicit approval.

## The three-file set (per session)

Each session produces a **three-file set**:

1. **Context packet** - the bounded brief given to the runtime.
2. **Selection log (selection trace)** - a short log of what was included and why (plus major exclusions).
3. **Update proposals** - suggested long-term changes, pending **approval**.

Nothing becomes durable by accident.

## The minimum rules (plain language)

- Default boundary is **private** unless explicitly marked otherwise.
- The selection log is not optional. If it does not exist, the packet is not trustworthy.
- Update proposals are not durable until approved and written into a durable registry as a **normalized record**.
- A **rebuildable index** (if used) is not authoritative. It can be regenerated from durable registries.
- If integrity matters, use a **copy/paste drift check** (drift marking) on durable artifacts.

## 10-minute onramp

1. Choose one real task for today.
2. Create a session folder and copy in the three templates (context packet / selection log / update proposals).
3. Fill the context packet with 3-8 items.
4. Fill the selection log (5-10 bullets).
5. Run the session using only the context packet as the briefing.
6. Write update proposals. Approve/reject them later during the weekly review.

## Files to read next

- `docs/first-30-minutes.md` - scripted first run.
- `docs/weekly-review.md` - the maintenance practice (15-30 min/week).
- `docs/common-failures.md` - what breaks and how the artifacts prevent it.
- `tour/docent-script.md` - a guided tour runnable in any assistant UI.
- `docs/compatibility.md` - what "compatible" means (plain contract).

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

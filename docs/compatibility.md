SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Plain-language contract for what a compatible workflow must do.
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# Compatibility (plain contract)

This document defines a "compatible workflow" in plain language.

Compatibility matters because it keeps the workflow portable across assistants and vendors. The assistant is an interface; the workflow is the stable layer.

## Required (for compatibility)

A compatible workflow:

1. Produces a **three-file set** for each session:
   - `context_packet.md`
   - `selection_trace.md` (selection log; selection trace)
   - `update_proposals.md`

   File naming rule: `selection_trace.md` is the canonical filename for the selection log. Do not rename it to `selection_log.md` (or other variants) if portability is a goal.

2. Treats the selection log as mandatory.
   - If there is no selection log, the packet is not considered valid.

3. Separates update proposals from durable state.
   - Durable state changes only by explicit **approval**.

4. Uses **artifact labels** (or an equivalent explicit classification header) to declare:
   - boundary (private by default),
   - intended audience (internal vs external),
   - authority level (durable vs session),
   - verification stance (how claims should be treated).

5. Keeps custody local by default.
   - The workflow must not require vendor-owned hidden memory to function.

## Recommended (strongly)

A compatible workflow should:

- keep durable registries as **normalized records**,
- keep durable registries small via weekly pruning,
- maintain a boundary policy that treats work material as private by default,
- use a copy/paste drift check (drift marking) for durable artifacts that must not silently change.

## Extensions and dialects

Extensions are allowed.

- If an extension changes meaning (new labels, new artifact types, new obligations), write it down as a public addendum.
- If an extension is proprietary/undocumented, treat it as a dialect: it may work locally but is not portable.

## What compatibility does not promise

Compatibility does not promise identical model output. It promises:

- stable inputs (packets),
- visible selection (logs),
- controlled change (proposals + approval),
- clear boundaries (artifact labels),
- portability of continuity.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

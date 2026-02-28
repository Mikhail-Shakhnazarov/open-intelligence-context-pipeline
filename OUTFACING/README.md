# Local Context Pipeline Protocol (text-first)

This repository contains a text-defined workflow for **governed assistant work**.

> NON-NORMATIVE: This README is informational. Normative requirements live in `protocol/`.

"Governed" here does not mean corporate policy claims or vendor assurances. It means: the working state is kept as **operator-owned artifacts** with explicit boundaries and explicit change-control, so assistant use becomes inspectable, portable, and reviewable across runtimes.

The protocol is intentionally boring on purpose: it treats continuity as paperwork.

## What gets produced every session

The canonical output is a set of three files:

- **Context packet** (`context_packet.md`): the bounded brief given to the runtime.
- **Selection trace** (`selection_trace.md`): why each item was included (a receipt).
- **Update proposals** (`update_proposals.md`): suggested long-term updates, explicitly non-binding until approved.

The set is the governance unit. Packet-only workflows drift into opaque selection and silent hardening.

## When this matters (economic + organizational context)

Vendor "memory" is a switching-cost mechanism. Corporate accounts can reduce some categories of risk, but they do not solve:

- accidental canon formation ("we wrote it once so it became true later"),
- boundary leaks (confidential material pasted into the wrong surface),
- audit gaps ("why did the assistant do that; what did it see?"),
- portability ("rebuild everything when the tool policy changes").

This protocol makes the *selection and promotion steps visible*.

## Repository layout

- `protocol/` -- the normative corpus (routing labels, obligations, procedures, conformance).
- `starter-kit/` -- minimal templates and registries for a single operator.
- `examples/` -- small worked examples (brief + receipt + change requests).
- `docs/` -- practical notes for workplace use.
- `analysis/` -- background reasoning and incentives framing.

## Quick start

1. Copy `starter-kit/` into an operator store (a local folder, a private repo, or an internal knowledge base).
2. For a task, fill a **context packet set** (three files) using the templates.
3. Run the session using the packet as the only briefing material.
4. After the session, keep outputs and produce **update proposals** (still provisional).
5. Periodically, review proposals and explicitly accept/reject them into durable registries.

This is meant to be usable ad hoc by a single operator. The invariants are minimal: labels, boundaries, trace, and no silent promotion.

## License and attribution

The protocol text and repository documentation are licensed **CC BY-SA 4.0** (see `LICENSE.md`).
Copyright (c) 2026 Mikhail Shakhnazarov

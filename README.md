# Open Intelligence Context Pipeline (Local Context Pipeline Protocol)

This repository contains a text-defined workflow for **governed assistant work**.

> NON-NORMATIVE: This README is informational. Normative requirements live in `protocol/normative/`. Plain-language mirror: `protocol/plain-language/`.

A note from the author: work is a process. Programming governance structures in natural language is fun, but it takes time. The assistant persona is not yet finalized, but any competent runtime will assume one when instructed, so feel free to just instruct the runtime to assist and follow protocol.

One switch makes all the difference here: you need to switch from having a conversation with an LLM runtime to **instructing** the LLM runtime. That change takes a bit of perspective shifting, but once you are there, there is no going back.

I don't think this technology should be free. I strongly believe this is just a form of literacy and knowledge should be free. Pay attention to the licensing when forking.

In the meantime, [hire me](https://www.linkedin.com/in/shakhnazarov/) to build a personalized procedural pipeline and intelligence corpus for you and your organization **and also** see me on [patreon](https://www.patreon.com/c/earmark/membership). 

More info on the Open Intelligence Protocol (OpenIP) project [here](https://earmark.build/)

"Governed" here does not mean corporate policy claims or vendor assurances. It means: the working state is kept as **operator-owned artifacts** with explicit boundaries and explicit change-control, so assistant use becomes inspectable, portable, and reviewable across runtimes.

The protocol is deliberately procedural: continuity is maintained through explicit artifacts rather than implicit tool "memory".

## What gets produced every session

The canonical output is a set of three files:

- **Context packet** (`context_packet.md`): the bounded brief given to the runtime.
- **Selection log** (`selection_trace.md`; selection trace): why each item was included.
- **Update proposals** (`update_proposals.md`): suggested long-term updates, explicitly non-binding until approved.

The set is the governance unit. Packet-only workflows drift into opaque selection and silent hardening.

## When this matters (economic + organizational context)

Vendor "memory" increases switching costs. Corporate accounts can reduce some categories of risk, but they do not solve:

- accidental canon formation ("we wrote it once so it became true later"),
- boundary leaks (confidential material pasted into the wrong surface),
- audit gaps ("why did the assistant do that; what did it see?"),
- portability ("rebuild everything when the tool policy changes").

This protocol makes the *selection and promotion steps visible*.

## Repository layout

- `protocol/` -- protocol editions (normative corpus + plain-language mirror).
- `starter-kit/` -- minimal templates and registries for a single operator.
- `examples/` -- small worked examples (brief + selection log + update proposals).
- `docs/` -- practical notes for workplace use.
- `market-analysis-and-project-rationale/` -- background reasoning, incentives framing, and project rationale.
- `cc0/` -- a copy/paste pitch + quickstart intended for internal documentation reuse.

## Quick start

Two equal entrypoints:

- Personal path (single operator): `docs/personal-quickstart.md`
- Team path (shared outputs + personal userland): `docs/team-quickstart.md`

1. Copy `starter-kit/` into an operator vault (a local folder, a private repo, or an internal knowledge base).
2. For a task, fill a **context packet set** (three files) using the templates.
3. Run the session using the packet as the only briefing material.
4. After the session, keep outputs and produce **update proposals** (still provisional).
5. Periodically, review proposals and explicitly accept/reject them into durable registries.

This is meant to be usable ad hoc by a single operator. The invariants are minimal: labels, boundaries, trace, and no silent promotion.

## License and attribution

This repository uses a split license strategy (see `LICENSE.md`):

- `protocol/` and `market-analysis-and-project-rationale/` are CC BY-SA 4.0.
- `docs/` is dual-licensed: CC BY-SA 4.0 OR CC0 1.0.
- `starter-kit/` and `examples/` are dual-licensed: CC BY-SA 4.0 OR CC0 1.0.
- `cc0/` is CC0 1.0 (explicitly for internal copy/paste).

Copyright (c) 2026 Mikhail Shakhnazarov



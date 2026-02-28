SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Scripted first run (30 minutes) for producing a three-file set.
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# First 30 minutes

Goal: complete one real task using the governed workflow and end with a usable **three-file set**.

Assumption: a local folder exists that contains the starter kit templates and registries.

## 0) Choose the boundary (2 minutes)

Pick one:

- **Personal**: private to an individual.
- **Work**: private to an organization.

In custody terms, both are **private** by default. Only explicitly marked material is eligible for external sharing.

## 1) Pick one real task (2 minutes)

Choose a task with a concrete deliverable and a short horizon:

- draft a message,
- summarize notes into action items,
- produce a short plan,
- rewrite a paragraph to match a style contract.

## 2) Create the session folder + three files (5 minutes)

Create a folder named like:

`YYYY-MM-DD__slug__001/`

Add:

- `context_packet.md`
- `selection_trace.md` (selection log)
- `update_proposals.md`

Copy/paste the templates from `starter-kit/` if available.

Fill only what matters:

- purpose (one sentence),
- constraints (what must not happen),
- included context (3-8 items is enough).

## 3) Write the selection log (3 minutes)

Minimum content:

- for each included item: why it matters for this task,
- boundary applied (private; internal vs external),
- one major exclusion (if relevant) and why it is excluded.

Keep it short. The point is that selection is not magic.

## 4) Run the session (10-15 minutes)

Paste the **context packet** into the assistant. Then paste this instruction block:

> **Runtime instruction (paste into chat)**
>
> Use the provided context packet as the only briefing.
> Treat everything as **private** unless the packet explicitly marks eligibility for external sharing.
> Do not invent facts. If something is missing, ask for the smallest missing detail or mark it as an assumption.
> Produce the requested deliverable.
> Then output:
> 1) a short list of uncertainties/assumptions, and
> 2) 3-7 update proposals that would reduce future work (each tagged: stated / inferred / assumed).

## 5) Write update proposals into the file (5 minutes)

Take the suggested updates and rewrite them into `update_proposals.md`:

- keep them compact,
- point to evidence ("where this came from"),
- keep them pending approval.

Do **not** write them into durable registries yet.

## Success condition

Success is not "perfect output." Success is:

- a deliverable exists,
- the three-file set exists,
- the long-term store did not silently change.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

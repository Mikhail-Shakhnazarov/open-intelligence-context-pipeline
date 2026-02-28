SPDX-License-Identifier: CC0-1.0
Summary: Copy/paste pitch + quickstart for internal adoption of the Local Context Pipeline Protocol.
Permissions: CC0; no attribution required. Copy into wikis, runbooks, onboarding docs, and tooling repos.
See: LICENSE.md in this directory.

# Local Context Pipeline Protocol: one-page pitch + quickstart

This is a text-first workflow for using assistants without letting vendor "memory" silently become the source of truth.

The point is not better prompting. The point is governance: making the assistant's working context bounded, inspectable, and reviewable, so continuity survives runtime/tool changes and sensitive material stays inside the correct boundary.

The canonical output per session is a three-file set:

- `context_packet.md`: the bounded brief that is fed to the runtime.
- `selection_trace.md`: a selection log (selection trace) of what was included and why.
- `update_proposals.md`: change requests to durable state, explicitly non-binding until reviewed and accepted.

This produces a simple but enforceable rule: nothing becomes durable because it was said once. Long-term "memory" is a curated store that changes only through explicit ratification.

## Quick start (copy/paste workflow)

1. Keep an operator store (private repo, local folder, or internal knowledge base) that holds durable registries and prior packet sets.
2. For a task, create a new packet set (three files) using the templates in `starter-kit/`.
3. Populate `context_packet.md` with only the records eligible for the task boundary (private vs personal; internal vs external).
4. Populate `selection_trace.md` with a short justification and evidence pointer for each included record.
5. Run the assistant session using the packet as the only briefing material.
6. After the session, write `update_proposals.md` as a list of candidate registry updates (still provisional).
7. On a review cadence (weekly is enough), accept/reject proposals into durable registries.

## Where the rules live

Normative requirements, definitions, and conformance live in `protocol/normative/`. Plain-language mirror: `protocol/plain-language/`. This page is non-normative and is meant to be copied into internal documents.

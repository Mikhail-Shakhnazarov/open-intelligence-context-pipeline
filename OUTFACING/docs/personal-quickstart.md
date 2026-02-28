SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Personal path quickstart (single operator) for running the Local Context Pipeline Protocol.
Normative: Requirements and definitions live in `protocol/` (this repository).
See: LICENSE.md in this directory.

# Personal quickstart (single operator)

The personal path keeps assistant continuity in explicit, operator-owned artifacts rather than relying on vendor-managed "memory". The goal is portability (swap runtimes without losing continuity) and governance (no silent promotion of guesses into durable state).

The kernel is a three-file set per session:

- `context_packet.md`: the bounded brief that is fed to the runtime.
- `selection_trace.md`: why each item was included (a receipt).
- `update_proposals.md`: suggested durable updates, explicitly non-binding until ratified.

## Minimal setup

Create an operator store (local folder, private repo, or internal KB) that will hold durable registries and prior packet sets. Copy `starter-kit/` into that operator store.

Durable registries start small. A minimal set is:

- `registries/style_contract.md`
- `registries/entities.md`
- `registries/decision_log.md`
- `registries/boundary_policy.md`

## Run one session

1. Create a new packet set directory for the task (three files).
2. Fill `context_packet.md` using only records eligible for the boundary of the session.
3. Fill `selection_trace.md` with a short justification and evidence pointer for each included record (and major exclusions if relevant).
4. Run the assistant session using the packet as the only briefing material.
5. After the session, write `update_proposals.md` as candidate changes to durable registries (still provisional).

## Keep it governed (minimal overhead)

The workflow drifts when provisional content becomes durable by inertia. The simplest stabilizer is a short review cadence (weekly is enough): accept/reject proposals into registries and prune duplicates. No other ceremony is required.

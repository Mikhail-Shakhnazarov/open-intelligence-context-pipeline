SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Team path quickstart (shared outputs + personal userland) for running the Local Context Pipeline Protocol.
Normative: Requirements and definitions live in `protocol/` (this repository).
See: LICENSE.md in this directory.

# Team quickstart (shared outputs + personal userland)

The team path is the personal path plus coordination on shared artifacts. The kernel stays unchanged: each session produces a bounded packet, a receipt, and explicit update proposals. The additional discipline is that the team agrees on what is shared, who can ratify updates, and what is prohibited from crossing boundaries.

Two stores exist in parallel:

- Member userland: each team member's operator store (drafts, local notes, provisional interpretations, and private material).
- Team shared store: a shared location for team registries and agreed durable state.

The team shared store is a coordination interface, not a compliance product. It is simply where the team keeps the artifacts that must be stable across members and across time.

## Minimal setup

1. Create a team shared store (internal repo or internal KB).
2. Copy `starter-kit/registries/` into the team shared store and treat them as the initial team registries.
3. Establish a ratification rule: who can accept/reject update proposals into the team registries, and on what cadence.

## Run one session (team task)

1. A team member creates a packet set for the task.
2. `context_packet.md` references team registries as the default authority for shared facts, decisions, and style requirements.
3. `selection_trace.md` records why each record was included and where it came from (team registry entry, prior decision, or approved source record).
4. The assistant session is run against the bounded packet (no additional hidden briefing sources).
5. `update_proposals.md` is produced as explicit candidate updates to team registries (and optionally to the member's private registries).

## Promotion discipline (what makes it "team" rather than "personal")

The main failure mode is unreviewed promotion: a draft becomes "the team's truth" because it was repeated. The team path prevents this by making promotion explicit: update proposals remain non-binding until ratified into the shared store.

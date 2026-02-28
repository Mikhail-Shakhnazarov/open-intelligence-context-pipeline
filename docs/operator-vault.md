SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: What an operator vault is and how to structure it (plain, practical guidance).
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# Operator vault

An operator vault is the local place that holds continuity for this workflow: durable registries plus the history of session outputs. It can be a local folder, a private repo, or an internal knowledge base.

The assistant UI is replaceable. The operator vault is the stable layer.

## Minimal contents

- Durable registries (long-term state): `registries/`
- Session folders (three-file sets): `sessions/`

Copy `starter-kit/` into the operator vault as a starting point.

## Recommended layout (example)

This is a suggestion, not a requirement:

- `registries/`
  - `boundary_policy.md`
  - `entities.md`
  - `decision_log.md`
  - `style_contract.md`
- `sessions/`
  - `YYYY-MM-DD__slug__001/`
    - `context_packet.md`
    - `selection_trace.md` (selection log)
    - `update_proposals.md`
- `sources/` (optional; operator-controlled)
  - stable reference docs, sanitized exports, or links
- `quarantine/` (optional)
  - raw captures awaiting normalization and boundary classification

## Default posture

- Treat the entire operator vault as **private** by default.
- Do not rely on vendor "memory" as the continuity layer.
- Do not let proposals become durable by inertia. Use a weekly review.

## What not to store

This workflow is compatible with very sensitive domains, but the operator vault still needs hygiene:

- Do not store credentials, API keys, or tokens in plaintext.
- Do not store raw confidential dumps unless the boundary and custody are explicitly controlled.
- Prefer references and normalized summaries over bulk copies when possible.

## Team usage

Teams typically use two vaults in parallel:

- Member userland: each member's private operator vault (drafts, notes, provisional interpretations).
- Team shared vault: a shared location for team registries and approved durable state.

The shared vault is a coordination interface, not a compliance product.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0


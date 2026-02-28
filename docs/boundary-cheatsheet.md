SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Plain boundary cheatsheet (private by default; internal vs external eligibility).
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# Boundary cheatsheet

The boundary decision is the first decision in this workflow. Everything else depends on it.

Default rule: treat material as **private** unless it is explicitly eligible for external sharing.

## Two questions to decide the boundary

1. Custody: is this **personal** or **work**?
   - Both are private by default (the difference is who the boundary belongs to).

2. Emission eligibility: is the intended audience **internal** or **external**?
   - Internal: may include private material (still bounded to the correct custody).
   - External: must include only material explicitly eligible for external sharing.

## Common "never external" categories (examples)

Keep this list generic. It is a reminder, not a data collection step.

- credentials, secrets, tokens
- client data, customer data, personal data
- internal financials and forecasts
- unreleased product plans, roadmaps, strategy memos
- legal/HR material under policy or contract
- anything covered by NDA or confidentiality terms

## Where the boundary is recorded

- Packet: in the artifact labels at the top of `context_packet.md`.
- Selection log: in `selection_trace.md` (selection log), record which boundary was applied and why exclusions happened.
- Durable policy: in `starter-kit/registries/boundary_policy.md` (or an equivalent registry in the operator store).

## A simple external rule

If a packet is intended for an external audience, add an explicit allowlist sentence in the packet:

- "This packet is eligible for external sharing because: <reason>."

If that sentence cannot be written honestly, treat the packet as private/internal.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

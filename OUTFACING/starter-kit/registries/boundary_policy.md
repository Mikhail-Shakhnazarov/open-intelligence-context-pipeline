# registries/boundary_policy.md

> NON-NORMATIVE TEMPLATE: Starter registry. Normative requirements live in `protocol/`.

ROUTING_LABELS:
  Authority: local_rule
  Audience: internal
  Verification: checklist
  Context: operator_store
  Time: durable
  Governance: strong
  Boundary: private
STATUS:
  Lifecycle: settled
  Epistemic: settled

## Purpose

A compact statement of what is considered private and what is eligible for external emission.

## Default

- Everything in the operator store is treated as **private** unless explicitly classified otherwise.
- External packets must contain only eligible material.

## Eligibility (examples)

Eligible for external emission:

- public information,
- operator-authored prose that contains no confidential material,
- sanitized summaries approved for sharing.

Not eligible:

- client data,
- internal financials,
- credentials,
- anything covered by NDA, contract, or policy.

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

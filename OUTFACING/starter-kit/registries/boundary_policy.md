SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative starter registry template for boundary posture and eligibility for emission.
Normative: Requirements and definitions live in `protocol/` (this repository).
See: LICENSE.md in the parent directory.

# registries/boundary_policy.md

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

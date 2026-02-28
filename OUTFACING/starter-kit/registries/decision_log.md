SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative starter registry template for durable governance-relevant decisions.
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in the parent directory.

# registries/decision_log.md

ROUTING_LABELS:
  Authority: local_rule
  Audience: internal
  Verification: evidence_bound
  Context: operator_store
  Time: durable
  Governance: strong
  Boundary: private
STATUS:
  Lifecycle: settled
  Epistemic: mixed

## Purpose

A durable log of governance-relevant decisions: boundary changes, rule changes, and template changes.

## Entries

- DEC-001 -- <decision summary>
  - Date:
  - Scope: <project/global>
  - Decision: <what changed>
  - Reason: <why>
  - Evidence pointer: <meeting note, policy text, etc.>


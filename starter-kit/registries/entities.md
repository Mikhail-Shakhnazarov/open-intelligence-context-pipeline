SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative starter registry template for durable entity and project references.
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in the parent directory.

# registries/entities.md

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
  Epistemic: mixed

## Purpose

A durable index of people, projects, systems, and recurring artifacts referenced by packets and traces.

## ID format

- `ENT-###` for entities
- `PRJ-###` for projects
- `SYS-###` for systems/tools

## Entries

- ENT-001 -- <name or role>
  - Type: <person/org>
  - Notes: *<why it matters>*
  - Boundary notes: *<what must not be exported>*

- PRJ-001 -- <project name>
  - Notes: *<one paragraph>*
  - Constraints: *<confidentiality, deadlines>*


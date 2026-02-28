# registries/entities.md

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

Copyright (c) 2026 Mikhail Shakhnazarov -- CC BY-SA 4.0

# 09 PIPELINE MODEL (plain-language mirror)

This is a plain-language mirror of: `../normative/09_PIPELINE_MODEL.md`.
This mirror is not authoritative. If any discrepancy exists, the normative edition governs.

## Overview

The local context pipeline is a workflow with:

- an input boundary (what is captured and under what custody),
- transforms (normalize, derive indexes, build packet sets),
- outputs (packet + log + proposals),
- a promotion gate (approval into durable registries),
- caches that are rebuildable (not authoritative).

## Key boundary posture

- Raw captures can be quarantined until normalized.
- Derived indexes can be regenerated.
- Durable claims live in durable registries after explicit approval.

The normative edition defines the state machine and acceptance criteria in detail.


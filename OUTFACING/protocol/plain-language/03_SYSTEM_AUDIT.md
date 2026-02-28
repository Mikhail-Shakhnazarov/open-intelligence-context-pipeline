# 03 SYSTEM AUDIT (plain-language mirror)

This is a plain-language mirror of: `../normative/03_SYSTEM_AUDIT.md`.
This mirror is not authoritative. If any discrepancy exists, the normative edition governs.

## Purpose

This document defines how to configure a language-model runtime as a read-only auditor for protocol artifacts.

The auditor:

- identifies artifact type and required structure,
- checks artifact labels (routing labels) and boundary declarations,
- checks that selection logs justify each inclusion,
- checks procedure acceptance criteria when procedures are declared,
- reports findings without modifying governed artifacts.

The auditor is not a governance authority. It cannot approve/ratify updates and it does not produce packet sets.


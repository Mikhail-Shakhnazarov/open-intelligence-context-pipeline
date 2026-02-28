# 12 CONFORMANCE (plain-language mirror)

This is a plain-language mirror of: `../normative/12_CONFORMANCE.md`.
This mirror is not authoritative. If any discrepancy exists, the normative edition governs.

## Purpose

Conformance converts posture into checkable claims. The protocol is portable only if procedures and boundary rules can be tested by fixtures and regressions.

## Example conformance claims (high level)

- Determinism (procedure-level): given the same inputs and selection policy, packet building produces the same set (or declared bounded nondeterminism).
- Boundary enforcement: private content is not emitted to external runtimes by default.
- No silent promotion: proposals remain non-binding until explicit approval.
- Trace completeness: each included packet item has a corresponding justification in the selection log.
- Rebuildable index non-authority: derived indexes are not sole provenance for durable claims.

Exact claim text and fixture posture are defined in the normative edition.


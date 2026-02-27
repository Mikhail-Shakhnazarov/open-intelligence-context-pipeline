# 07 LOCAL CONTEXT COMPILER — CONFORMANCE

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT COMPILER
- CONFORMANCE (TESTABLE CLAIMS)
- DERIVATIVE CORPUS: EARMARK OPEN INTELLIGENCE PROTOCOL (OPENIP) v1.0 (FEBRUARY 2026)
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0

## PURPOSE // 01

Conformance converts posture into checkable claims. The Local Context Compiler is “portable” only to the extent that its procedures and boundary rules are testable by fixtures and regressions.

## CONFORMANCE CLAIMS (V0) // 02

The following claims define initial conformance scope.

**C-1 Determinism (procedure-level).**

Given identical canonical records, identical coordinates, and identical selection policy, the `PACK` procedure produces identical bundles (byte-for-byte) or produces declared, bounded nondeterminism with traceable cause.

**C-2 Boundary enforcement.**

Artifacts with `Boundary: private` do not emit private content to external runtimes by default. Artifacts intended for external emission declare boundary class and are checked for violations.

**C-3 No silent promotion.**

Candidate updates remain non-binding until an explicit `PROMOTE` event. Storage is not ratification.

**C-4 Trace completeness.**

Every included pack item has a corresponding justification in the trace.

**C-5 Cache non-authority.**

Derived caches never serve as sole provenance for durable claims; canonical records remain reference.

## FIXTURES (PLANNED) // 03

Fixtures are synthetic and minimal until real operator material is introduced under explicit control.

Fixture requirements:

- include at least one personal record and one private record;
- include a selection policy that forbids private emission;
- include a pack request with `Audience: external`, `Boundary: personal`;
- assert that private content is excluded and that exclusions are justified in trace.

## REGRESSION POSTURE // 04

Changes to:

- boundary rules,
- artifact categories,
- coordinate axes,
- procedure acceptance criteria

require:

- fixture updates, and
- an explicit rationale recorded as a patch in this corpus.

CC BY-SA 4.0 — Mikhail Shakhnazarov, February 2026


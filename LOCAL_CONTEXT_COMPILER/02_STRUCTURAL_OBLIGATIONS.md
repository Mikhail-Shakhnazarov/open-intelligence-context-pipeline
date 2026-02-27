# 02 LOCAL CONTEXT COMPILER — STRUCTURAL OBLIGATIONS

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT COMPILER
- STRUCTURAL OBLIGATIONS (PROJECTED)
- DERIVATIVE CORPUS: EARMARK OPEN INTELLIGENCE PROTOCOL (OPENIP) v1.0 (FEBRUARY 2026)
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0

## OVERVIEW // 01

The Local Context Compiler is specified as a governed text system. The OpenIP kernel defines six structural obligations required for portability and durability of governed corpora; this document projects those obligations onto the specific problem of compiling bounded context packs.

The obligations below are minimum conditions for the compiler to remain:

- vendor-independent (runtime replaceable);
- inspectable (selection and promotion legible);
- safe against silent accumulation (no hidden “memory” hardening);
- testable (claims checkable by fixtures and regressions).

## OBLIGATION 1: SECOND-ORDER TOKENS // 02

The compiler’s procedures are second-order tokens: each transform is named, declared, and acceptance-tested.

Minimum requirement:

- Every transform that creates durable state (packs, traces, candidate updates, ratified memory) must declare inputs, outputs, and “done” criteria in text.

Failure mode:

- ad hoc, tool-specific behavior that cannot be reimplemented by another runtime or verified by another party.

## OBLIGATION 2: ARTIFACT COORDINATES // 03

Every durable artifact produced by the compiler declares routing metadata: what kind of thing it is, how it may be used, and which checks apply.

Minimum requirement:

- Artifacts are classed such that boundary rules are enforceable (especially personal vs private separation).

Failure mode:

- category collapse: drafts treated as durable; private material treated as personal; “pack” treated as an unbounded dump.

## OBLIGATION 3: COMPACTION TRANSFORMS // 04

High-entropy inputs are quarantined by default and reduced only through explicit transforms. The compiler is, primarily, a compaction and selection system.

Minimum requirement:

- Inputs enter an airlock (raw capture); only compacted, typed artifacts are eligible for durable use.
- Derived structure (summaries, embeddings, indices) is treated as rebuildable cache; the canonical record remains inspectable.

Failure mode:

- importing raw logs directly into durable state; treating caches as truth; allowing silent cross-scope leakage.

## OBLIGATION 4: EPISTEMIC GOVERNANCE // 05

The compiler must make epistemic standing visible: settled vs provisional, stated vs inferred vs assumed, and ratified vs candidate.

Minimum requirement:

- Candidate memory updates remain explicitly provisional until operator ratification.
- Pack inclusion rationales are separable from included content (trace exists, and is inspectable).

Failure mode:

- promotion by inertia: candidates harden into “memory” because they look clean or because the tool stored them.

## OBLIGATION 5: INTRINSIC SIGNAGE // 06

Durable artifacts that leave their original storage context require transport-surviving drift detection. Context packs are, by design, copy/pasted and routed through channels that strip metadata.

Minimum requirement:

- A declared plan for intrinsic provenance is present at the corpus level, even if the initial implementation is deferred.

Failure mode:

- version confusion: a pack is modified, truncated, or recombined without detectable signal; trace no longer matches pack.

## OBLIGATION 6: CROSS-RUNTIME VERIFICATION // 07

Portability is operationally tested. The same governed procedures should produce consistent, verifiable artifacts across different runtimes and toolchains (within declared tolerance).

Minimum requirement:

- Conformance fixtures exist for selection and compaction behavior, boundary enforcement, and non-promotion invariants.

Failure mode:

- the “spec” is the vendor; behavior drifts with model changes; the compiler becomes a proprietary memory pipeline by accident.

CC BY-SA 4.0 — Mikhail Shakhnazarov, February 2026


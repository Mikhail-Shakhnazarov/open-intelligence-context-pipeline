# 04 STRUCTURAL OBLIGATIONS

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT PIPELINE PROTOCOL
- STRUCTURAL OBLIGATIONS
- THE SIX REQUIREMENTS FOR PORTABILITY
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## OVERVIEW // 01

A conformant local context pipeline satisfies six structural obligations. These are minimum conditions for the corpus to function as a specification rather than a set of prompts or a vendor memory feature.

Failure on any obligation degrades along a predictable axis: portability collapses, verification becomes impossible, or governance erodes into convention without enforcement.

## OBLIGATION 1: SECOND-ORDER TOKENS // 02

Artifacts must carry their own procedure instructions. A procedure is named, declared, and acceptance-tested: inputs, outputs, invariants, and "done" criteria are explicit.

Failure mode: behavior exists only inside an implementation; another runtime cannot reproduce it from the corpus.

## OBLIGATION 2: ROUTING LABELS // 03

Every durable artifact declares its classification through a small set of routing labels. Routing labels determine which procedures apply, what evidence is required, what may be emitted, and what checks define completion.

Failure mode: category collapse (draft treated as durable, private treated as personal, packet treated as unbounded dump).

## OBLIGATION 3: COMPACTION TRANSFORMS // 04

High-entropy material is reducible to governed artifacts through explicit transforms. Raw inputs remain quarantined until compacted; derived caches remain rebuildable and non-authoritative.

Failure mode: raw logs become durable state; caches become truth; boundary rules leak under convenience pressure.

## OBLIGATION 4: CERTAINTY MARKING // 05

The protocol maintains a visible distinction between settled and provisional content. Update proposals remain provisional until explicit approval. Durable claims carry derivation markings.

Failure mode: promotion by inertia; provisional material hardens because it is stored.

## OBLIGATION 5: INTEGRITY MARKING // 06

Durable text intended for transport carries a transport-surviving drift signal. This signal is checksum-like: it detects accidental change; it is not adversarial security.

Failure mode: version confusion; packet and trace diverge after copy/paste without detectable signal.

## OBLIGATION 6: CROSS-RUNTIME VERIFICATION // 07

The corpus is testable across different runtimes and toolchains. Conformance is operational: fixtures and regressions define what "compatible" means.

Failure mode: the vendor becomes the spec; behavior drifts with model changes without detection.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026

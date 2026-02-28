# 04 STRUCTURAL OBLIGATIONS (plain-language mirror)

This is a plain-language mirror of: `../normative/04_STRUCTURAL_OBLIGATIONS.md`.
This mirror is not authoritative. If any discrepancy exists, the normative edition governs.

## Overview

A conformant local context pipeline satisfies six minimum requirements. These requirements are what make the corpus a protocol (portable and checkable) rather than a collection of prompts.

Each requirement has a predictable failure mode when missing.

## 1) Artifacts with embedded instructions (second-order tokens)

Artifacts carry their own procedure instructions and acceptance criteria: inputs, outputs, invariants, and "done" conditions are explicit.

Failure mode: behavior exists only inside an implementation; another runtime cannot reproduce it from the text.

## 2) Artifact labels (routing labels)

Durable artifacts declare a small set of labels (authority, audience, verification, boundary, etc.) so the correct procedures and checks can be applied.

Failure mode: category collapse (draft treated as durable; private treated as personal; bounded packet treated as an unbounded dump).

## 3) Explicit transforms (compaction)

High-entropy material is reduced into governed artifacts via explicit transforms. Raw inputs remain quarantined until compacted. Derived indexes remain rebuildable and non-authoritative.

Failure mode: raw logs become durable state; rebuildable indexes become "truth"; boundaries leak under convenience pressure.

## 4) Certainty marking

The system keeps a visible distinction between settled and provisional content. Proposals remain provisional until explicit approval (ratification). Durable claims carry derivation markings.

Failure mode: promotion by inertia; provisional material hardens because it is stored.

## 5) Copy/paste drift check (integrity marking)

Durable text intended for transport carries a transport-surviving drift signal. This is for accidental change detection, not adversarial security.

Failure mode: version confusion; packet and log diverge after copy/paste without detection.

## 6) Cross-runtime verification (conformance)

The protocol is testable across runtimes and toolchains. Compatibility is defined by fixtures and regressions, not by vendor claims.

Failure mode: "the vendor becomes the spec"; behavior drifts with model changes without detection.


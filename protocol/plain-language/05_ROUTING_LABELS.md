# 05 ARTIFACT LABELS (ROUTING LABELS) (plain-language mirror)

This is a plain-language mirror of: `../normative/05_ROUTING_LABELS.md`.
This mirror is not authoritative. If any discrepancy exists, the normative edition governs.

## Purpose

Artifacts are labeled, not guessed. A small set of labels classifies an artifact so the correct procedures, boundary rules, and checks can be applied.

## The label axes (high level)

Each artifact declares:

- Authority: whether it is draft, a local rule, or a spec-level statement.
- Audience: internal vs external (whether it is intended to leave the local environment).
- Verification: the checking posture (structural, checklist, or evidence-bound).
- Context: what sources the artifact depends on.
- Time: whether it is ephemeral, session-scoped, or durable.
- Governance: how strict the workflow is required to be.
- Boundary: personal vs private custody.

## Header shape (in files)

The protocol uses a parseable header:

ROUTING_LABELS:
  Authority:
  Audience:
  Verification:
  Context:
  Time:
  Governance:
  Boundary:
STATUS:
  Lifecycle:
  Epistemic:

The plain-language meaning of these fields is explained above. Exact allowed values and enforcement rules are defined in the normative edition.


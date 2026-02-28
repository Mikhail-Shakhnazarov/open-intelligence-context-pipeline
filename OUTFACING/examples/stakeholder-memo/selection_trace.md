# selection_trace.md -- Stakeholder memo example

> NON-NORMATIVE EXAMPLE: Worked example trace. Normative requirements live in `protocol/`.

ROUTING_LABELS:
  Authority: local_rule
  Audience: internal
  Verification: evidence_bound
  Context: operator_store
  Time: session
  Governance: strong
  Boundary: private
STATUS:
  Lifecycle: provisional
  Epistemic: mixed

TRACE:
  SET_ID: 2026-02-28__stakeholder-memo__001
  Selection policy: "Only settled registries + explicitly referenced decisions"
  Boundary class applied: private + external packet
  Notes: *External emission requires exclusion of raw transcripts and identifiers.*

INCLUSION JUSTIFICATIONS:
  - RECORD_ID: PRJ-001
    Why included: Establishes what the memo is about and who it is for.
    Evidence pointer: registries/entities.md (PRJ-001)

  - RECORD_ID: STYLE-001
    Why included: Prevents drift in tone; enforces marking of uncertainty.
    Evidence pointer: registries/style_contract.md

  - RECORD_ID: DEC-003
    Why included: Memo must reflect already-ratified decisions.
    Evidence pointer: registries/decision_log.md (DEC-003)

MAJOR EXCLUSIONS:
  - RECORD_ID: RAW-TRANSCRIPT-042
    Why excluded: Contains confidential identifiers and detail.
    Risk/impact: Memo will be higher-level; some nuance omitted intentionally.

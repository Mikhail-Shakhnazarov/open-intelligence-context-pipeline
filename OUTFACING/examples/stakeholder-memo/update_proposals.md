# update_proposals.md -- Stakeholder memo example

> NON-NORMATIVE EXAMPLE: Worked example proposals. Normative requirements live in `protocol/`.

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

PROPOSALS:
  - Proposal ID: UPD-001
    Target location: registries/entities.md
    Change type: add
    Derivation: stated
    Proposed text:
      *PRJ-001 -- Add stakeholder "Ops Lead" as a recurring recipient for this memo series.*
    Evidence pointer: Meeting note 2026-02-27 (internal)
    Review trigger / expiry: next weekly review

  - Proposal ID: UPD-002
    Target location: registries/style_contract.md
    Change type: modify
    Derivation: inferred
    Proposed text:
      *Add a default "Open Questions" section for stakeholder memos to reduce back-and-forth.*
    Evidence pointer: observed pattern across last 3 memos
    Review trigger / expiry: next weekly review

RATIFICATION LOG:
  - Proposal ID: UPD-001
    Outcome: deferred
    Date: 2026-02-28
    Notes: *Confirm with project owner before adding recipient.*

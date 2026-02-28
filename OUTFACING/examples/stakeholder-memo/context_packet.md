SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative worked example context packet (stakeholder memo).
Normative: Requirements and definitions live in `protocol/` (this repository).
See: LICENSE.md in the parent directory.

# context_packet.md -- Stakeholder memo example

ROUTING_LABELS:
  Authority: local_rule
  Audience: external
  Verification: evidence_bound
  Context: operator_store
  Time: session
  Governance: strong
  Boundary: private
STATUS:
  Lifecycle: provisional
  Epistemic: mixed

PACKET:
  SET_ID: 2026-02-28__stakeholder-memo__001
  Purpose: Draft a stakeholder memo summarizing project status and next steps.
  Constraints: Use the style contract; do not invent facts; mark uncertainty.
  Budget: ~1 page

INCLUDED CONTEXT:
  - RECORD_ID: PRJ-001
    Label: Project overview
    Origin: registries/entities.md
    Notes: *Defines scope and the stakeholder landscape.*

  - RECORD_ID: STYLE-001
    Label: Output style contract
    Origin: registries/style_contract.md
    Notes: *Governs tone, structure, and forbidden moves.*

  - RECORD_ID: DEC-003
    Label: Latest approved decision
    Origin: registries/decision_log.md
    Notes: *Sets the current "as of" truth for decisions already ratified.*

EXCLUSIONS (OPTIONAL):
  - RECORD_ID: RAW-TRANSCRIPT-042
    Reason: confidential detail
    Notes: *Raw transcript contains client identifiers; excluded from external packet.*

OUTPUT REQUEST:
  - Deliverable: Stakeholder memo
  - Format: Headings + short paragraphs + a small "Open Questions" section
  - Constraints: No client identifiers; no numbers unless present in included context

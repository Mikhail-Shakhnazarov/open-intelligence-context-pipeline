SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative template for proposing durable updates after a session (non-binding until ratified).
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# update_proposals.md (template)

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

PROPOSALS:
  - Proposal ID: <UPD-001>
    Target location: <registries/entities.md / registries/style_contract.md / registries/decision_log.md>
    Change type: <add / modify / delete>
    Derivation: <stated / inferred / assumed>
    Proposed text:
      *<proposal content; stays provisional until ratified>*
    Evidence pointer: <where this came from>
    Review trigger / expiry: <date, event, or "next weekly review">

RATIFICATION LOG (OPTIONAL):
  - Proposal ID: <UPD-001>
    Outcome: <accepted / rejected / deferred>
    Date:
    Notes: *<brief reason>*


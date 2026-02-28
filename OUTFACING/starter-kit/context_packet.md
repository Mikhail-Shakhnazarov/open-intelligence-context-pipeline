# context_packet.md (template)

> NON-NORMATIVE TEMPLATE: Starting point template. Normative requirements live in `protocol/`.

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
  SET_ID: <yyyy-mm-dd__slug__001>
  Purpose: <one sentence>
  Constraints: <style, tone, forbidden moves>
  Budget: <token/character limit>

INCLUDED CONTEXT:
  - RECORD_ID: <ENT-000 / DEC-000 / STYLE-000 / ...>
    Label: <short name>
    Origin: <path or record pointer>
    Notes: *<why this matters for this packet>*

EXCLUSIONS (OPTIONAL):
  - RECORD_ID: <...>
    Reason: <one short reason code>
    Notes: *<optional commentary>*

OUTPUT REQUEST:
  - Deliverable: <what should be produced>
  - Format: <bullets, memo, table, etc.>
  - Constraints: <deadline, audience, length>

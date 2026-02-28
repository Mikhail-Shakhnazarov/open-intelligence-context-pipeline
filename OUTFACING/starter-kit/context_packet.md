SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative template for producing a context packet (one file in a packet set).
Normative: Requirements and definitions live in `protocol/` (this repository).
See: LICENSE.md in this directory.

# context_packet.md (template)

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

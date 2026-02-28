# selection_trace.md (template)

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

TRACE:
  SET_ID: <must match context_packet.md>
  Selection policy: <name/version or short description>
  Boundary class applied: <private/personal; internal/external>
  Notes: *<anything relevant about why the packet is shaped this way>*

INCLUSION JUSTIFICATIONS:
  - RECORD_ID: <...>
    Why included: <reason>
    Evidence pointer: <registry entry / decision log / source record>
    Notes: *<optional>*

MAJOR EXCLUSIONS (OPTIONAL):
  - RECORD_ID: <...>
    Why excluded: <reason>
    Risk/impact: <what changes because it was excluded>

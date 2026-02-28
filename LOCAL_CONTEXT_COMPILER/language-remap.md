---
status: draft
scope: LOCAL_CONTEXT_COMPILER/kernel/*.md
purpose: language remap crosswalk + style guardrails
---

# Language Remap (Draft)

This protocol is written in natural language and executed by a runtime by feeding the protocol text into context. The language is therefore part of the system behavior.

Names must be:

- plain (normal-people readable)
- stable (one concept, one name)
- practical (predicts behavior)
- minimal (new terminology only where necessary)

This file is the authoritative crosswalk from current kernel terms to the preferred terms. After this remap is locked, the kernel is patched to match it.

## Principles

1. Prefer everyday nouns over metaphors.
2. Prefer "what it does" over "what it is like".
3. Keep existing terms when they are already clear (personal, private).
4. If a term is renamed, remove the old term rather than keeping both everywhere; allow a single alias on first mention only.
5. Avoid vendor terms ("memory feature") and anthropomorphic terms ("knows", "intimate") in normative text.

## Canonical term set (preferred words)

| Concept | Canonical term | Definition (1 sentence) |
|---|---|---|
| System | context pipeline | A local system that turns messy inputs into a small task-specific context packet, plus receipts and proposed updates. |
| Output (primary) | context packet | The bounded text payload a runtime consumes for one task. |
| Output (auditability) | selection trace | A receipt explaining why each packet item was included (and major exclusions). |
| Output (state change) | update proposals | Suggested long-term state changes; never applied automatically. |
| Labeling | routing labels | A small header that classifies an artifact so rules and checks can be applied. |
| Verification doc | system audit | Read-only instructions for a runtime to check artifacts and report findings. |
| Transport integrity | integrity marking | A copy/paste-surviving drift check for text artifacts (detects accidental edits). |
| Epistemics | certainty marking | A visible distinction between settled vs tentative text, plus derivation markings. |
| Ingest quarantine | quarantine inbox | Where raw input lands before it is normalized and becomes eligible for reuse. |
| Durable state | long-term state | Governed artifacts that persist across sessions; changed only by explicit approval. |

## Avoid list (deprecated / misleading)

These terms cause confusion or sound like internal jargon. Avoid them in kernel prose and headings.

- compiler, compile, compilation (replace with context pipeline terms)
- coordinate system, coordinates (replace with routing labels)
- intrinsic signage (replace with integrity marking)
- epistemic governance (replace with certainty marking)
- airlock (replace with quarantine inbox)
- memory (when used as a product feature; prefer long-term state)

## Crosswalk (current -> preferred)

| Current kernel term | Replace with | Notes |
|---|---|---|
| Local Context Compiler | context pipeline | Keep "Local Context ..." prefix only where needed; otherwise "the pipeline". |
| compiler | pipeline | "Compiler model" -> "Pipeline model". |
| compilation | packet building | Use "building" for generating a context packet; reserve "approval" for long-term state changes. |
| context pack | context packet | Packet signals a bounded payload; avoid pack as the noun. |
| context pack bundle | context packet set | Set is the 3-file grouping (packet + trace + proposals). |
| explanation trace | selection trace | Selection makes the function explicit. |
| candidate memory updates | update proposals | Candidate is avoidable; memory is overloaded. |
| ratified memory | long-term state (approved) | Optional on first mention: approved long-term state. |
| coordinate system | routing labels | Prefer labels framing; drop geometric language where possible. |
| coordinates | routing labels | In templates, rename the header block label (see below). |
| COORDINATES: (header block) | ROUTING_LABELS: | Preferred for readability; requires a coordinated kernel patch. |
| epistemic governance | certainty marking | Keep derivation markings as-is; rename heading text. |
| intrinsic signage | integrity marking | Keep drift-detection framing. |
| airlock | quarantine inbox | "Airlocked raw capture" -> "quarantined raw capture". |

## Document-level rename targets (kernel)

Headings and filenames should follow the canonical terms:

- kernel/03_SYSTEM_AUDIT.md
- kernel/05_ROUTING_LABELS.md
- kernel/06_CERTAINTY_MARKING.md
- kernel/07_INTEGRITY_MARKING.md
- kernel/09_PIPELINE_MODEL.md

## Protocol tokens and headers (normative)

Two different "language layers" exist:

1. Human-facing terms in prose and headings (must be plain).
2. Machine-facing markers in artifacts (must be stable and parseable).

Preferred direction:

- Use the same phrase for both layers when feasible (avoid one name in prose, another in headers).
- Kernel uses ROUTING_LABELS:. COORDINATES: is deprecated; accept both only during migration (when tooling exists).

## Patch plan (after remap is locked)

1. Patch headings and prose first (low risk).
2. Patch artifact header keys next (COORDINATES: -> ROUTING_LABELS:) as a single coordinated change across kernel docs.
3. Sweep for stragglers: any remaining deprecated terms are removed or explicitly justified.
OPERATOR: MIKHAIL SHAKHNAZAROV
DATE: 26.02.2026
PROJECT: OPEN_IP_DOID

---

# LIVE BUILD — PLANNING SURFACE (DRAFT)

This file is the active planning surface for the repo. It is intentionally not “kernel text”: it is allowed to be incomplete, to contain open questions, and to change frequently. When items here become stable, they should be compacted into durable artifacts (charter, decision register, glossary, conformance tests, repo policy docs).

---

## 0) Mission (current statement)

Create an outward-facing GitHub repository that **projects the OpenIP v1 corpus into an operable project shape**, while keeping the posture “machines for thinking”: we explore first, we compact later. The repo should make it possible to build governed intelligence *for something* once that “something” becomes clear through use.

---

## 1) Working definitions

### “Projection” (repo projection of the corpus)

A projection is a repo structure and set of public artifacts that:

- preserves the kernel/spec as-is (verbatim, attributed, CC BY-SA compliant);
- adds an **ergonomic surface** (docs + templates + workflows + tooling hooks) that compiles back into kernel-grade artifacts without changing kernel semantics;
- makes the protocol *doable* for new users: a clear start path, clear artifact types, clear boundaries (draft vs binding), and a conformance story.

### “Frozen kernel” (OpenIP v1 posture in this repo)

- `the-corpus/` is treated as a stable baseline unless explicitly changed via an operator-authorized patch process (no silent edits).
- All ergonomics live outside the kernel boundary; changes to ergonomics must not redefine kernel obligations.

---

## 2) Constraints (non-negotiables to route decisions)

- Vendor independence is a design requirement (no single-runtime dependency).
- The protocol/spec text is CC BY-SA 4.0; do not create license confusion by mixing spec text into future code paths.
- Trademark boundary: nominative reference allowed; no implied endorsement; do not present the mark as the product name.
- Crypto/tokens boundary: no cryptocurrency/token product; “blockchain” only as infrastructure primitive if used at all.
- Governance boundary: draft/userland must be visibly distinguishable from kernel/spec; promotion is explicit (no silent hardening).

---

## 3) Target repo shape (proposed public layout)

This is a planning target, not yet executed.

- `spec/`
  - Verbatim OpenIP v1 corpus (attributed; CC BY-SA 4.0).
  - Versioning notes and change process for spec-level edits.
- `docs/`
  - Onboarding path (“start here”), mental model (“compiler stance”), and practical how-to.
  - Examples that demonstrate coordinates, promotion boundaries, and conformance checks.
- `profiles/`
  - “Droid profile” drafts: token vocabulary, artifact templates, compaction procedures.
  - Explicit statement: profile ≠ fork; compiles losslessly into kernel-grade artifacts.
- `conformance/`
  - Minimal conformance suite + fixtures (“goldens”) that operationalize “kernel v1 compliant” behaviors.
- `src/` (later phase)
  - Tooling (linter/compiler/promotion assistant; editor integration), under a software license.
- Root policy files (when ready)
  - `README.md`, `LICENSE*`, `NOTICE*`, `CONTRIBUTING.md`, `GOVERNANCE.md`, `TRADEMARKS.md` (names TBD).

Open question: keep `the-corpus/` as the spec location vs move to `spec/` and keep `the-corpus/` as legacy import. (Defer if not needed; keep changes reversible.)

---

## 4) Artifact types we need (projection deliverables)

### 4.1 “Public front door” artifacts

- Project charter (what this repo is, who it is for, non-goals).
- “Start here” onboarding doc: minimum reading + doing path.
- Repo boundary docs: spec vs profile vs tooling; what is binding; what is draft.
- Compatibility statement: “OpenIP v1 compliant implementation + optional Droid profile” (test-backed, not rhetorical).

### 4.2 “Governance machinery” artifacts (still text-first)

- Decision register (durable): what decisions exist, what rationale, and what status.
- Glossary (durable): definitions with promotion rules.
- Token vocabulary (profile): minimal, stable surface syntax for fast capture + linting.
- Compaction transforms (profile): named procedures with inputs/outputs/acceptance criteria.
- Promotion protocol: when a draft becomes binding; what checks block promotion; what evidence is required.

### 4.3 “Conformance” artifacts

- A minimal test suite definition: what behaviors must hold for “kernel v1 compliant” compilation/promotion.
- Golden fixtures: small texts that exercise coordinates, epistemic marking, and drift detection expectations.

---

## 5) Sequencing plan (phased; not a one-shot)

### Phase A — Build-first exploration (now)

Goal: build a minimal public surface that can host exploration, then let compaction and boundaries harden as evidence accumulates.

Checklist:

- Create the minimal directory boundaries (`spec/` or `the-corpus/`, plus `docs/`).
- Publish a “start here” path that invites exploration without pretending the product is already known.
- Create a place to accumulate compactions (decisions/defs/questions) without declaring them binding yet.
- Add the smallest possible conformance placeholder (even if it is just “what we will test later”).

### Phase B — Public skeleton (repo scaffolding)

Goal: create a clean, publishable skeleton with explicit boundaries.

- Create `spec/` (or formalize `the-corpus/`) with attribution + boundary notes.
- Create `docs/` onboarding: short path + examples.
- Create `profiles/` with token vocabulary v0 and compaction transform v0.
- Create `conformance/` with minimal test definition + one golden.
- Add root policy docs for licensing/trademark and contribution posture.

### Phase C — Tooling seed (optional once text substrate is stable)

Goal: smallest useful “governance layer” artifact: lint + compile hooks.

- Define a machine-checkable token grammar (simple; stable under copy/paste).
- Implement a minimal linter that flags missing markers and category violations.
- Implement a compaction/compile transform (session log → decisions/questions/defs).
- Add promotion gating checks (advisory first; blocking at promotion only).

---

## 6) Decision queue (must resolve before Phase B)

This is explicitly *not* a “decide everything now” list. These are decision hooks: only resolve when build pressure forces the choice.

1) Spec placement (only if we need to publish structure):
   - Keep `the-corpus/` as canonical spec dir, or project into `spec/`?

2) Minimal public identity (only if we need a README headline):
   - Repo name + one-paragraph positioning (avoid overcommitment).

3) Minimal Droid profile v0 (only if we need lintable surface syntax):
   - Minimal token vocabulary, unparameterized unless IDs become necessary.

4) Conformance v0 (only if we need credibility for claims):
   - First concrete “kernel v1 compliant” check we can demonstrate.

5) Software licensing (defer until code exists):
   - Choose `src/` license when we actually create `src/`.

---

## 7) Open questions (parked; revisit after Phase A)

- Canonical compiled output format for kernel-grade artifacts (Markdown profile vs strict grammar).
- How strongly to enforce `[FACT]`-style claims in early versions (advisory vs blocking; what counts as evidence).
- Intrinsic signage integration timeline (v0 as concept; v1 as implementation; or keep out until tooling exists).
- Editor integration target (VSCode first?) and what minimal UX proves value to “platform builders building platforms”.



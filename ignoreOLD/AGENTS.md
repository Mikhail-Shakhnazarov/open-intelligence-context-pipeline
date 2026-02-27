# Repository agent guide (vendor-agnostic)

This file exists to make the repository operable for any human or machine agent without repeatedly re-reading the full corpus. It is an orientation + ruleset, not a replacement for the source documents.

Source of truth for protocol semantics: `the-corpus/` (Open Intelligence Protocol v1.0, February 2026). If anything here conflicts with the corpus, the corpus wins.

---

## What this repo currently is

This repository currently contains:

- `the-corpus/`: the published **kernel** documents for the Earmark Open Intelligence Protocol (OpenIP) v1.0.
- `project plan..md`: working compaction notes describing the intended **next project** (provisionally “openip-droid”).
- `live_build.md`: a minimal session header file (operator/date/project).

The intent (per `project plan..md`) is to keep OpenIP v1 as a frozen kernel and build a parallel software project (“openip-droid”) that operationalizes the kernel through tooling (onboarding + editor-integrated governance workflow).

---

## Corpus map (reading order + when to open what)

The corpus is deliberately layered. Recommended reading order for onboarding:

1. `the-corpus/02_PROTOCOL_INTRODUCTION.md` — what this protocol is for.
2. `the-corpus/04_STRUCTURAL_OBLIGATIONS.md` — the six required primitives.
3. `the-corpus/05_COORDINATE_SYSTEM.md` — routing metadata; how artifacts declare “what kind of thing this is”.
4. `the-corpus/06_EPISTEMIC_GOVERNANCE.md` — the roman/italic convention + derivation markings.
5. `the-corpus/08_TERSE_STYLE.md` — style rules; also defines the “dial” inventory that signage can use.
6. `the-corpus/07_INTRINSIC_SIGNAGE.md` and `the-corpus/07a_INTRINSIC_SIGNAGE_ADDENDUM.md` — transport-surviving drift detection via style variation.
7. `the-corpus/01_CORPUS_MANIFEST.md` — license, scope boundaries, versioning rules.
8. `the-corpus/00_THE_INTELLIGENCE_IS_LANGUAGE.md` — the thesis / public argument (useful for messaging; not required for implementation details).

When you are asked to do a task:

- “What is this / why does it exist?” → `02_PROTOCOL_INTRODUCTION.md`
- “What are the non-negotiables?” → `04_STRUCTURAL_OBLIGATIONS.md`
- “What kind of artifact should I produce?” → `05_COORDINATE_SYSTEM.md`
- “What can be considered settled vs provisional?” → `06_EPISTEMIC_GOVERNANCE.md`
- “How should prose be structured?” → `08_TERSE_STYLE.md`
- “How can text self-verify after copy/paste?” → `07_INTRINSIC_SIGNAGE*.md`
- “Can we change the protocol?” → `01_CORPUS_MANIFEST.md` (versioning + “no silent changes”)

---

## Kernel rules for working in this repo

### 1) Treat `the-corpus/` as read-only by default

Assume `the-corpus/` is a frozen kernel unless the operator explicitly requests edits to it. If edits are requested:

- follow the corpus’s “no silent changes” posture (explicit patch + rationale + insertion points);
- preserve authorship attribution and CC BY-SA obligations;
- do not casually rewrite for style—protocol text is normative.

### 2) Vendor independence is a design requirement

Do not introduce requirements that depend on a specific model vendor, a proprietary toolchain, or a single runtime’s quirks. Any implementation guidance should be stated as: “any competent runtime can implement X given Y”, with Y being text-defined procedures and acceptance criteria.

### 3) No crypto/token product boundary

Per `the-corpus/01_CORPUS_MANIFEST.md`: this project will never issue/sell/promote a cryptocurrency or token. If “blockchain” appears, treat it only as an infrastructure primitive (integrity/provenance/coordination), not as a financial product.

### 4) Keep spec text and software licensing separable

The protocol/spec documents are CC BY-SA 4.0. Software in a future `src/` tree will likely require a conventional software license (MIT/Apache-2.0/etc.). Avoid mixing adapted corpus text into code files in a way that confuses licensing. Prefer a clear directory boundary (e.g., `spec/` vs `src/`) once the software project is created.

---

## Protocol essentials (operational summary)

### The “compiler” stance (conceptual)

- The corpus is the specification; the language model is the runtime carrier.
- Durable output should be treated as a compiled artifact: it has declared constraints and an acceptance test, not just “helpful text”.
- Model upgrades are runtime swaps; they require regression checks (cross-runtime verification), not faith.

### The six structural obligations (minimum conditions)

1. **Second-order tokens**: artifacts carry their own compilation instructions (templates/procedures with constraints + how to verify).
2. **Artifact coordinates**: durable artifacts declare routing metadata (authority, audience, verification mode, context source, time horizon, governance cost).
3. **Compaction transforms**: high-entropy material must be reducible to durable artifacts through named procedures with acceptance criteria (airlock rule: raw stays quarantined until compacted).
4. **Epistemic governance**: visibly separate settled vs provisional content (roman vs italic) and require explicit promotion.
5. **Intrinsic signage**: embed transport-surviving drift detection into text via deterministic style dials (checksum-like; not adversarial security).
6. **Cross-runtime verification**: portability is tested by running the same governed corpus against multiple runtimes and checking for consistent/verifiable output.

### Coordinate system (routing metadata)

Axis names and their intent (values listed here are illustrative; use the corpus text as authoritative):

- **Authority**: `draft` / `local rule` / `spec`
- **Audience**: `internal` / `external`
- **Verification**: e.g. `checklist`, `evidence-bound`, `citation-required`, `formal template check`, `external termination`
- **Context source**: `corpus-anchored` / `corpus + cited sources` / `model prior + explicit sources`
- **Time horizon**: `ephemeral` / `session-scoped` / `durable`
- **Governance cost**: `untyped` / `lightly typed` / `strongly typed`

Practical implication: coordinates decide which template applies, what evidence is required, what tone is permitted, and what “done” means.

Suggested header pattern for durable artifacts (keep simple; adjust later if a formal grammar is chosen):

```
COORDINATES:
  Authority:
  Audience:
  Verification:
  Context:
  Time:
  Governance:
```

### Epistemic governance (roman/italic + derivation markings)

- Roman text: binding/ratified (compiled output within the corpus).
- Italic text: commentary/provisional (assumptions, uncertainty, candidate improvements, unresolved gaps).
- Promotion from italic → roman is explicit and requires resolution (decision/test/imported evidence). No automated promotion.
- Claims should carry derivation markings: **Stated** (from an identified source), **Inferred** (derived from evidence), **Assumed** (adopted without direct evidence).

If an agent is asked to *interpret/verify* rather than author:

- treat output as commentary; do not claim governance authority;
- separate non-corpus knowledge from corpus-sourced observations (the corpus’s runtime guidance uses italics for non-corpus content).

### Intrinsic signage (what it is / what it is not)

- Purpose: drift detection that survives copy/paste and channels that strip metadata.
- Mechanism: canonicalize → hash → PRNG sequence → apply dial settings (style variation points) → verify by recomputing and comparing.
- Not cryptographic signing: no keypairs, no non-repudiation; an informed adversary can re-mark.
- Composes with cryptographic signatures if needed: sign the marked text as a file/message, but signage covers the “string in the wild”.

### Terse style (why it matters operationally)

- “Terse” means **density**, not shortness: tokens carry meaning plus relational structure.
- Prefer in-language structure (subordination/coordination/punctuation semantics) over layout where relationships are the point.
- Lists/tables/steps are correct for procedure/comparison/random-access; prose is correct for explanation/synthesis/causal argument.
- The style rules double as the dial inventory that signage can consume: consistency enables deterministic checking.

---

## Intended next project (“openip-droid”) — current working direction

This section summarizes the current working direction captured in `project plan..md`. Treat it as provisional until promoted into a charter/decision register.

### Strategic shape

- OpenIP v1 is treated as a **frozen kernel** (high-governance, high-integrity).
- “openip-droid” is a parallel OSS software project that operationalizes the kernel via onboarding + editor-integrated governance workflow.
- Differentiator: **compaction as precompilation** — reduce raw work into durable artifacts continuously, not as cleanup.

### Working decisions already captured

- Default stance is **compliant implementation + optional “Droid profile”**, not a protocol fork.
  - A fork only exists if normative semantics change (primitive meanings, promotion rules, validity criteria).
  - A profile/dialect is acceptable if it compiles losslessly into kernel-grade artifacts and does not redefine kernel obligations.
- Tooling posture: extension is a **governance layer** (lint/compile/promote), not just UI.
- MVP posture: chat onboarding → compiled artifact bundle; editor highlights tokens, runs lint, supports explicit promotion.

### Draft token system intent (v0)

Inline tokens should be:

- trivially parseable;
- stable under copy/paste and formatting loss;
- ignorable during fast human writing;
- strict enough to support lint/compile rules.

Candidate token classes (illustrative, not yet canonical):

- Epistemic: `[FACT] [INFER] [SPEC]`
- Artifact control: `[DECISION] [QUESTION] [DEF] [RISK] [ASSUMPTION]`
- Lifecycle: `[DRAFT] [PROPOSED] [ACCEPTED] [DEPRECATED]`

### Open questions still live

- Canonical compiled output format for kernel-grade artifacts (Markdown profile? front-matter? strict grammar?).
- Advisory vs blocking governance rules; what promotion gates exist; what `[FACT]` requires.
- Minimal stable token vocabulary; whether parameterization exists from day one.
- Code license choice for future software (`MIT` vs `Apache-2.0` etc.).
- Conformance test suite definition: what “kernel v1 compliant” means operationally.
- MVP scope cut: smallest set of governance functions that prove value without overbuilding.

---

## Practical working defaults (until the new project scaffolding exists)

- Keep new, non-kernel work out of `the-corpus/` unless explicitly instructed.
- When capturing ongoing work, prefer a single “raw” file (session log) plus periodic compaction into named artifacts (decisions, glossary, open questions). Do not import raw transcripts into kernel-grade text.
- If asked to create a new artifact, start by asking for/declaring coordinates; then define the acceptance test (what counts as “done”).


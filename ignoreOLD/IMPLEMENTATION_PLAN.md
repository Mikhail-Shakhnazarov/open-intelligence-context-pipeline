# Implementation Plan — DROID_BY_OPENIP (Draft)

This is a software-first implementation plan for turning the existing OpenIP v1 corpus into an outward-facing GitHub repo that supports exploration, compaction, and eventually governed promotion—without changing kernel semantics.

This plan is written to be followed by an agentic runtime. It is intentionally incremental: build a usable CLI first, then tighten governance, then add editor integration.

---

## 0) Source of truth and boundaries

**Kernel / spec source of truth (read-only by default):**

- `the-corpus/` (OpenIP v1 corpus; CC BY-SA 4.0; February 2026)

**Planning + working direction (non-binding):**

- `live_build.md` (planning surface)
- `project plan..md` (compaction notes / direction)

**Repo-level guardrails (already captured):**

- `AGENTS.md` (orientation + constraints)

Non-negotiables to preserve throughout implementation:

- Vendor independence (no single-runtime dependency).
- No crypto/token product.
- No silent hardening: draft/userland vs durable/binding must be visible; promotion is explicit.
- Do not modify `the-corpus/` unless explicitly instructed and done as an operator-authorized patch.

---

## 1) Product framing (software project)

### 1.1 What “Droid” is (v0–v1)

An OSS toolchain that provides:

- **Capture surface**: accept messy working Markdown (session logs).
- **Lint**: identify missing structure (tokens/coordinates/status) and category violations.
- **Compaction**: deterministically reduce a session log into durable, queryable artifacts (decisions, questions, definitions).
- **Promotion**: explicitly elevate draft/userland artifacts into “durable” form (coordinates header + status + checklist) without rewriting the kernel.
- **Verification**: run conformance checks over fixtures to keep behavior stable across changes/runtimes.

### 1.2 What “Droid” is not (v0)

- Not a hosted service.
- Not a model-vendor feature.
- Not a protocol fork (unless normative semantics change—out of scope for v0).
- Not an intrinsic-signage implementation in v0 (can be planned; implement when the dial table + canonicalization rules are stable).

---

## 2) Repo projection: target structure (minimal, outward-facing)

Create these directories (names are intentionally plain; change later if needed):

- `the-corpus/` (already present): verbatim kernel/spec (read-only posture).
- `docs/`: outward-facing onboarding and examples (human-first).
- `profiles/`: “Droid profile” (token vocabulary + compaction/promotion procedures).
- `workbench/`: raw working captures (session logs) and their compacted outputs (operator-controlled; can be gitignored later).
- `conformance/`: fixtures + expected outputs; deterministic tests.
- `src/` or `packages/`: software implementation (chosen by stack).

Initial root docs (v0):

- `README.md` (1 page; minimal).
- `IMPLEMENTATION_PLAN.md` (this file).
- `AGENTS.md` (already present).

---

## 3) Stack decision (choose one lane; keep reversible)

This plan supports two lanes. Pick **Lane A** unless there is a strong reason not to.

### Lane A (recommended): TypeScript + Node CLI

Why:

- Smooth path to VSCode extension later (same language/tooling).
- Cross-platform.
- Strong Markdown tooling ecosystem (remark/unified).

Baseline toolchain:

- Node.js LTS (20+).
- Package manager: `npm` (keep simple).
- Testing: Node built-in `node:test` + `assert` (avoid heavy frameworks).

Dependencies (keep minimal):

- `commander` (CLI parsing) **or** minimal manual parsing.
- `gray-matter` (optional) if we adopt frontmatter later.
- `remark` ecosystem (optional) if we need AST-level Markdown parsing; v0 can be line-based.

### Lane B (alternative): Python CLI

Why:

- Fast iteration for text transforms.
- No TS build step.

Baseline toolchain:

- Python 3.11+.
- Testing: `pytest`.

Choose Lane B only if editor integration is explicitly deferred and Python is preferred operationally.

Implementation steps below assume **Lane A**; where it matters, annotate Lane B equivalents.

---

## 4) Data model (v0): minimal typed surface

### 4.1 Token syntax (v0)

Tokens are plain, copy/paste-safe bracket tags at line start:

- Artifact-kind tokens (required for compacted outputs):
  - `[DECISION]`, `[QUESTION]`, `[DEF]`
- Epistemic tokens (optional in v0; advisory lint only):
  - `[FACT]`, `[INFER]`, `[ASSUME]`
- Lifecycle tokens (optional in v0; used by promote):
  - `[DRAFT]`, `[PROPOSED]`, `[ACCEPTED]`, `[DEPRECATED]`

Minimal rule (v0):

- Token must be the first non-whitespace on a line.
- Token is uppercase A–Z plus underscore.
- Token may be followed by a space and then text.

Deferral:

- Parameterization like `[DECISION id=...]` is deferred until we actually need stable IDs.

### 4.2 Coordinates header (v0)

For “durable” artifacts produced by promote (not for raw session logs), use a simple, parseable header:

```
COORDINATES:
  Authority:
  Audience:
  Verification:
  Context:
  Time:
  Governance:
STATUS:
  Lifecycle:
  Epistemic:
```

Rules:

- Fields may be blank in v0, but lint will warn if missing for “durable” files.
- The header must occur at the top of the file, before content.

### 4.3 Artifact file types (v0)

We standardize three compacted outputs (each is Markdown):

- `decisions.md` — list of decisions as items.
- `questions.md` — list of open questions as items.
- `defs.md` — list of definitions as items.

Each item format (v0):

- One item starts with an artifact token line: `[DECISION] ...`
- Item body is subsequent indented lines until next token line or EOF.

This keeps parsing deterministic without needing full Markdown AST.

---

## 5) Commands (CLI UX): what “done” looks like

CLI name: `droid` (placeholder; rename later if needed).

### 5.1 `droid lint <file-or-dir>`

Checks (v0):

- Token validity: unknown tokens, lowercase tags, tags not at line start.
- “Durable header” presence: if file is in `profiles/` or `docs/` marked durable (rule: filename contains `durable` or frontmatter flag later), require `COORDINATES:` block.
- Category violations (basic): files under `the-corpus/` must not be modified by tooling; if lint sees tokens suggesting Droid profile inside `the-corpus/`, warn.

Output:

- Human-readable list of findings with file:line.
- Exit code non-zero if “errors” exist; warnings do not fail by default.

Acceptance criteria:

- Running lint on fixtures produces stable results.

### 5.2 `droid compact <session-log.md> --out <dir>`

Goal:

- Produce `decisions.md`, `questions.md`, `defs.md` deterministically.

Algorithm (v0, deterministic, rule-based):

- Scan session log for lines starting with `[DECISION]`, `[QUESTION]`, `[DEF]`.
- Group token line + following lines until next token line (any of the three) or EOF.
- Write grouped items into the corresponding output file, preserving order.

If no items exist for a type, still write an empty file with a header (so downstream tools can rely on presence).

Acceptance criteria:

- Same input yields identical outputs (byte-for-byte).
- No network calls.
- Does not rewrite input file.

### 5.3 `droid promote <file> --to durable`

Goal:

- Turn a draft/userland file into a durable artifact by adding the coordinates + status header if absent, and by applying minimal structural checks.

Rules (v0):

- If header is missing, insert the `COORDINATES:` + `STATUS:` block at top.
- Do not fill values automatically unless the user supplies flags (defer).
- Optionally add a `PROMOTION:` line with timestamp and source file path (local provenance; keep minimal).

Acceptance criteria:

- Promotion is explicit: command must be invoked; no implicit upgrades.

### 5.4 `droid verify`

Goal:

- Run conformance suite deterministically.

Checks (v0):

- `lint` passes on fixtures with expected warning set.
- `compact` output matches expected files for fixtures.

Acceptance criteria:

- CI-friendly: one command, stable exit codes.

---

## 6) Conformance suite (v0): fixtures and goldens

### 6.1 Directory layout

- `conformance/fixtures/`
  - `session_minimal.md`
  - `session_mixed.md`
  - `session_empty.md`
- `conformance/expected/`
  - `session_minimal/decisions.md`
  - `session_minimal/questions.md`
  - `session_minimal/defs.md`
  - etc.

### 6.2 What a fixture should cover

Minimal set:

- One decision + one question + one definition.
- Multi-paragraph item bodies.
- Items interleaved in source.
- Unknown token should trigger warning (lint).

### 6.3 Test harness

Lane A:

- Use `node:test` and snapshot-like byte comparison of output files.

Lane B:

- Use `pytest` with golden file comparison.

---

## 7) Implementation steps (agent-executable)

This section is the step-by-step work order an agentic runtime should follow.

### Step 1 — Scaffold directories and minimal docs

1. Create directories: `docs/`, `profiles/`, `workbench/`, `conformance/fixtures/`, `conformance/expected/`.
2. Add `docs/START_HERE.md` with:
   - What the repo is (1 page).
   - A “first run” path: run `droid verify`, run `droid compact` on a fixture.
   - A boundary note: kernel in `the-corpus/`, droid profile elsewhere.
3. Add `profiles/TOKENS_v0.md` describing the v0 token set and rules (copy from Section 4.1, adapted).
4. Add `profiles/COMPACTION_v0.md` describing the deterministic compaction procedure and acceptance criteria.

Stop condition:

- Repo has a visible public surface even before code exists.

### Step 2 — Initialize Lane A toolchain (TypeScript CLI)

1. Create `package.json` with:
   - `type`: `module` (or commonjs; choose one).
   - scripts:
     - `droid`: run CLI (dev).
     - `test`: run `node --test`.
2. Create `src/` with:
   - `src/cli.ts` (argument parsing and subcommands).
   - `src/lint.ts`
   - `src/compact.ts`
   - `src/promote.ts`
   - `src/verify.ts` (or route verify to tests).
   - `src/fs.ts` (safe file ops helpers).
   - `src/tokens.ts` (token definitions and parsing).
3. Provide a runnable entrypoint:
   - `bin/droid` script (Node shebang) or `npm run droid -- ...` as a first step.

Stop condition:

- `npm test` runs (even if tests are empty initially).

### Step 3 — Implement token parsing (core engine)

Implement in `src/tokens.ts`:

- `isTokenLine(line): { token: string, rest: string } | null`
- `TOKEN_SETS` (artifact tokens, lifecycle tokens, epistemic tokens)
- `parseItems(text): Item[]` for artifact tokens only:
  - each item has `kind`, `headerLine`, `bodyLines`, `startLine`, `endLine`.

Stop condition:

- Unit tests for token parsing pass.

### Step 4 — Implement `lint`

Implement `src/lint.ts`:

- Check unknown tokens at line start.
- Check token capitalization.
- Check “durable header” presence when file matches a rule:
  - v0 heuristic: files under `profiles/` must include `COORDINATES:` block if they claim durable status (initially: no requirement; only warn).

Add tests with fixtures.

Stop condition:

- `droid lint conformance/fixtures/session_minimal.md` returns expected zero errors.

### Step 5 — Implement `compact`

Implement `src/compact.ts`:

- Read session log.
- Extract items for `[DECISION]`, `[QUESTION]`, `[DEF]`.
- Write outputs to `--out` directory with deterministic order.

Add fixtures + expected outputs and tests.

Stop condition:

- `droid compact conformance/fixtures/session_mixed.md --out tmp/` matches goldens.

### Step 6 — Implement `promote`

Implement `src/promote.ts`:

- Detect whether coordinates header exists.
- If missing, insert at top with blank fields.
- Optionally insert a `PROMOTION:` block with timestamp and command parameters (keep stable formatting).

Add tests:

- Promote a small file and ensure header insertion is correct and idempotent (running twice does not duplicate header).

Stop condition:

- `droid promote workbench/example.md --to durable` is deterministic and idempotent.

### Step 7 — Implement `verify` and CI wiring

Implement `droid verify`:

- Option A: run internal checks (lint+compact) over fixtures and compare to expected outputs.
- Option B: delegate to `npm test` (simpler; verify becomes a thin wrapper).

Add a GitHub Actions workflow (optional at v0 if repo is not yet public).

Stop condition:

- One command runs the full deterministic suite.

---

## 8) Phase 2 (after v0): tightening governance without overdefining

Only do these once the v0 loop is useful.

### 8.1 Stabilize IDs (if needed)

If items need durable references:

- Add optional parameterization: `[DECISION id=YYYYMMDD-XX] ...`
- Add a helper command: `droid id` or `droid normalize` to assign IDs deterministically (careful: avoid nondeterminism).

### 8.2 Stronger coordinate enforcement (promotion gates)

Make promotion require:

- Coordinates fields filled (at least Authority/Audience/Time/Governance).
- Lifecycle status set (e.g., `PROPOSED`).
- Optional epistemic markings for high-stakes claims (advisory first).

### 8.3 Intrinsic signage integration (separate package)

Do not implement signage until:

- canonicalization rules are fixed,
- dial inventory is codified,
- and fixtures exist for marking/verification.

When implemented, keep it in a separate module/package with a declared profile.

### 8.4 Editor integration (VSCode extension)

Once CLI is stable:

- Highlight tokens.
- Provide “compact selection/file” command.
- Provide “promote” UI with checklist.
- Show lint diagnostics inline.

---

## 9) Risks and mitigations (engineering)

- **Over-governance early** → keep lint advisory by default; only block at promotion.
- **Semantic drift** → keep kernel read-only; keep profile docs explicit: “profile compiles to kernel”.
- **Nondeterminism** → keep compaction rule-based in v0; add LLM-assisted compaction only behind flags and with “draft output” posture.
- **License confusion** → do not copy kernel text into code files; keep references as links/paths.

---

## 10) “Ready to implement” checklist

An agentic runtime should start implementation when:

- Lane A (TS) or Lane B (Python) is selected.
- The v0 token vocabulary is accepted as provisional but usable.
- The deterministic compaction outputs (`decisions.md`, `questions.md`, `defs.md`) are accepted as the v0 artifact surface.

If any of these are disputed, resolve minimally and proceed; do not block the build on perfect definitions.


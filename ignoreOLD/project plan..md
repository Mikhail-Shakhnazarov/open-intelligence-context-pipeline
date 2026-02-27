## Extended compaction (chat-to-date)

### Project frame

OpenIP v1 (the existing corpus) is treated as a frozen kernel: high-governance, high-integrity, not optimized for onboarding. A parallel project is created: **openip-droid**, positioned as open-source software that operationalizes the kernel through guided onboarding and an editor-integrated governance workflow. The differentiator is **compaction as precompilation**: ongoing work is continuously reduced into durable artifacts (decisions, definitions, open questions, dependencies), making continuity and drift-control a byproduct of work rather than an after-the-fact cleanup.

### Core strategic claim

“Context management is obvious” is not the value; the value is **precompilation of context while work happens**. Terse documentation and disciplined surface language are not “style”; they function as an executable interface layer: they enable deterministic compaction, drift detection, and promotion boundaries. The project becomes an accumulator of authority: use produces substrate; substrate reduces future work; artifacts become portable across runtimes and sessions.

### Decisions captured

- OpenIP **v1** is kernel and is left in place (frozen baseline).
    
- A forked parallel project is created instead of mutating v1.
    
- Internal name: **openip-droid**.
    
- Onboarding surface: **chat interface** that guides usage.
    
- Primary workspace integration: **VSCode-like surface** (Codex-extension model).
    
- The extension is explicitly a **governance layer** (lint/compile/promote), not merely UI.
    
- Target audience: **platform builders building platforms for people building with AI** (upstack).
    
- Language strategy: **capture the language**; avoid technobabble; use clear practical descriptive terminology.
    
- Adoption strategy: “attack the top by capturing the bottom”: friendly to regular users while selling upstack.
    
- Protocol already published; assume unknown observers; anticipate “art where there was science” misread; messaging must emphasize observable/measurable properties.
    
- Status marking mechanism in droid: **inline tokens** (machine-checkable, human-ignorable).
    
- openip-droid is decided **open source**.
    
- Protocol/spec documents are published under **CC BY-SA 4.0** with explicit boundary: protocol documents are covered; operator-produced outputs are not; trademark rights are not granted; forks must use distinct naming and avoid presenting the mark as the product name.
    

### Fork vs compliance (resolved stance)

Default interpretation: **compliant implementation + optional “Droid profile,” not a protocol fork**. A fork exists only if normative semantics change (primitive meanings, promotion rules, validity criteria). A profile/dialect is acceptable if it compiles losslessly into kernel-grade artifacts and does not redefine kernel obligations. This keeps the published protocol stable and lets openip-droid move fast on ergonomics.

### Governance architecture (kernel/userland with promotion)

Kernel remains strict and authoritative; droid provides userland ergonomics and compilation paths back to kernel artifacts. The enforcement boundary sits at **promotion**: advisory linting during capture/authoring; stricter gating when promoting artifacts to kernel-grade status. No silent hardening: moving from draft/userland to kernel-grade is an explicit event with traceable transformations.

### Token system (v0 intent)

Inline tokens are introduced as the droid-friendly surface syntax. They must remain: (a) trivially parseable, (b) stable under copy/paste and formatting loss, (c) ignorable to humans during fast writing, and (d) strict enough to support lint/compile rules. Candidate token classes were outlined: epistemic (`[FACT] [INFER] [SPEC]`), artifact control (`[DECISION] [QUESTION] [DEF] [RISK] [ASSUMPTION]`), lifecycle (`[DRAFT] [PROPOSED] [ACCEPTED] [DEPRECATED]`), optionally parameterized later (`id=…`).

### MVP shape (aligned to audience)

MVP is an onboarding-to-artifact pipeline that demonstrates governance value to platform builders:

- Chat onboarding generates an initial bundle: project charter + decision register + glossary patch + open questions backlog (from raw conversation).
    
- VSCode extension highlights tokens, runs lint checks (status consistency, missing markers, ambiguous claims), compiles session notes into artifacts, and supports explicit promotion to kernel-grade files.
    
- Regular-user friendliness is preserved by accepting plain prose and suggesting structure, with one-click compaction templates (“turn this into decisions + questions + definitions”).
    

### Monetization paths discussed (to keep in view despite “open source”)

Making the core tool free/open is coherent with adoption-as-moat; funding must live at high-value edges that do not corrupt the protocol.

1. **Paid hosted service (“Governance Cloud”)**: team policies, shared registries, audit trails, approvals/promotion workflows, cross-repo indexing, access control/SSO, analytics, SLAs.
    
2. **Enterprise support/implementation**: onboarding, custom rulesets, CI integration, training, incident support.
    
3. **Certification/conformance program**: paid conformance testing and compatibility reports/badges.
    
4. **OEM/embedding license (phase 2)**: commercial track for embedding in proprietary platforms, priority roadmap influence (only if licensing posture supports it).
    
5. **Donations/sponsorship**: supplementary runway, not primary plan.
    

Recommended direction given the strategy: keep tooling open and maximize adoption; monetize collaboration/compliance infrastructure (Cloud) and support first; consider embedding/OEM later once the kernel profile stabilizes.

### Licensing implications (spec vs code separation)

Because protocol/spec text is **CC BY-SA**, and code needs a standard OSS software license, repository separation is required to avoid license contamination:

- `/spec` or `/protocol`: verbatim corpus + any adapted spec text (CC BY-SA with attribution/change marking).
    
- `/docs`: if derived/adapted from corpus, also CC BY-SA; if net-new explanatory material referencing the corpus, can be separately licensed but must not misrepresent the kernel.
    
- `/src`: extension/compiler/linter/verifier under a software license (Apache-2.0 or MIT were floated as adoption-friendly defaults for platform builders).  
    Trademark policy and conformance claims matter: nominative reference without implied endorsement; compatibility language should be explicit and test-backed.
    

### Messaging constraint (published protocol + misread risk)

Positioning must make the “science” legible: show lint outputs, compiled artifacts, promotion diffs, conformance tests, drift detection signals. Avoid narrative that sounds like a manifesto; emphasize operational benefits: continuity, reduced context loss, governance separation, transport resilience, auditable promotion.

### Risks noted (from the same strengths)

- Semantic drift if “friendliness” changes meanings rather than surface ergonomics.
    
- Authority dilution if draft/userland outputs become indistinguishable from kernel-grade artifacts.
    
- Governance drag if kernel-grade changes require heavy process without tooling support.
    
- Legal/brand ambiguity if CC BY-SA spec text is mixed under code license or if trademark boundaries are not enforced via policy and conformance.
    

### Open questions (still live)

- Canonical compiled output format for kernel-grade artifacts (Markdown profile + front-matter vs strict grammar).
    
- Governance boundary: advisory vs blocking rules; when `[FACT]` requires support; what triggers promotion gates.
    
- Minimal stable token vocabulary and whether parameterization exists from day one.
    
- Code license choice for `/src` (Apache-2.0 vs MIT vs other) given the target audience.
    
- Funding surface prioritization (Cloud vs support vs conformance vs embedding) and sequencing.
    
- Public compatibility statement format and conformance test suite definition.
    
- MVP scope cut: which governance functions ship first to prove value to platform builders without overbuilding.
    

### Immediate next artifacts implied

1. **openip-droid Charter v0**: purpose, audience, non-goals, decision register, token set v0, MVP scope, compatibility stance (“profile, not fork”), funding hypothesis.
    
2. **Conformance skeleton**: minimal golden tests + fixtures defining what “kernel v1 compliant” means in compiled output.
    
3. **Repo license layout**: explicit directory-level licensing/NOTICE so CC BY-SA spec/docs and code license cannot be confused.
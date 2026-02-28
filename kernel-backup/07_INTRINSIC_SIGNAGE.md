# 07 INTRINSIC SIGNAGE

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT COMPILER PROTOCOL
- INTRINSIC SIGNAGE
- CONTENT-DERIVED VERIFICATION THROUGH STYLE VARIATION
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## THE PROBLEM // 01

Context packs are transported as text through channels that strip metadata (chat boxes, email, copy/paste, API payloads). A protocol that relies on container signatures alone loses integrity signals at the first paste.

Intrinsic signage provides transport-surviving drift detection by encoding a content-derived pattern into a text's surface form. The mechanism detects accidental change; it does not prevent adversarial re-marking.

## THE MECHANISM // 02

Intrinsic signage operates by:

1. Canonicalization: normalize all dial instances to canonical form.
2. Hashing: hash the canonical text to a digest.
3. Sequence generation: use the digest to seed a PRNG to generate expected dial settings.
4. Dial application: apply the expected settings to produce a marked text.

Inputs required for interoperability:

- dial definition table (provided by the style system),
- hash function identifier,
- PRNG identifier.

These inputs constitute a signing profile.

## VERIFICATION // 03

Verification reverses the process: read observed dial settings, canonicalize, hash, generate expected settings, and compare expected vs observed per dial position.

Mismatch classifications:

- Local mismatch: isolated mismatches; suggests localized edits or corruption.
- Cascade: a contiguous mismatch region beginning at a point; suggests content divergence.
- Category violation: observed pattern matches a different signing profile than declared or expected.
- Full match: all dial positions match expected settings.

## WHAT THIS IS NOT // 04

This is not cryptographic signing. There is no non-repudiation. An informed adversary can re-mark modified text if the signing profile is known.

This is not a substitute for version control. It complements version control by surviving transport outside repositories and file containers.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026


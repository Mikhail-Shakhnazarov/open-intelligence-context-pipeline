# 07a INTRINSIC SIGNAGE -- EXPLANATORY ADDENDUM

## METADATA // 00

- MACHINES FOR THINKING
- INTRINSIC SIGNAGE -- EXPLANATORY ADDENDUM
- WHAT IT IS, WHY IT MATTERS, AND WHERE IT APPLIES
- EARMARK OPEN INTELLIGENCE PROTOCOL
- AUTHOR: MIKHAIL SHAKHNAZAROV
- BERLIN, FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- TRADEMARKS: SEE README.md#TRADEMARKS
- https://creativecommons.org/licenses/by-sa/4.0/

## WHAT THIS DOCUMENT IS // 01

This addendum accompanies the Intrinsic Signage specification. The specification defines the mechanism; this document explains what the mechanism is for, what existing approaches it complements, and where it applies. The audience is anyone evaluating whether intrinsic signage solves a problem they have -- not just those implementing it.

## THE GAP // 02

Images and video now have transport-surviving provenance through standards like C2PA: metadata embedded in the content itself, verifiable without contacting an external authority. Text has no equivalent. Digital signatures verify files, not strings. Watermarking requires vendor cooperation and degrades output. External registries require infrastructure and the text to be registered before verification is possible. All of these fail when text is copied, pasted, emailed, quoted, or inserted into a prompt -- which is how most text actually moves.

Language models have made this gap urgent. LLM-generated text is unsigned by default. The text does not announce what produced it, what constraints governed its production, or whether it has been modified since generation. Organizations generating governed text -- compliance filings, clinical documentation, legal drafts, editorial content -- have no lightweight mechanism to verify that the text they are reviewing is the text the governance system approved. The integrity chain breaks at the first copy-paste.

## WHAT INTRINSIC SIGNAGE DOES // 03

Intrinsic signage encodes a verification pattern into the stylistic surface of a text -- choices like colon versus period, demonstrative versus repetition, subordination versus coordination -- that preserve meaning while varying form. The pattern is derived from a hash of the text's own content, so changes to the text produce detectable changes in the pattern. The mechanism is a deterministic script: signing uses a language model to produce natural-sounding text that conforms to the pattern; verification requires only pattern matching and hash comparison. No AI is needed to verify. No vendor cooperation is needed to sign. No infrastructure is needed to check.

The mechanism operates at the same trust level as a checksum. It does not prevent tampering; it detects accidental change -- drift, copy error, version confusion, unauthorized edit, model behavior divergence. Most integrity failures are accidental, not adversarial. For adversarial contexts, intrinsic signage composes with cryptographic signing: sign the marked text with a keypair, and the signature covers both the content and the intrinsic pattern.

## USE CASES // 04

**Regulatory compliance.** An organization uses an LLM to draft text for a regulatory filing. The governance system approves a specific version. The approved text is signed using intrinsic signage. At any later point -- after the text has been emailed, pasted into a submission form, or moved through an approval chain -- verification confirms whether the filed text matches the approved text. No external registry required; the text carries its own integrity signal.

**Editorial integrity.** A publication generates or edits text using LLM assistance under an editorial governance regime. The signed text travels through the publication pipeline -- editors, layout, legal review. Intrinsic signage detects whether the text was altered at any stage, without requiring every participant in the pipeline to use the same tools or maintain access to a shared repository.

**Output attribution.** An organization operates multiple LLM configurations -- different governance regimes for different purposes. Intrinsic signage uses different signing profiles for different regimes, producing mechanically distinguishable patterns. Text can be verified as belonging to a specific governance category without accessing the system that produced it. This distinguishes governed output from unverified output, and one governance regime from another, by pattern alone.

**Contract and legal text.** Parties exchange drafted text through email, messaging, and document platforms. Intrinsic signage detects whether the text received matches the text sent, without requiring both parties to use the same document management system or maintain a shared signature registry. The verification is symmetric: either party can check, using the same script, without trusting the other's infrastructure.

## CONFORMANCE LEVELS // 05

The mechanism supports three levels of verification, each composing on the previous.

**Level 1 -- Integrity.** Has this text changed since marking? Binary: the pattern matches or it does not. This is the minimum useful deployment. It requires a single signing profile and a verification script.

**Level 2 -- Category differentiation.** Does this text belong to the category it claims? Different text categories use different signing profiles, producing different patterns. Verification determines not only whether the text has changed but whether it was produced under the expected governance regime. This requires multiple signing profiles within a corpus.

**Level 3 -- Provenance typing.** Was this text produced under a specific, identified governance regime, distinguishable from ungoverned output? The signing profile itself becomes a provenance marker: text signed under Profile A is mechanically distinguishable from text signed under Profile B, from unsigned text, and from text that mimics a profile without conforming to it. This requires published or exchanged signing profiles between parties.

## RELATIONSHIP TO EXISTING STANDARDS // 06

Intrinsic signage does not compete with existing provenance and integrity standards; it covers the medium they do not address.

C2PA provides content provenance for images, video, and audio through embedded metadata. Intrinsic signage provides content provenance for text through embedded style patterns. The two mechanisms are complementary; a document containing both images and text could use C2PA for images and intrinsic signage for text, providing provenance across media types.

Digital signatures (PGP, X.509) verify files and messages within container formats. Intrinsic signage verifies text that has left its container. The two compose: a digitally signed document provides strong provenance within the signing infrastructure; intrinsic signage provides weaker but transport-surviving provenance outside it.

Watermarking (vendor-side LLM watermarks) requires vendor cooperation, is specific to the generating model, and degrades with paraphrase. Intrinsic signage requires no vendor cooperation, is model-independent (any runtime can produce conforming text), and operates on stylistic features that are more robust to minor edits than statistical watermarking. The two mechanisms solve different problems: watermarking identifies the generating model; intrinsic signage verifies conformance to a governance regime.

CC BY-SA 4.0 -- Mikhail Shakhnazarov, Berlin, February 2026

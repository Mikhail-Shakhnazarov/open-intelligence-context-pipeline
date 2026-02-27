# 07 INTRINSIC SIGNAGE

## METADATA // 00

- MACHINES FOR THINKING
- INTRINSIC SIGNAGE
- CONTENT-DERIVED VERIFICATION THROUGH STYLE VARIATION
- EARMARK OPEN INTELLIGENCE PROTOCOL
- AUTHOR: MIKHAIL SHAKHNAZAROV
- BERLIN, FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- TRADEMARKS: SEE README.md#TRADEMARKS
- https://creativecommons.org/licenses/by-sa/4.0/

## THE PROBLEM // 01

Text is the one major content type with no transport-surviving provenance mechanism; intrinsic signage provides one, requiring no vendor cooperation, no external infrastructure, and no AI to verify.

Text moves through channels that strip container metadata: chat windows, email, copy-paste, prompt boxes, API calls. Verification mechanisms that depend on metadata -- headers, watermarks, external registries, container signatures -- fail at the boundary of these channels. The text arrives but the verification does not.

A governed corpus requires verification that survives transport. The verification must therefore be intrinsic to the text: encoded in the text's own surface form rather than attached to it. Changes to the text must produce detectable changes in the verification signal. The mechanism must not depend on vendor cooperation, institutional trust, or any infrastructure beyond the text itself.

## THE MECHANISM // 02

Intrinsic signage encodes a content-derived pattern into the stylistic surface of a text through four operations: canonicalization, hashing, sequence generation, and dial application. The mechanism is a deterministic script -- not a natural-language analysis process -- that operates on text as structured input according to a declared dial definition.

### Dials

A dial is an observable choice in a text that can be toggled without changing semantic content. Every dial has a defined identification pattern (how to locate the dial in the text), a canonical form (the normalized position used for hashing), and one or more alternate forms (the positions the dial can be set to). Dials are defined by the style system in use; the signage mechanism consumes dial definitions but does not generate them.

### Dial definitions

A dial definition is the interface between a style system and the signage mechanism. Each definition must specify: a dial type identifier, the identification pattern (what the script matches against in the text), the canonical form (the default position to which all instances are normalized before hashing), the set of alternate forms (the valid positions the dial can be set to), and the form count (the number of valid positions, which determines the information density of the dial -- a binary dial carries one bit; a ternary dial carries log2(3) bits). A conforming style system provides a dial definition table containing all dial types it declares. The signage mechanism requires nothing from the style system except this table.

### Canonicalization

Given a text and a dial definition table, canonicalization normalizes every dial instance to its canonical form. The script identifies all dial positions by matching against identification patterns, then sets each to canonical form. The result is a canonical text that is semantically identical to the original but stylistically uniform -- all variation has been removed. Two texts that differ only in dial settings produce the same canonical form.

### Hashing

The canonical text is hashed to produce a fixed-length digest. The hash function must be declared in the signing profile (the combination of dial definition table, hash function, and PRNG that constitutes a complete signing configuration). The hash binds the pattern to the content: any change to the semantic content changes the canonical form, which changes the hash, which changes the expected dial sequence.

### Sequence generation

The hash is used as a seed for a declared pseudo-random number generator. The PRNG produces a sequence of values, one per dial position in the text, each selecting a form from the dial's set of alternate forms. The sequence is deterministic: same hash, same PRNG, same sequence. The sequence length equals the number of dial positions identified in the text.

### Dial application

The script walks the text in document order, visiting each dial position as identified during canonicalization. At each position, the script sets the dial to the form selected by the corresponding value in the generated sequence. The result is a marked text: semantically identical to the input, but carrying an embedded pattern of stylistic choices derived from its own content.

## VERIFICATION // 03

Verification reverses the process. Given a marked text and the same signing profile, the script identifies all dial positions, reads their current settings, canonicalizes, hashes, generates the expected sequence, and compares expected settings against observed settings. Verification produces a binary result per dial position (match or mismatch) and an aggregate classification.

### Mismatch types

Local mismatch: a small number of dials show unexpected settings while surrounding dials match. Indicates manual edit, copy error, or localized corruption. The affected region is identifiable from the mismatch positions.

Cascade: a large contiguous region of mismatches beginning at a point in the text. Indicates content change -- the canonical text differs from the marked text, producing a different hash and therefore a different expected sequence from the point of divergence onward.

Category violation: the text's dial settings match a pattern, but the pattern corresponds to a different dial definition table than expected. Indicates text marked under one style system appearing in a context governed by another.

Full match: all observed settings match expected settings. The text has not changed from its marked state and belongs to the expected category.

## SIGNING PROFILES // 04

A signing profile is the complete configuration required to mark and verify text. It comprises: a dial definition table (provided by the style system), a hash function identifier, and a PRNG algorithm identifier. Two implementations using the same signing profile will produce identical marked text from identical input and identical verification results from identical marked text. Interoperability requires agreement on the signing profile; the signage mechanism itself is profile-agnostic.

A signing profile should be declared in or alongside any artifact that carries intrinsic signage, so that verification is possible without external coordination. The profile declaration is itself metadata that can be stripped by transport -- but because the profile is agreed upon within a governed corpus (and typically stable across the entire corpus), the verifier can reconstruct it from corpus-level configuration rather than per-artifact metadata.

## CATEGORY DIFFERENTIATION // 05

Different text categories can use different signing profiles -- different dial definition tables, or the same table with different canonical forms -- producing different patterns that are mechanically distinguishable. The signage mechanism does not define categories; it provides the machinery for categories to be distinguished through pattern. The governing corpus defines which categories exist and which signing profile each uses.

Typical category distinctions: kernel text (governance rules, definitions -- minimal dial space, high stability) vs operational text (content produced under governance -- full dial family) vs draft text (work in progress -- unsigned or unstably signed) vs model output (runtime-generated text -- verifiable against the corpus's expected patterns to detect drift into generic behavior).

## WHAT THIS IS NOT // 06

This is not cryptographic signing. There is no keypair, no non-repudiation, no protection against adversarial re-marking. An attacker who knows the signing profile can modify text and re-sign it. The mechanism is drift detection: it identifies accidental change, not deliberate forgery.

This is not a replacement for version control. It complements version control by making integrity signals travel with the text through channels where version metadata does not survive.

This is not dependent on any particular style system. The mechanism consumes dial definitions; it does not produce them. Any style system that can declare variation points as a conforming dial definition table can use intrinsic signage.

The primitive: style variation points, operated by a deterministic script, become transport-surviving verification signals bound to the text's own content.

CC BY-SA 4.0 -- Mikhail Shakhnazarov, Berlin, February 2026

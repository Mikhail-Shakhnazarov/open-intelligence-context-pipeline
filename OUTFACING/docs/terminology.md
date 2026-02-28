SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Target glossary for outward-facing text (plain-language aliases for protocol terms).
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# Terminology

This file provides plain-language aliases for terms used in the normative protocol corpus.

Rule for outward-facing text: use the plain term by default; include the protocol term in parentheses on first mention only.

Plain-language edition of the protocol: `protocol/plain-language/` (non-authoritative mirror).

## Core mapping

| Protocol term | Plain term |
|---|---|
| selection trace | selection log |
| second-order tokens | artifacts with embedded instructions |
| canonical record | normalized record |
| ratification | approval |
| promotion | approval into durable state |
| derived cache | rebuildable index |
| cache non-authority | rebuildable index is not authoritative |
| routing labels | artifact labels |
| integrity marking | copy/paste drift check |
| integrity indicator | drift marking |
| signing profile | marking profile |
| dial | marking knob |

## Short glosses (plain-language definitions)

- Selection log (selection trace): a short log explaining what was included in a context packet and why, plus major exclusions.
- Artifacts with embedded instructions (second-order tokens): artifacts that carry their own processing and governance cues inside the text.
- Normalized record (canonical record): the reference form of a record after normalization so it can be compared and reused reliably.
- Approval (ratification): the explicit act of accepting a proposal into durable registries.
- Rebuildable index (derived cache): a non-authoritative convenience layer that can be regenerated from authoritative records.
- Copy/paste drift check (integrity marking): a visible marking pattern that helps detect accidental edits, corruption, or drift during copying/formatting.
- Artifact labels (routing labels): metadata labels that determine how an artifact is handled (authority, boundary, audience, etc.).
- Marking profile (signing profile): the defined settings for drift marking so verification is repeatable.
- Marking knob (dial): one adjustable parameter in the marking profile.

## Notes

- These aliases are intended for docs, onboarding, templates, and examples.
- If a plain term starts to accumulate normative meaning, anchor it by including the protocol term on first mention.

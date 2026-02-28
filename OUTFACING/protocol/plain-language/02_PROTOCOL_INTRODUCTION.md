# 02 PROTOCOL INTRODUCTION (plain-language mirror)

This is a plain-language mirror of: `../normative/02_PROTOCOL_INTRODUCTION.md`.
This mirror is not authoritative. If any discrepancy exists, the normative edition governs.

## What this protocol is

This protocol defines a local context pipeline: a governed workflow that takes messy, high-entropy material (notes, transcripts, documents, repos, calendars) and produces a bounded briefing package for a language-model runtime.

The runtime is intentionally replaceable. Continuity lives in artifacts, not inside a vendor feature.

## What gets produced every session

The canonical output is a three-file set:

- Context packet: the bounded brief given to the runtime.
- Selection log (selection trace): a receipt for what was included and why, plus major exclusions.
- Update proposals: suggested durable updates, explicitly non-binding until approved (ratified).

The set is the governance unit. Packet-only workflows drift into opaque selection and silent hardening.

## Why this exists

When assistant state is implicit or vendor-managed, continuity becomes hard to inspect, hard to move, and easy to leak across boundaries. This protocol keeps custody and promotion explicit:

- Boundaries are declared (private vs personal; internal vs external).
- Inclusions are explained (selection log).
- Long-term changes are explicit and reviewable (update proposals -> approval).

Derived convenience layers (summaries, embeddings, indices) are treated as rebuildable indexes, not as authoritative truth.


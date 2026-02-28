# 02 PROTOCOL INTRODUCTION

## METADATA // 00

- MACHINES FOR THINKING
- LOCAL CONTEXT PIPELINE PROTOCOL
- FIRST-ORDER ORIENTATION FOR HUMAN READERS
- AUTHOR: MIKHAIL SHAKHNAZAROV
- DATE: FEBRUARY 2026
- LICENSE: CC BY-SA 4.0
- https://creativecommons.org/licenses/by-sa/4.0/

## WHAT THIS IS // 01

This corpus specifies a local context pipeline: a governed system that ingests high-entropy material (notes, transcripts, documents, repositories, calendars) and emits bounded, inspectable context packets for language-model runtimes.

The pipeline is specified as a portable protocol: procedures are text-defined, artifacts are typed by routing labels, boundaries are enforceable, and conformance claims are testable. The runtime remains replaceable.

## THE PROBLEM // 02

Assistants at scale face an incentive gradient toward retention and monetization. Continuity creates switching costs; personal context is the raw material for continuity. Vendor-owned memory pipelines accumulate context silently, derive latent profiles, and convert dependence into default capture.

The technical pipeline (logging to inference to embeddings to retrieval to compaction) is not the issue; custody is. When the pipeline is opaque or vendor-locked, personalization becomes extraction by default.

## THE SOLUTION // 03

The alternative is an operator-owned, inspectable pipeline that externalizes continuity into user-controlled artifacts and procedures.

The pipeline produces three explicit outputs:

| Output | Purpose |
|--------|---------|
| Packet content | What a runtime sees; bounded, inspectable, editable |
| Selection trace | Why items were selected; evidence-linked selection, not mind-reading |
| Update proposals | Proposed long-term state changes; deliberate, never silent |

Continuity survives runtime swaps because it is stored as artifacts, not as a vendor profile. Derived structure (summaries, embeddings, indices) is treated as rebuildable cache, not as truth.

## THE PIPELINE STANCE // 04

Building packets, not assistance, is the framing. A context packet is a built artifact: it declares what category it is, what inputs were permitted, what boundaries were enforced, and what acceptance criteria define "done."

The pipeline does not become intimate; it makes selection inspectable and termination explicit. Promotion into long-term state requires explicit ratification.

## SCOPE AND BOUNDARIES // 05

This protocol governs:

- artifact types and their routing labels;
- compaction and packet-building procedures (named transforms with acceptance criteria);
- epistemic status and promotion rules (settled vs provisional);
- boundary enforcement (explicit separation between categories of context);
- conformance claims (what can be tested, and how).

This protocol does not:

- prescribe domain content or recommendations;
- define a hosted service;
- grant a vendor access to unbounded state;
- equate memory with silent accumulation.

## HOW TO READ THIS CORPUS // 06

Start with the Manifest for scope and license. Then proceed through System Audit, Structural Obligations, Routing Labels, Certainty Marking, Integrity Marking, and Terse Style. Then proceed to the Pipeline Model, Artifact Types, Procedures, and Conformance.

CC BY-SA 4.0 - Mikhail Shakhnazarov, February 2026

SPDX-License-Identifier: CC-BY-SA-4.0 OR CC0-1.0
Summary: Non-normative guidance for using the protocol ad hoc as a single operator without losing invariants.
Normative: Requirements and definitions live in `protocol/normative/` (this repository).
See: LICENSE.md in this directory.

# Single-operator adaptation (ad hoc without collapse)

This note belongs to the personal path. Start at `docs/personal-quickstart.md` for the minimal end-to-end workflow.

A single operator can invent structure on the fly. The danger is not improvisation; the danger is losing invariants.

Keep these invariants even when inventing everything else:

- A parseable header with routing labels and boundary.
- A visible "provisional vs settled" distinction.
- A three-file set per session (packet + trace + proposals).
- No silent promotion of proposals into durable registries.

Everything beyond that can be invented per project.


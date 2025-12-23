# ARC BR — Boundary Routing & Inter-Institution Executability
## BR-3 — Obligation Packet (OP): The Cross-Boundary Payload

**Status:** IN PROGRESS  
**Progress Marker:** BR-3  
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Purpose

This file defines the **Obligation Packet (OP)** — the **minimal, sufficient, and non-interpretive payload** that may cross an institutional boundary under Boundary Routing.

The OP is **not data exchange**.  
It is the **carrier of institutional obligation continuity**.

Anything not required to preserve execution, legitimacy, and verifiability **must not cross**.

---

## Scope & Non-Goals

### In Scope
- Definition of the Obligation Packet
- Required and forbidden fields
- Versioning and identity rules
- Integrity and replay properties
- Relationship to BSFEU, SFEU, ENI, and TDV

### Out of Scope
- Serialization formats
- Transport protocols
- Cryptographic algorithms
- Compression or optimization
- UI or documentation payloads

---

## Table of Contents (Upcoming Only)

- BR-3.1 Definition & Rationale
- BR-3.2 Required Fields
- BR-3.3 Forbidden Fields
- BR-3.4 Identity & Versioning
- BR-3.5 Integrity & Replay Properties
- BR-3.6 Minimality Principle

---

## BR-3.1 Definition & Rationale

An **Obligation Packet (OP)** is:

> a deterministic, non-interpretive representation of an institutional state transition, sufficient to allow boundary execution continuation or explicit refusal by a BSFEU.

The OP exists to:
- preserve institutional meaning,
- prevent narrative leakage,
- eliminate discretion at the boundary.

---

## BR-3.2 Required Fields

An OP **MUST** contain exactly the following fields:

1. **`state_delta`**  
   The concrete institutional state transition produced by the originating SFEU.

2. **`authority_ref`**  
   A reference to the authority that permitted the originating transition.

3. **`rule_ref`**  
   A globally unique identifier of the rule version that fired.

4. **`time_ref`**  
   A non-erasable execution time reference from ENI.

5. **`tdv_ref`**  
   A pointer enabling independent verification of execution evidence.

6. **`origin_institution_id`**  
   A stable identifier for the originating institution.

7. **`packet_id`**  
   A unique identifier for the Obligation Packet itself.

No other fields are required.

---

## BR-3.3 Forbidden Fields

An OP **MUST NOT** contain:

- free-text descriptions
- rationale or intent explanations
- policy statements
- discretionary flags
- suggested outcomes
- severity or priority labels
- human commentary
- derived interpretations

If interpretation is needed, execution has already failed.

---

## BR-3.4 Identity & Versioning

The OP is **identity-bound**.

- `packet_id` identifies the OP instance.
- `rule_ref` identifies the rule semantics.
- `authority_ref` identifies permission scope.
- `origin_institution_id` identifies provenance.

Versioning rules:
- OP schema versions must be explicit.
- Rule evolution does not retroactively alter OP meaning.
- OPs are immutable once issued.

---

## BR-3.5 Integrity & Replay Properties

An OP **MUST** satisfy:

1. **Integrity**  
   Any mutation invalidates the packet.

2. **Replay Safety**  
   Replays must be detectable via `packet_id` and `time_ref`.

3. **Order Preservation**  
   OPs must not be reorderable across boundaries.

4. **Context Independence**  
   OP meaning must not depend on out-of-band context.

Integrity is structural, not cryptographic (mechanisms unspecified).

---

## BR-3.6 Minimality Principle

> **If a field is not required for deterministic continuation or explicit refusal, it must not be included.**

This principle ensures:
- lowest trust load,
- lowest attack surface,
- maximal fork visibility,
- resistance to narrative creep.

Minimal OPs are a **security feature**, not a limitation.

---

## Completion Criteria

BR-3 is complete when:

1. Cross-boundary payload is unambiguous.
2. No narrative or discretionary data can cross.
3. BSFEU decisions can be made using OP alone.
4. Replay and mutation are detectable.

---

**Next File:**  
`04_br4_refusal_and_non_routing.md`

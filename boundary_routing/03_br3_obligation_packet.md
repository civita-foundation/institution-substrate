# ARC BR — Boundary Routing & Inter-Institution Executability

## BR-3 — Obligation Packet (OP): CI/EI-Aligned Cross-Boundary Payload

**Status:** IN PROGRESS
**Progress Marker:** BR-3
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Terminology Guardrail (Non-Negotiable)

* **Computable Institution (CI)** determines *which institutional state transitions are admissible and decidable*.
* **Executable Institution (EI)** makes CI outcomes *non-bypassable* through refusal-first routing, authority binding, and immutable memory.

An **Obligation Packet (OP)** is a **CI-level artifact**.
It carries *computable institutional state* across boundaries.

An OP **does not itself execute or enforce anything**.

---

## Purpose

This file defines the **Obligation Packet (OP)** — the **minimal, sufficient, and non-interpretive payload** that may cross an institutional boundary under Boundary Routing.

The OP is **not data exchange**.
It is the **carrier of CI-determined institutional state or obligation continuity**.

Anything not required to preserve:

* computable admissibility,
* legitimacy provenance,
* temporal ordering, and
* verifiability

**MUST NOT cross the boundary**.

---

## Scope & Non-Goals

### In Scope

* Definition of the Obligation Packet
* Required and forbidden fields
* Identity and versioning rules
* Integrity and replay properties
* Relationship to BSFEU, SFEU, ENI, and TDV

### Out of Scope

* Serialization formats
* Transport protocols
* Cryptographic algorithms
* Compression or optimization
* UI or documentation payloads

---

## BR-3.1 Definition & Rationale

An **Obligation Packet (OP)** is:

> a deterministic, non-interpretive representation of a **CI-determined institutional state transition**, sufficient to allow boundary continuation or explicit refusal by a BSFEU.

The OP exists to:

* preserve institutional meaning without interpretation,
* prevent narrative leakage across boundaries,
* eliminate discretion at the routing boundary.

---

## BR-3.2 Required Fields

An OP **MUST** contain exactly the following fields:

1. **`state_delta`**
   The institutional state transition as *determined by CI logic* on the originating side.

2. **`authority_ref`**
   A reference to the authority that permitted the originating transition.

3. **`rule_ref`**
   A globally unique identifier of the rule version that fired.

4. **`time_ref`**
   A non-erasable institutional time reference.

5. **`tdv_ref`**
   A pointer enabling independent verification of the originating transition.

6. **`origin_institution_id`**
   A stable identifier for the originating institution.

7. **`packet_id`**
   A unique identifier for the Obligation Packet instance.

No other fields are permitted.

---

## BR-3.3 Forbidden Fields

An OP **MUST NOT** contain:

* free-text descriptions
* rationale or intent explanations
* policy statements
* discretionary flags
* suggested outcomes
* severity or priority labels
* human commentary
* derived or inferred interpretations

If interpretation is required, boundary routing has already failed.

---

## BR-3.4 Identity & Versioning

The OP is **identity-bound and immutable**.

* `packet_id` identifies the OP instance.
* `rule_ref` identifies the rule semantics.
* `authority_ref` identifies permission scope.
* `origin_institution_id` identifies provenance.

Versioning rules:

* OP schema versions MUST be explicit.
* Rule evolution MUST NOT retroactively alter OP meaning.
* OPs MUST NOT be mutated once issued.

---

## BR-3.5 Integrity & Replay Properties

An OP **MUST** satisfy all of the following:

1. **Integrity**
   Any mutation invalidates the packet.

2. **Replay Safety**
   Replays MUST be detectable via `packet_id` and `time_ref`.

3. **Order Preservation**
   OPs MUST NOT be reorderable across boundaries.

4. **Context Independence**
   OP meaning MUST NOT depend on out-of-band context.

Integrity requirements are **structural**, not cryptographic.

---

## BR-3.6 Minimality Principle

> **If a field is not required for deterministic CI-level continuation or explicit refusal, it MUST NOT be included.**

This principle ensures:

* minimal trust load,
* minimal attack surface,
* maximal fork visibility,
* resistance to narrative creep.

Minimal OPs are a **security feature**, not a limitation.

---

## Completion Criteria

BR-3 is complete when:

1. Cross-boundary payload is unambiguous and CI-complete.
2. No narrative, discretionary, or inferred data can cross.
3. BSFEU decisions can be made using OP alone.
4. Replay and mutation are detectable.
5. EI responsibility is limited to non-bypassability and memory.

---

**Next File:**
`04_br4_refusal_and_non_routing.md`

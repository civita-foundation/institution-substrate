# ARC BR — Boundary Routing & Inter-Institution Executability
## BR-1 — Formal Definition & Invariants

**Status:** IN PROGRESS  
**Progress Marker:** BR-1  
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Purpose

This file defines **Boundary Routing** as a first-class execution concept.

Boundary Routing closes the gap between **local institutional execution** and **cross-institutional propagation** by formalizing routing as **execution continuation**, not communication or interoperability.

---

## Scope & Non-Goals

### In Scope
- Formal definition of Boundary Routing
- Preconditions for valid routing
- Non-negotiable invariants
- Explicit success and failure semantics

### Out of Scope
- Transport protocols
- Cryptographic mechanisms
- Network topology
- Pricing or business models
- Governance procedures

---

## Table of Contents (Upcoming Only)

- BR-1.1 Formal Definition  
- BR-1.2 Routing Preconditions  
- BR-1.3 Invariants  
- BR-1.4 Forbidden Shortcuts  
- BR-1.5 Success & Failure Conditions  
- BR-1.6 Minimal Interface Contract  

---

## BR-1.1 Formal Definition

**Boundary Routing** is the **deterministic propagation of an institutional state transition across institutional boundaries**, such that the receiving institution can continue execution **without interpretation**, while preserving:

- authority provenance,
- rule identity and version,
- execution order (time),
- and TDV-verifiable memory,

**without requiring trust** between institutions.

Boundary Routing propagates **institutional reality**, not messages.

---

## BR-1.2 Routing Preconditions

Boundary Routing **MUST NOT occur** unless all preconditions hold:

1. **Local Execution Completed**  
   A valid institutional state transition has been executed by an SFEU on ENI.

2. **Authority Explicitly Referenced**  
   The authority permitting the transition is encoded and referenceable.

3. **Rule Identity Fixed**  
   The exact rule version that fired is uniquely identified.

4. **Temporal Anchor Present**  
   Execution time is ordered, explicit, and non-erasable.

5. **TDV Anchor Present**  
   A TDV reference exists enabling future independent verification.

Failure of any precondition → routing is invalid.

---

## BR-1.3 Invariants (Non-Negotiable)

Boundary Routing **MUST preserve all invariants below**.  
Violation of any invariant invalidates routing.

1. **Authority Provenance Invariant**  
   The right to cause the transition is traceable to an explicit authority definition.

2. **Rule Identity Invariant**  
   The originating rule is preserved by identity, not semantic equivalence.

3. **Execution Order Invariant**  
   Cross-boundary continuation must not reorder or backdate transitions.

4. **Determinism Invariant**  
   Given identical inputs and rule references, continuation yields the same outcome or explicit failure.

5. **TDV Verifiability Invariant**  
   The transition remains verifiable across time without trusting either institution.

6. **No Interpretation Invariant**  
   The receiving institution must not infer intent, context, or meaning beyond encoded facts.

---

## BR-1.4 Forbidden Shortcuts

The following invalidate Boundary Routing **by construction**:

- Narrative or free-text fields
- Discretion hooks or manual overrides
- Rule substitution or semantic mapping
- Silent drops or implicit refusal
- Assumed shared trust, clocks, or administrators
- Post-hoc repair or retroactive justification

Any occurrence → not Boundary Routing.

---

## BR-1.5 Success & Failure Conditions

### Success

Boundary Routing succeeds **iff**:
- All preconditions hold
- All invariants are preserved
- The receiving institution reaches:
  - a continued executable state, **or**
  - an explicit terminal failure state

### Failure (Explicit, Typed)

Failure **MUST** be explicit and typed:

- `AUTHORITY_INVALID`
- `RULE_MISMATCH`
- `TIME_ORDER_VIOLATION`
- `TDV_ANCHOR_MISSING`
- `DETERMINISM_BREAK`
- `LEGITIMACY_WITHDRAWN`

No silent or ambiguous outcomes are permitted.

---

## BR-1.6 Minimal Interface Contract (Abstract)

### Inputs
- `state_delta`
- `authority_ref`
- `rule_ref`
- `time_ref`
- `tdv_ref`

### Outputs
- `continued_state` **or** `explicit_failure`
- optional `new_time_ref`
- optional `new_tdv_ref`

No interpretation layer.  
No side channels.

---

## Completion Criteria

BR-1 is complete when:

- Boundary Routing is unambiguously defined as execution continuation
- Trust is not reintroduced implicitly
- Failure is explicit, enumerable, and attributable

---

**Next File:**  
`02_br2_boundary_sfeu.md`
BR-2 — Boundary SFEUs (BSFEU): The Execution Atom at the Boundary

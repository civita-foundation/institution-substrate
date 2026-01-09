# ARC BR — Boundary Routing & Inter-Institution Executability

## BR-2 — Boundary SFEUs (BSFEU): CI/EI-Aligned Boundary Execution Unit

**Status:** IN PROGRESS
**Progress Marker:** BR-2
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Terminology Guardrail (Non-Negotiable)

* **Computable Institution (CI)** determines *whether an institutional state transition is admissible and decidable*.
* **Executable Institution (EI)** makes CI outcomes *non-bypassable* through refusal-first routing, authority binding, and immutable memory.

A **BSFEU operates at the CI-defined boundary**.
It does **not** by itself confer execution authority or enforcement.

BSFEU outcomes become unavoidable **only when embedded in an EI**.

---

## Purpose

This file defines **Boundary Status-Function Execution Units (BSFEUs)** — the minimal, non-discretionary units that evaluate **cross-boundary continuation or refusal** of CI-determined institutional state transitions.

A BSFEU is the **only component permitted to decide whether a routed state transition may continue across an institutional boundary**, producing either:

* a **continued CI-admissible state**, or
* an **explicit terminal refusal**.

No interpretation. No negotiation. No silent outcomes.

---

## Scope & Non-Goals

### In Scope

* Definition of BSFEU
* CI/EI-aligned execution responsibilities and constraints
* Input/output contracts
* Explicit failure typing and semantics
* Relationship to SFEU, ENI, and TDV

### Out of Scope

* Transport or networking
* Cryptography choices
* Identity provisioning
* Governance workflows
* Product or UI integration

---

## BR-2.1 Definition & Role

A **Boundary Status-Function Execution Unit (BSFEU)** is a deterministic, execution-only unit that:

> evaluates whether a **CI-determined institutional state transition** may be *continued* within a receiving institution, or must be *explicitly refused*, without interpretation.

BSFEU is:

* execution-native
* non-interpretive
* refusal-capable
* legitimacy-sensitive

BSFEU is **not**:

* a gateway
* an adapter
* an API
* a governance actor

---

## BR-2.2 Position in the Execution Stack

BSFEU operates **after** local CI/SFEU determination on the originating side and **before** any local execution or enforcement on the receiving side.

```
[ Origin SFEU (CI) ]
        |
        v
[ TDV Reference ]
        |
        v
[ Boundary Routing ]
        |
        v
[ BSFEU ]  <-- CI-level boundary decision
        |
        v
[ Local SFEU(s) or Explicit Refusal ]
```

BSFEU:

* does not execute local business rules
* does not modify governance
* does not alter past state

It decides **only** whether CI-defined continuation is admissible.

---

## BR-2.3 Input Contract

A BSFEU **MUST** accept exactly the following inputs:

* `state_delta`
  The institutional state transition determined by the originating CI/SFEU.

* `authority_ref`
  A reference to the authority that permitted the originating transition.

* `rule_ref`
  A unique identifier for the rule version that fired.

* `time_ref`
  An ordered, non-erasable institutional time reference.

* `tdv_ref`
  A pointer enabling independent verification of the prior transition.

No additional inputs are permitted.

---

## BR-2.4 Execution Semantics

BSFEU execution is **deterministic** and **total**.

Given valid inputs, the BSFEU MUST:

1. Verify authority provenance
2. Verify rule identity compatibility
3. Verify institutional time ordering
4. Verify TDV availability
5. Evaluate local acceptance constraints (rule-bound and pre-declared)

BSFEU **MUST NOT**:

* infer intent
* evaluate fairness
* negotiate terms
* request human judgment
* introduce delays beyond deterministic checks

---

## BR-2.5 Output Contract

BSFEU outputs **exactly one** of the following:

### A. Continued CI-Admissible State

* `continued_state`
* optional `new_time_ref`
* optional `new_tdv_ref`

This output authorizes **CI-level continuation** only.
Non-bypassable execution requires EI guarantees.

### B. Explicit Refusal

* `failure_code`
* `failure_time_ref`
* optional `failure_tdv_ref`

No silent drops. No partial success.

---

## BR-2.6 Failure Typing

BSFEU failures **MUST** be explicit and typed:

* `AUTHORITY_INVALID`
* `RULE_MISMATCH`
* `TIME_ORDER_VIOLATION`
* `TDV_UNVERIFIABLE`
* `LEGITIMACY_WITHDRAWN`
* `LOCAL_ACCEPTANCE_FAILED`

Failure codes are enumerable and closed.

---

## BR-2.7 Forbidden Capabilities

A BSFEU **MUST NOT**:

* modify rules
* reinterpret authority
* mutate prior state
* request discretionary approval
* embed policy logic
* expose narrative explanations
* retry implicitly
* route around failure

Any such capability invalidates BSFEU conformance.

---

## Completion Criteria

BR-2 is complete when:

1. The boundary continuation role is unambiguous at the CI level
2. No discretion exists at the boundary
3. All outcomes are deterministic and explicit
4. EI responsibility is limited to non-bypassability and memory
5. BSFEU behavior is independently testable

---

**Next File:**
`03_br3_obligation_packet.md`

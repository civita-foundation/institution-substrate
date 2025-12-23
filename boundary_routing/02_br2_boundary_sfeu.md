# ARC BR — Boundary Routing & Inter-Institution Executability
## BR-2 — Boundary SFEUs (BSFEU): The Execution Atom at the Boundary

**Status:** IN PROGRESS  
**Progress Marker:** BR-2  
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Purpose

This file defines **Boundary Status-Function Execution Units (BSFEUs)** — the minimal, non-discretionary execution units that operate **at institutional boundaries**.

A BSFEU is the **only** component permitted to execute cross-boundary continuation of institutional state under Boundary Routing. It converts a routed state transition into either:
- a **continued executable state**, or
- an **explicit terminal failure**.

No interpretation. No negotiation. No silent outcomes.

---

## Scope & Non-Goals

### In Scope
- Definition of BSFEU
- Execution responsibilities and constraints
- Input/output contracts
- Failure typing and semantics
- Relationship to SFEU, ENI, and TDV

### Out of Scope
- Transport or networking
- Cryptography choices
- Identity provisioning
- Governance workflows
- Product integration details

---

## Table of Contents (Upcoming Only)

- BR-2.1 Definition & Role
- BR-2.2 Position in the Execution Stack
- BR-2.3 Input Contract
- BR-2.4 Execution Semantics
- BR-2.5 Output Contract
- BR-2.6 Failure Typing
- BR-2.7 Forbidden Capabilities

---

## BR-2.1 Definition & Role

A **Boundary Status-Function Execution Unit (BSFEU)** is an execution-only unit that:

> deterministically evaluates whether a routed institutional state transition may continue execution within the receiving institution, and produces a corresponding state transition or explicit failure.

BSFEU is:
- execution-native,
- non-interpretive,
- legitimacy-sensitive,
- refusal-capable.

BSFEU is **not** a gateway, adapter, or API.

---

## BR-2.2 Position in the Execution Stack

BSFEU operates **after** local SFEU execution on the sender side and **before** any local SFEU execution on the receiver side.

```
[ Origin SFEU ]
|
v
[ TDV Commit ]
|
v
[ Boundary Routing ]
|
v
[ BSFEU ] <-- THIS FILE
|
v
[ Local SFEU(s) or Explicit Failure ]
```


BSFEU:
- does not execute local business rules,
- does not modify governance,
- does not alter past execution.

It decides **only** whether execution may continue.

---

## BR-2.3 Input Contract

A BSFEU **MUST** accept exactly the following inputs:

- `state_delta`  
  The institutional state change produced by the originating SFEU.

- `authority_ref`  
  A reference to the authority that permitted the originating transition.

- `rule_ref`  
  A unique identifier for the rule version that fired.

- `time_ref`  
  An ordered, non-erasable execution time reference.

- `tdv_ref`  
  A pointer enabling independent verification of prior execution.

No additional inputs are permitted.

---

## BR-2.4 Execution Semantics

BSFEU execution is **deterministic** and **total**.

Given valid inputs, the BSFEU MUST:

1. Verify authority provenance
2. Verify rule identity compatibility
3. Verify temporal ordering
4. Verify TDV availability
5. Evaluate local acceptance constraints (rule-bound, pre-declared)

BSFEU **MUST NOT**:
- infer intent,
- evaluate fairness,
- negotiate terms,
- request human judgment,
- introduce delays beyond deterministic checks.

---

## BR-2.5 Output Contract

BSFEU outputs **exactly one** of the following:

### A. Continued Execution State
- `continued_state`
- optional `new_time_ref`
- optional `new_tdv_ref`

This output authorizes subsequent **local SFEU execution**.

### B. Explicit Failure
- `failure_code`
- `failure_time_ref`
- optional `failure_tdv_ref`

No silent drops. No partial success.

---

## BR-2.6 Failure Typing

BSFEU failures **MUST** be explicit and typed:

- `AUTHORITY_INVALID`
- `RULE_MISMATCH`
- `TIME_ORDER_VIOLATION`
- `TDV_UNVERIFIABLE`
- `LEGITIMACY_WITHDRAWN`
- `LOCAL_ACCEPTANCE_FAILED`

Failure codes are enumerable and closed.

---

## BR-2.7 Forbidden Capabilities

A BSFEU **MUST NOT**:

- modify rules
- reinterpret authority
- mutate prior state
- request discretionary approval
- embed policy logic
- expose narrative explanations
- retry implicitly
- route around failure

Any such capability invalidates BSFEU conformance.

---

## Completion Criteria

BR-2 is complete when:

1. The boundary execution role is unambiguous.
2. No discretion exists at the boundary.
3. All outcomes are deterministic and explicit.
4. BSFEU can be validated independently of implementations.

---

**Next File:**  
`03_br3_obligation_packet.md`

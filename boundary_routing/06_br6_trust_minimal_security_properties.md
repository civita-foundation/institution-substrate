# ARC BR — Boundary Routing & Inter-Institution Executability
## BR-6 — Trust-Minimal Security Properties

**Status:** IN PROGRESS  
**Progress Marker:** BR-6  
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Purpose

This file defines the **security properties** required for Boundary Routing to function under **trust-minimal conditions**.

Security here is **structural**, not cryptographic.
It specifies **what must be true** for execution to remain legitimate across institutional boundaries, regardless of implementation choices.

---

## Scope & Non-Goals

### In Scope
- Adversarial assumptions
- Required trust-minimal properties
- Verifiability and independence conditions
- Failure visibility guarantees
- Boundary attack surfaces (structural)

### Out of Scope
- Cryptographic algorithms
- Key management
- Network security
- Authentication mechanisms
- Intrusion detection systems

Those belong to engineering layers and may vary by implementation.

---

## Table of Contents (Upcoming Only)

- BR-6.1 Adversarial Assumptions
- BR-6.2 Required Security Properties
- BR-6.3 Verification Independence
- BR-6.4 Failure Visibility & Non-Deniability
- BR-6.5 Boundary Attack Surfaces
- BR-6.6 Forbidden Security Assumptions

---

## BR-6.1 Adversarial Assumptions

Boundary Routing assumes **worst-case institutional behavior**.

Specifically:
- institutions may act in self-interest,
- operators may be compromised,
- incentives may diverge,
- trust may be asymmetric or absent,
- historical narratives may be rewritten.

Boundary Routing must remain valid **without relying on good faith**.

---

## BR-6.2 Required Security Properties

A Boundary Routing implementation **MUST satisfy all properties below**:

1. **Deterministic Executability**  
   Given valid inputs, execution outcomes are predictable or explicitly failed.

2. **Authority Non-Forgery**  
   Authority references cannot be fabricated without detection.

3. **Rule Integrity**  
   Rule identity and version cannot be altered in transit.

4. **Temporal Integrity**  
   Time ordering cannot be manipulated without detection.

5. **Evidence Persistence**  
   Execution and refusal evidence cannot be erased silently.

6. **Selective Non-Trust**  
   No single institution is trusted as an arbiter of truth.

---

## BR-6.3 Verification Independence

Verification of boundary execution **MUST**:

- be possible by third parties,
- not depend on trusting either institution,
- rely only on preserved evidence and rules.

If verification requires:
- testimony,
- private logs,
- administrative access,

then Boundary Routing has failed structurally.

---

## BR-6.4 Failure Visibility & Non-Deniability

Security requires that **failure is visible**.

Boundary Routing **MUST ensure**:

- attempts to route are observable,
- refusals are recorded,
- suppression is detectable,
- absence of execution is meaningful.

> Silence is treated as a security failure.

---

## BR-6.5 Boundary Attack Surfaces (Structural)

The primary attack surfaces are **structural**, not technical:

- rule ambiguity
- discretionary overrides
- narrative justification
- selective memory
- delayed execution
- asymmetric observability

Boundary Routing mitigates these by:
- forbidding interpretation,
- enforcing explicit failure,
- externalizing memory,
- preserving time ordering.

---

## BR-6.6 Forbidden Security Assumptions

Boundary Routing **MUST NOT assume**:

- shared administrators
- synchronized clocks
- benevolent operators
- aligned incentives
- reversible execution
- secrecy as security

Any such assumption reintroduces trust implicitly.

---

## Completion Criteria

BR-6 is complete when:

1. Security properties are implementation-agnostic.
2. No trust assumption is required to reason about correctness.
3. Failure and suppression are observable.
4. Adversarial behavior degrades gracefully into explicit refusal.

---

**Next File:**  
`07_br7_conformance_and_standard_surface.md`

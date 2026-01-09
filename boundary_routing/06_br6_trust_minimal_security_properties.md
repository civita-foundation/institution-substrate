# ARC BR — Boundary Routing & Inter-Institution Executability

## BR-6 — Trust-Minimal Security Properties (CI/EI Aligned)

**Status:** IN PROGRESS
**Progress Marker:** BR-6
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Terminology Guardrail (Non-Negotiable)

* **Computable Institution (CI)** defines *which boundary routing behaviors are admissible and computable under worst-case assumptions*.
* **Executable Institution (EI)** makes CI security outcomes *non-bypassable* through refusal-first routing and immutable memory.

Security properties in this file are defined **structurally at the CI level**.
Their enforcement and persistence are guaranteed **only under EI**.

---

## Purpose

This file defines the **trust-minimal security properties** required for Boundary Routing to function correctly under **worst-case institutional behavior**.

Security here is **structural, not cryptographic**.
It specifies **what must be true** for boundary continuation or refusal to remain legitimate across institutional boundaries, independent of implementation choices.

---

## Scope & Non-Goals

### In Scope

* Adversarial assumptions
* Required trust-minimal properties
* Verification independence conditions
* Failure visibility and non-deniability guarantees
* Structural boundary attack surfaces

### Out of Scope

* Cryptographic algorithms
* Key management
* Network security
* Authentication mechanisms
* Intrusion detection systems

Those belong to engineering layers and may vary by implementation.

---

## BR-6.1 Adversarial Assumptions

Boundary Routing assumes **worst-case institutional behavior by default**.

Specifically:

* institutions may act in self-interest,
* operators may be compromised,
* incentives may diverge,
* trust may be asymmetric or absent,
* historical narratives may be rewritten.

Boundary Routing MUST remain valid **without relying on good faith** or cooperative behavior.

---

## BR-6.2 Required Security Properties (CI-Level)

A Boundary Routing implementation **MUST satisfy all properties below** at the CI level:

1. **Deterministic Continuation or Refusal**
   Given identical inputs, routing MUST deterministically continue or explicitly refuse.

2. **Authority Non-Forgery**
   Authority references MUST NOT be fabricable without detection.

3. **Rule Integrity**
   Rule identity and version MUST NOT be altered in transit or reinterpretation.

4. **Temporal Integrity**
   Institutional time ordering MUST NOT be manipulable without detection.

5. **Evidence Persistence (Reference-Level)**
   Evidence references for continuation or refusal MUST NOT be suppressible silently.

6. **Selective Non-Trust**
   No single institution, operator, or boundary participant is trusted as an arbiter of truth.

---

## BR-6.3 Verification Independence

Verification of boundary routing outcomes **MUST**:

* be possible by third parties,
* not depend on trusting either institution,
* rely only on preserved evidence, rule references, and time anchors.

If verification requires:

* testimony,
* private logs,
* administrative access,

then Boundary Routing has failed structurally.

---

## BR-6.4 Failure Visibility & Non-Deniability

Security requires that **failure is observable**.

Boundary Routing **MUST ensure**:

* attempts to route are detectable,
* refusals are explicitly recorded,
* suppression or omission is observable,
* absence of continuation is meaningful.

> Silence is treated as a security failure, not a neutral condition.

Under EI, failure visibility becomes non-bypassable and permanently recorded.

---

## BR-6.5 Boundary Attack Surfaces (Structural)

The primary attack surfaces are **structural**, not technical:

* rule ambiguity
* discretionary overrides
* narrative justification
* selective memory
* delayed continuation
* asymmetric observability

Boundary Routing mitigates these by:

* forbidding interpretation,
* enforcing explicit refusal,
* externalizing memory via TDV,
* preserving institutional time ordering.

---

## BR-6.6 Forbidden Security Assumptions

Boundary Routing **MUST NOT assume**:

* shared administrators
* synchronized clocks
* benevolent operators
* aligned incentives
* reversible execution
* secrecy as security

Any such assumption implicitly reintroduces trust and invalidates conformance.

---

## Completion Criteria

BR-6 is complete when:

1. Security properties are implementation-agnostic and CI-defined
2. No trust assumption is required to reason about correctness
3. Failure and suppression are observable
4. Adversarial behavior degrades gracefully into explicit refusal
5. EI responsibility is limited to non-bypassability and memory

---

**Next File:**
`07_br7_conformance_and_standard_surface.md`

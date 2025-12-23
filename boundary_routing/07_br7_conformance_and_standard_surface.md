# ARC BR — Boundary Routing & Inter-Institution Executability
## BR-7 — Conformance & Standardization Surface

**Status:** IN PROGRESS  
**Progress Marker:** BR-7  
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Purpose

This file defines the **conformance criteria** and **standardization surface** for Boundary Routing.

Its function is to make Boundary Routing:
- testable,
- comparable,
- fork-visible,
- and certifiable,

without prescribing implementations or vendors.

Boundary Routing becomes a **standard** only when conformance is unambiguous.

---

## Scope & Non-Goals

### In Scope
- Conformance requirements (normative)
- MUST / SHOULD / MUST NOT criteria
- Observable behaviors
- Non-conformance signals
- Versioning and compatibility rules

### Out of Scope
- Certification authorities
- Governance bodies
- Compliance processes
- Pricing or licensing
- Branding or trademarks

---

## Table of Contents (Upcoming Only)

- BR-7.1 Conformance Levels
- BR-7.2 Normative Requirements
- BR-7.3 Observable Behaviors
- BR-7.4 Non-Conformance Signals
- BR-7.5 Versioning & Compatibility
- BR-7.6 Reference Implementations

---

## BR-7.1 Conformance Levels

Boundary Routing conformance is **binary**.

A system is either:
- **Boundary-Routing-Conformant**, or
- **Not Boundary-Routing-Conformant**

Partial conformance is not recognized.

This avoids ambiguity and “marketing compliance.”

---

## BR-7.2 Normative Requirements

A conformant system **MUST** satisfy all of the following:

1. Implement BSFEU semantics (BR-2)
2. Accept only valid Obligation Packets (BR-3)
3. Emit explicit refusals (BR-4)
4. Preserve time ordering across boundaries (BR-5)
5. Maintain TDV-verifiable memory (BR-5)
6. Operate under trust-minimal assumptions (BR-6)

A conformant system **MUST NOT**:
- introduce discretionary overrides,
- rely on narrative interpretation,
- suppress refusal visibility,
- require implicit trust.

---

## BR-7.3 Observable Behaviors

Conformance is assessed by **observable behavior**, not claims.

Observable indicators include:

- deterministic acceptance or refusal,
- explicit refusal codes,
- monotonic time references,
- verifiable TDV chains,
- absence of silent drops,
- absence of interpretive fields.

If behavior cannot be observed or reconstructed, it is non-conformant.

---

## BR-7.4 Non-Conformance Signals

Any of the following indicate **non-conformance**:

- silent non-routing
- implicit retries
- discretionary approval steps
- rule substitution
- unverifiable execution claims
- narrative explanations in boundary logic
- reliance on shared trust assumptions

Non-conformance is structural, not moral.

---

## BR-7.5 Versioning & Compatibility

Boundary Routing versions:

- MUST be explicitly declared
- MUST be backward-identifiable
- MUST NOT reinterpret prior semantics

Compatibility rules:

- newer versions may extend capabilities
- older versions must remain verifiable
- routing between incompatible versions MUST refuse explicitly

Silent downgrade or upgrade is forbidden.

---

## BR-7.6 Reference Implementations

Reference implementations may exist to:
- demonstrate feasibility,
- validate interpretation,
- test edge cases.

Reference implementations:
- do not define the standard,
- do not override normative text,
- may be open or closed source.

The **standard is defined solely by this ARC**.

---

## Completion Criteria

BR-7 is complete when:

1. Conformance can be tested without vendor cooperation.
2. Forks are visible via behavior.
3. Compatibility rules prevent semantic drift.
4. Boundary Routing qualifies as a standard surface.

---

## ARC BR — Exit Condition

ARC BR is complete when **all BR-1 through BR-7** are satisfied and:

> Boundary execution can propagate or refuse deterministically,  
> across institutions,  
> without trust,  
> without discretion,  
> and without narrative reconciliation.

---

**ARC BR STATUS:** READY FOR FREEZE

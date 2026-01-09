# ARC BR — Boundary Routing & Inter-Institution Executability

## BR-7 — Conformance & Standardization Surface (CI/EI Aligned)

**Status:** IN PROGRESS
**Progress Marker:** BR-7
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Terminology Guardrail (Non-Negotiable)

* **Computable Institution (CI)** defines *computable boundary routing semantics* and determines whether continuation or refusal is admissible.
* **Executable Institution (EI)** makes CI routing outcomes *non-bypassable* and preserves them as immutable institutional memory.

**Boundary Routing conformance is asserted only at the EI level.**
CI-level routing logic may be correct but is **not conformant** unless made non-bypassable and observable.

---

## Purpose

This file defines the **conformance criteria** and **standardization surface** for Boundary Routing.

Its function is to make Boundary Routing:

* testable,
* comparable,
* fork-visible, and
* objectively assessable,

**without prescribing implementations, vendors, or governance bodies**.

Boundary Routing becomes a **standard** only when conformance is unambiguous and behaviorally observable.

---

## Scope & Non-Goals

### In Scope

* Normative conformance requirements
* MUST / SHOULD / MUST NOT criteria
* Observable boundary behaviors
* Non-conformance signals
* Versioning and compatibility rules

### Out of Scope

* Certification authorities
* Governance bodies
* Compliance processes
* Pricing or licensing
* Branding or trademarks

---

## BR-7.1 Conformance Levels

Boundary Routing conformance is **binary**.

A system is either:

* **Boundary-Routing-Conformant (EI)**, or
* **Not Boundary-Routing-Conformant**

Partial, aspirational, or marketing conformance is not recognized.

---

## BR-7.2 Normative Requirements (EI-Level)

A Boundary-Routing-Conformant system **MUST** satisfy **all** of the following:

1. Implement BSFEU semantics (BR-2)
2. Accept only valid Obligation Packets (BR-3)
3. Emit explicit refusals for all non-routed cases (BR-4)
4. Preserve institutional time ordering across boundaries (BR-5)
5. Maintain TDV-verifiable, immutable memory (BR-5)
6. Operate under trust-minimal security assumptions (BR-6)

A conformant system **MUST NOT**:

* introduce discretionary overrides,
* rely on narrative interpretation,
* suppress refusal visibility,
* require implicit trust between institutions.

---

## BR-7.3 Observable Behaviors

Conformance is assessed by **observable behavior**, not claims, documentation, or intent.

Observable indicators include:

* deterministic continuation or refusal,
* explicit refusal codes for all non-routing outcomes,
* monotonic institutional time references,
* verifiable TDV chains across boundaries,
* absence of silent drops,
* absence of interpretive or narrative fields in routing logic.

If behavior cannot be independently observed or reconstructed, the system is non-conformant.

---

## BR-7.4 Non-Conformance Signals

Any of the following indicate **non-conformance**:

* silent non-routing
* implicit retries or fallbacks
* discretionary approval steps
* rule substitution or semantic mapping
* unverifiable continuation or refusal claims
* narrative explanations embedded in boundary logic
* reliance on shared administrators or trust assumptions

Non-conformance is **structural**, not moral or operational.

---

## BR-7.5 Versioning & Compatibility

Boundary Routing versions:

* MUST be explicitly declared
* MUST be backward-identifiable
* MUST NOT reinterpret prior semantics

Compatibility rules:

* newer versions may extend capabilities
* older versions MUST remain verifiable
* routing between incompatible versions MUST refuse explicitly

Silent downgrade, upgrade, or reinterpretation is forbidden.

---

## BR-7.6 Reference Implementations

Reference implementations may exist to:

* demonstrate feasibility,
* validate interpretation,
* test edge cases.

Reference implementations:

* do not define the standard,
* do not override normative text,
* may be open or closed source.

The **standard is defined solely by this ARC**.

---

## Completion Criteria

BR-7 is complete when:

1. Boundary Routing conformance can be tested without vendor cooperation
2. Forks and deviations are visible via behavior alone
3. Compatibility rules prevent semantic drift
4. Boundary Routing qualifies as a stable standard surface

---

## ARC BR — Exit Condition

ARC BR is complete when **all BR-1 through BR-7** are satisfied and:

> Boundary routing outcomes can be deterministically continued or refused,
> across institutions,
> under CI-defined semantics,
> made non-bypassable by EI guarantees,
> without trust, discretion, or narrative reconciliation.

---

**ARC BR STATUS:** READY FOR FREEZE

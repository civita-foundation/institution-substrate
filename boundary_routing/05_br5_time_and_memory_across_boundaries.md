# ARC BR — Boundary Routing & Inter-Institution Executability

## BR-5 — Time & Memory Across Institutional Boundaries (CI/EI Aligned)

**Status:** IN PROGRESS
**Progress Marker:** BR-5
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Terminology Guardrail (Non-Negotiable)

* **Computable Institution (CI)** defines *institutional time semantics* and determines whether boundary continuation is admissible.
* **Executable Institution (EI)** makes CI time and memory outcomes *non-bypassable* and preserves them as immutable institutional memory.

Time ordering and memory linkage are **defined at the CI level**.
Their *finality and survivability* are guaranteed only under EI.

---

## Purpose

This file defines how **institutional time and institutional memory** are preserved when **CI-determined state transitions** cross institutional boundaries.

Boundary Routing is invalid unless **time ordering** and **TDV-referencable memory continuity** survive the boundary intact.

Without this, cross-institution continuation collapses into narrative reconciliation and trust assumptions.

---

## Scope & Non-Goals

### In Scope

* Institutional time semantics (CI)
* Cross-boundary time continuity
* TDV linkage requirements
* Memory survivability requirements
* Drift detection hooks

### Out of Scope

* Clock synchronization mechanisms
* Timestamp formats
* Cryptographic time proofs
* Data retention policy
* Legal admissibility rules

---

## BR-5.1 Institutional Time Continuity (CI)

Institutional time is **not wall-clock time**.

> **Institutional time is the ordered accumulation of irreversible institutional state transitions under constraint.**

Boundary Routing **MUST NOT**:

* reset institutional time,
* fork institutional timelines,
* reinterpret time references,
* collapse multiple transitions into one.

Each routed transition extends a **single, ordered institutional timeline**, even across institutions.

---

## BR-5.2 Ordering Guarantees (CI)

Boundary Routing **MUST preserve** all of the following ordering guarantees:

1. **Precedence**
   A routed transition must occur *after* its originating institutional transition.

2. **Non-Backdating**
   No routed transition may be assigned an earlier effective time than its origin.

3. **Monotonicity**
   Time references must advance or explicitly terminate.

4. **No Reordering**
   Parallel routing paths MUST NOT be merged without explicit ordering rules.

Violation of any ordering guarantee invalidates routing.

---

## BR-5.3 TDV Linkage Across Boundaries

TDV MUST preserve **cross-boundary evidentiary continuity**.

Requirements:

* Each routed transition MUST reference:

  * the originating `tdv_ref`, and
  * the resulting local `tdv_ref` (if continuation is accepted)

* TDV custody separation MUST be preserved.

* Verification MUST NOT depend on trusting either institution.

TDV linkage creates an **unbroken, cross-institution evidentiary chain**.

---

## BR-5.4 Memory Survivability (EI Requirement)

Boundary Routing **MUST be compatible with long-term institutional survivability**.

Memory MUST survive:

* personnel changes,
* administrative turnover,
* institutional reorganization,
* system migration,
* political regime change.

Therefore:

* TDV references MUST remain resolvable over time.
* Institutional memory MUST NOT depend on local databases alone.
* Loss of local records MUST NOT erase institutional history.

Memory survivability is a **design requirement**, not an operational preference.

---

## BR-5.5 Drift Detection Hooks

Cross-boundary continuation increases drift risk.

Boundary Routing **MUST enable** detection of:

* missing transitions,
* suppressed refusals,
* reordered execution,
* unverifiable evidentiary chains.

These detections are **signals**, not judgments.

Drift signals are surfaced to governance or RSI and are **never handled inline**.

---

## BR-5.6 Forbidden Temporal Shortcuts

The following **invalidate Boundary Routing**:

* wall-clock substitution for institutional time
* retroactive correction of time references
* silent consolidation of multiple transitions
* “eventual consistency” claims without ordering guarantees
* narrative reconciliation of timelines

Temporal shortcuts reintroduce trust implicitly and are forbidden.

---

## Completion Criteria

BR-5 is complete when:

1. Institutional time remains ordered across boundaries (CI)
2. TDV preserves a continuous evidentiary chain
3. Memory survivability is guaranteed under EI
4. Drift becomes observable, not narratively managed

---

**Next File:**
`06_br6_trust_minimal_security_properties.md`

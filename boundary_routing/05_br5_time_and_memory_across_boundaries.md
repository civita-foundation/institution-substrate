# ARC BR — Boundary Routing & Inter-Institution Executability
## BR-5 — Time & Memory Across Institutional Boundaries

**Status:** IN PROGRESS  
**Progress Marker:** BR-5  
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Purpose

This file defines how **institutional time and memory** are preserved when execution crosses institutional boundaries.

Boundary Routing is invalid unless **time ordering** and **TDV-backed memory** survive the boundary intact.  
Without this, cross-institution execution collapses into narrative reconciliation.

---

## Scope & Non-Goals

### In Scope
- Temporal ordering guarantees
- Cross-boundary time continuity
- TDV linkage requirements
- Memory survivability across institutional change
- Drift detection hooks

### Out of Scope
- Clock synchronization mechanisms
- Timestamp formats
- Cryptographic time proofs
- Data retention policy
- Legal admissibility rules

---

## Table of Contents (Upcoming Only)

- BR-5.1 Institutional Time Continuity
- BR-5.2 Ordering Guarantees
- BR-5.3 TDV Linkage Across Boundaries
- BR-5.4 Memory Survivability
- BR-5.5 Drift Detection Hooks
- BR-5.6 Forbidden Temporal Shortcuts

---

## BR-5.1 Institutional Time Continuity

Institutional time is **not wall-clock time**.

> **Institutional time is the ordered accumulation of irreversible state transitions under constraint.**

Boundary Routing **MUST NOT**:
- reset time,
- fork time,
- reinterpret time,
- collapse multiple transitions into one.

Each routed transition extends a **single institutional timeline**, even across institutions.

---

## BR-5.2 Ordering Guarantees

Boundary Routing **MUST preserve**:

1. **Precedence**  
   A routed transition must occur *after* its originating execution.

2. **Non-Backdating**  
   No routed transition may be assigned an earlier effective time.

3. **Monotonicity**  
   Time references must advance or explicitly terminate.

4. **No Reordering**  
   Parallel routing paths must not be merged without explicit ordering rules.

Violating ordering guarantees invalidates routing.

---

## BR-5.3 TDV Linkage Across Boundaries

TDV must preserve **cross-boundary continuity**.

Requirements:

- Each routed transition must reference:
  - the originating `tdv_ref`
  - the resulting local `tdv_ref` (if accepted)
- TDV custody separation must be preserved.
- Verification must not depend on trusting either institution.

TDV linkage creates an **unbroken evidentiary chain** across boundaries.

---

## BR-5.4 Memory Survivability

Boundary Routing must survive:

- personnel changes,
- administrative turnover,
- institutional reorganization,
- system migration,
- political regime change.

Therefore:

- TDV references must remain resolvable over time.
- Memory must not depend on local databases alone.
- Loss of local records must not erase institutional history.

Memory survivability is a **design requirement**, not an operational preference.

---

## BR-5.5 Drift Detection Hooks

Cross-boundary execution increases drift risk.

Boundary Routing **MUST enable**:

- detection of missing transitions,
- detection of suppressed refusals,
- detection of reordered execution,
- detection of unverifiable evidence chains.

These are **signals**, not judgments.

Drift detection hooks are surfaced to governance or RSI, never handled inline.

---

## BR-5.6 Forbidden Temporal Shortcuts

The following invalidate Boundary Routing:

- wall-clock substitution for institutional time
- retroactive correction of time references
- silent consolidation of multiple transitions
- “eventual consistency” claims without ordering guarantees
- narrative reconciliation of timelines

Time shortcuts reintroduce trust implicitly and are forbidden.

---

## Completion Criteria

BR-5 is complete when:

1. Institutional time remains ordered across boundaries.
2. TDV preserves a continuous evidentiary chain.
3. Memory survives institutional change.
4. Drift becomes observable, not narratively managed.

---

**Next File:**  
`06_br6_trust_minimal_security_properties.md`

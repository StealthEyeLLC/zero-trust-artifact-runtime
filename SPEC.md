# Zero-Trust Artifact Runtime (ZTAR) — Formal Specification

This document defines the formal behavior, invariants, and outputs of the
Zero-Trust Artifact Runtime (ZTAR).

ZTAR exists to establish verifiable truth about execution:
what ran, under what constraints, and with what effects.

---

## Definitions

**Artifact**  
A static, identifiable unit of execution. Artifacts are immutable inputs.

**Constraint**  
An explicit, declared limit on execution, including but not limited to:
- Time
- CPU
- Memory
- I/O
- Network access
- Filesystem access

**Receipt**  
A structured, deterministic record of execution produced by ZTAR.
Receipts are the primary output.

---

## Inputs

ZTAR requires:

1. **Artifact Descriptor**
   - Identity and integrity of the artifact
   - No dynamic mutation allowed

2. **Constraint Set**
   - Explicit bounds for all controlled resources
   - Missing constraints are not inferred

3. **Execution Context**
   - Declared environment
   - No ambient or inherited state

---

## Execution Model

- Artifacts execute only within declared constraints
- No implicit retries or fallbacks
- No background or asynchronous execution
- No hidden state between runs

Execution either completes within bounds or halts.

---

## Output Classification

ZTAR produces exactly one outcome:

### COMPLETED
Artifact executed fully within all declared constraints.

### FAILED
Artifact executed but terminated with an error.

### HALTED
Execution was stopped due to constraint exhaustion or violation.

### REFUSED
Artifact or constraints violate ZTAR invariants.

---

## Invariants

The following invariants are mandatory:

- Explicit constraints for all controlled resources
- Deterministic execution given identical inputs
- No ambient authority
- No dynamic code generation
- No silent retries
- Complete receipt emission

Violation of any invariant results in `REFUSED`.

---

## Determinism

Given identical:
- Artifact
- Constraints
- Execution context

ZTAR will always produce identical receipts and outcome classification.

There is no learning, adaptation, or state carryover.

---

## Composition

ZTAR may be composed with other primitives provided:
- Receipts are not altered
- Constraints remain explicit
- Failure states propagate without suppression

ZTAR does not reinterpret outcomes.

---

## Non-Goals

ZTAR does not:
- Validate artifact correctness
- Prove intent
- Optimize performance
- Guarantee safety beyond declared constraints

ZTAR proves execution facts only.

---

## Summary

Zero-Trust Artifact Runtime is a deterministic execution primitive.
Its value comes from receipts, not trust.

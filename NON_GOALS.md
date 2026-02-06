# Zero-Trust Artifact Runtime (ZTAR) — Non-Goals

This document defines what ZTAR is explicitly not designed to do.

ZTAR enforces execution truth, not execution safety or correctness.

---

## ZTAR Does Not Judge Artifact Intent

ZTAR does not:
- Interpret what an artifact is “trying” to do
- Infer developer intent
- Determine whether behavior is desirable

Only observable execution is recorded.

---

## ZTAR Does Not Repair or Retry Execution

ZTAR does not:
- Retry failed executions
- Recover from crashes
- Heal partial state
- Perform compensating actions

Failure is surfaced, not masked.

---

## ZTAR Does Not Optimize Execution

ZTAR does not:
- Improve performance
- Reorder instructions
- Optimize resource usage
- Modify artifacts for efficiency

Artifacts run as-is, within bounds.

---

## ZTAR Does Not Enforce Policy Semantics

ZTAR does not:
- Decide whether execution should be allowed
- Interpret policy meaning
- Enforce business rules

ZTAR enforces declared constraints only.

---

## ZTAR Does Not Operate Continuously

ZTAR does not:
- Run as a daemon
- Monitor systems over time
- Observe future executions
- Maintain long-lived state

Each execution is isolated and explicit.

---

## ZTAR Does Not Provide Security Guarantees Beyond Scope

ZTAR does not:
- Prevent malicious logic
- Guarantee absence of exploits
- Protect against undeclared channels

Security claims are limited strictly to declared constraints.

---

## Summary

ZTAR is intentionally narrow.

Its role is to produce unambiguous execution receipts,
not to solve higher-level safety or policy problems.

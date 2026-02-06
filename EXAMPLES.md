# Zero-Trust Artifact Runtime (ZTAR) — Examples

This document provides concrete examples of ZTAR executions.
Examples are intentionally minimal and factual.

---

## Example 1: Successful Bounded Execution

**Artifact**
- Script: `process_data.sh`
- Hash: `sha256:abc123`

**Constraints**
- CPU time: 500ms
- Memory: 128MB
- Network: disabled
- Filesystem: read-only `/data/input`

**Execution Result**
`COMPLETED`

**Receipt Summary**
- CPU used: 212ms
- Memory peak: 64MB
- Files accessed: `/data/input/file.csv`
- Network access: none
- Exit code: 0

---

## Example 2: Constraint Exhaustion

**Artifact**
- Script: `analyze_large_file.sh`
- Hash: `sha256:def456`

**Constraints**
- CPU time: 100ms
- Memory: 64MB
- Network: disabled

**Execution Result**
`HALTED`

**Receipt Summary**
- CPU used: 100ms (limit reached)
- Memory peak: 58MB
- Files accessed: `/data/input/large.bin`
- Exit code: none (terminated)

---

## Example 3: Execution Failure

**Artifact**
- Script: `transform.sh`
- Hash: `sha256:789ghi`

**Constraints**
- CPU time: 300ms
- Memory: 128MB
- Network: disabled

**Execution Result**
`FAILED`

**Receipt Summary**
- CPU used: 34ms
- Memory peak: 12MB
- Error: invalid input format
- Exit code: 1

---

## Example 4: Invariant Violation

**Artifact**
- Script: dynamically generated code

**Constraints**
- CPU time: unspecified
- Memory: unspecified

**Execution Result**
`REFUSED`

**Reason**
- Artifact is not immutable
- Constraints are incomplete

---

## Summary

These examples illustrate all ZTAR outcomes:
- `COMPLETED`
- `FAILED`
- `HALTED`
- `REFUSED`

ZTAR records execution truth.
Nothing more.

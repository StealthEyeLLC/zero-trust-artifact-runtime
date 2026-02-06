# Zero-Trust Artifact Runtime (ZTAR)

Zero-Trust Artifact Runtime (ZTAR) is a deterministic runtime that executes
artifacts under explicit constraints and emits verifiable execution receipts
instead of relying on trust.

ZTAR does not assume correctness.
It proves what executed, under what limits, and with what effects.

---

## What ZTAR Guarantees

- Explicit execution constraints
- Deterministic runtime behavior
- Complete execution receipts
- No hidden state or background execution
- Refusal on invariant violation

ZTAR never executes implicitly.

---

## What ZTAR Does NOT Do

- No dynamic code generation
- No adaptive behavior
- No silent retries
- No background daemons
- No trust-based execution

If execution cannot be proven, ZTAR refuses.

---

## Output

ZTAR emits structured execution receipts that include:
- Artifact identity
- Declared constraints
- Resources accessed
- Execution boundaries
- Final outcome classification

Receipts are the product.

---

## Failure Modes

- **REFUSED** — artifact or constraints violate invariants
- **HALTED** — execution exceeded declared limits
- **FAILED** — artifact executed but failed
- **COMPLETED** — execution completed within bounds

---

## Relationship to StealthEye

ZTAR is a core StealthEye runtime primitive.
Other tools may depend on ZTAR to establish execution truth.

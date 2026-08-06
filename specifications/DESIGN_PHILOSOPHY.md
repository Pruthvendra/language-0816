# Design Philosophy

**Version: 0.1**  
**Status: Draft**  
**Date: August 2026**

---

## 1. Purpose

This document translates the three locked constitutional decisions of Project 0816 into architectural guidance for Harven. It exists so that every future design decision — syntax, type system, compiler behavior, and standard library — can be traced back to a single, coherent philosophy.

---

## 2. Harven Design Philosophy

&gt; Harven produces trustworthy software by making programmer intent explicit, mutation intentional, and compiler guarantees understandable.

---

## 3. Constitutional Foundation

The following decisions are locked and permanent. This document does not rewrite them; it references them.

### Issue #1 — Explicit Intent Expression
Harven's language philosophy is Explicit Intent Expression. Syntax makes purpose visible and unambiguous to humans, AI systems, and compilers.

### Issue #2 — Value Immutability by Default
Values are immutable by default. `let` creates immutable values. `mut` explicitly permits mutation. Function parameters are immutable by default. Mutation is always an explicit and intentional decision.

### Issue #3 — Enforce First, Explain Second
The compiler exists to protect language guarantees, not merely to reject programs. Enforcement identifies the violated language rule and the program location of the violation. The compiler makes an explanation of the violated language rule available. Enforcement and explanation are distinct capabilities of the compiler. They are never conflated.

---

## 4. How They Work Together

The three constitutional decisions form a single chain:

**Explicit Intent Expression** requires that purpose be visible in the code itself. A human auditor must be able to read a `.hvn` file and understand what every program element means, why it exists, and what it promises — without reading documentation or trusting the author.

**Value Immutability by Default** makes the default state predictable. When a developer sees `let`, they know the value will never change. When they see `mut`, they know mutation was intentional. The absence of `mut` is itself a visible promise.

**Enforce First, Explain Second** ensures that when intent is wrong, the compiler responds with clarity. It blocks compilation because a guarantee was violated. It makes the explanation available separately, so the auditor can triage quickly and learn deeply when needed.

Together, they produce a language where:
- Intent is visible by default.
- Change is explicit by default.
- Violations are caught and separated from lessons.

This is how Harven earns trust.

---

## 5. Architectural Principles

The following principles are derived directly from the Constitution. Every principle traces to Issue #1, #2, or #3.

| Principle | Source | Meaning |
|---|---|---|
| The default state of any Harven program element must reveal its intent without requiring additional context. | Issue #1 | If intent is not visible in the syntax, the design is wrong. |
| Mutation is an exceptional capability, not the baseline. | Issue #2 | The absence of a mutation keyword is a guarantee of stability. |
| Function boundaries must preserve the caller's expectations. | Issue #2 | A function cannot modify what it receives unless explicitly permitted. |
| The compiler is a guardian of language guarantees. | Issue #3 | The compiler does not merely translate; it protects. |
| Error output serves two distinct purposes and must never confuse them. | Issue #3 | Enforcement and explanation are separate capabilities, never mixed. |

No architectural principle may be added that does not trace to Issues #1, #2, or #3.

---

## 6. Design Decision Hierarchy

Harven's design authority flows downward. Lower layers must never contradict higher layers.

## Design Integrity Rule

Harven evolves from the top down.

No design decision may contradict a higher layer.

When uncertainty exists:

- Constitution wins over Design Philosophy.
- Design Philosophy wins over Specifications.
- Specifications win over Implementation.

If a conflict cannot be resolved, the lower-layer proposal must be rejected or revised.

---

## 7. Out of Scope

This document intentionally does NOT define:

- Grammar or syntax details
- Keywords or reserved words
- Parser architecture
- Compiler internals or algorithms
- Memory model or management strategy
- Runtime behavior or ABI
- Optimization strategy
- Standard library scope or API
- Error codes or numbering schemes
- Diagnostics formatting or presentation
- IDE or LSP behavior
- Package manager design
- Build system architecture

These belong to future specifications, not to philosophy.

---

## 8. Future Specification Topics

The following questions are important but remain unanswered. They will be decided through future Issues, not through this document.

- Type system philosophy (static vs dynamic, nominal vs structural)
- Concurrency and parallelism model
- Memory management approach (manual, garbage collected, or hybrid)
- Module and package system philosophy
- Error handling mechanism (exceptions, results, panics, or other)
- String, collection, and numeric type semantics
- Foreign function interface philosophy
- Standard library scope and guarantees
- Backward compatibility policy for language evolution
- Governance model for RFCs and proposals" in file

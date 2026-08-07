# Type System Philosophy

**Version: 0.1**  
**Status: Draft**  
**Date: August 2026**

---

## 1. Purpose

This document translates Issue #4 into architectural guidance for Harven's type system. It defines how types express intent, how they are compared, and what the compiler guarantees.

---

## 2. Constitutional Foundation

Issue #4 is locked:

&gt; Harven's type system is static. Type identity is nominal by default. Names carry semantic intent. Any future structural compatibility mechanism must be explicitly defined in the Language Specification and must preserve Explicit Intent Expression and compiler guarantees.

---

## 3. Type System Principles

The following principles are derived directly from the Constitution. Every principle traces to Issue #4 or Issue #1.

| Principle | Source | Meaning |
|---|---|---|
| Every program element has a statically known type before execution. | Issue #4 | Type correctness is established before execution. Programmer intent remains visible whether types are explicitly declared or inferred by the language. |
| Types are compared by name, not by shape. | Issue #4 | `UserId` and `ProductId` are incompatible even if both are strings. |
| The compiler rejects programs with type mismatches. | Issue #4 | Enforcement happens before execution. |
| Types express semantic intent, not merely representation. | Issue #1 | `Money` means currency. `Count` means quantity. They are not interchangeable. |

No type system principle may be added that does not trace to Issues #1 or #4.

---

## 4. Design Integrity

This document defines the philosophy of Harven's type system.

It does not prescribe:

- language syntax
- parser behavior
- compiler algorithms
- optimization techniques
- runtime implementation

If any future specification conflicts with the constitutional decisions established by Issue #4, the specification must be revised.

---

## 5. Out of Scope

This document does NOT define:

- Specific type keywords or syntax
- Type inference rules
- Generic or parametric type mechanisms
- Trait, protocol, or interface definitions
- Structural record syntax
- FFI type boundary rules
- Compiler type-checking algorithms

These belong to the Language Specification and Compiler Specification.

---

## 6. Future Specification Topics

The following questions are important but remain unanswered. They will be decided through future Issues, not through this document.

- Type inference philosophy
- Generic type system design
- Trait/protocol mechanism
- Error type design
- Null safety approach

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

| Principle | Source | Meaning |
|---|---|---|
| Every value has a type known at compile time. | Issue #4 | No runtime type discovery. Intent is visible in source. |
| Types are compared by name, not by shape. | Issue #4 | `UserId` and `ProductId` are incompatible even if both are strings. |
| The compiler rejects programs with type mismatches. | Issue #4 | Enforcement happens before execution. |
| Type annotations express semantic intent, not just memory layout. | Issue #1 | `Money` means currency. `Count` means quantity. They are not interchangeable. |

---

## 4. Out of Scope

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

## 5. Future Specification Topics

- Type inference philosophy
- Generic type system design
- Trait/protocol mechanism
- Error type design
- Null safety approach

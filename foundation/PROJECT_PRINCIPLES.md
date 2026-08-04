# Project Principles

**Version: 0.1**  
**Status: Draft**  
**Date: August 3, 2026**

---

## The One Sentence

&gt; Every line of code written for Harven must make the language easier to trust.

Everything else is secondary.

---

## The Trust Stack

| Layer | Question | How We Earn It |
|---|---|---|
| **Behavioral** | Does it do what it says? | Consistent, predictable semantics. |
| **Correctness** | Can I prove it is right? | Strong static analysis, formal verification hooks. |
| **Security** | Is it safe by default? | Secure defaults, explicit unsafe blocks. |
| **Transparency** | Can I understand why it works? | Open governance, documented decisions. |
| **Durability** | Will it still work in 2035? | Backward compatibility, stable releases. |

---

## Non-Negotiables

1. **No code without documentation.**  
   The specification leads. The implementation follows.

2. **No AI-generated code without human ownership.**  
   AI can draft. Humans must understand, review, and sign off.

3. **No breaking changes without a migration path.**  
   Trust dies when working code stops working.

4. **No security as an afterthought.**  
   If it is not secure by default, it is not in the language.

5. **No complexity without justification.**  
   Every feature pays rent in cognitive load.

---

## Final Principle

&gt; If a decision makes Harven harder to trust — even if it makes it faster, more popular, or more feature-rich — that decision is wrong.

This principle sits above the compiler. Above the specification. Above every contributor.

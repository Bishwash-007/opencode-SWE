# Spec-Driven Development

Write a clear specification before writing any code. No spec, no implementation.

## Overview

Every non-trivial change starts with a written spec that answers: what, why, how, and how we'll know it works. Agents must not write implementation code until a spec exists and is reviewed.

## When to Use

- Starting a new feature or module
- Making architectural changes
- Adding or modifying APIs
- Any change touching more than one file

## Process

1. **Interview**: Clarify requirements until ~95% confidence. Ask one question at a time.
2. **Spec**: Write a PRD covering objectives, commands, structure, code style, testing, and boundaries.
3. **Review**: The spec must be reviewed before implementation begins.
4. **Lock**: Once reviewed, the spec becomes the source of truth. Changes require explicit re-review.

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "I'll write the spec after the code" | Code without spec drifts from intent. Spec first. |
| "It's too small for a spec" | Small changes compound into technical debt. Spec anyway. |
| "The user knows what they want" | Users often underspecify. Interview until clarity. |

## Red Flags

- Implementation starts before spec review
- Spec written after code exists
- Code diverges from spec without re-review

## Verification

- A written spec exists and is reviewed
- Every code change maps back to spec requirements
- Spec updated when requirements change
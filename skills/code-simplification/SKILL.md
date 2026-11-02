# Code Simplification

Reduce complexity while preserving exact behavior. Chesterton's Fence — understand why something exists before changing it. Rule of 500 — functions over 500 lines need refactoring.

## Overview

Code that works but is hard to read is technical debt. Simplify aggressively, but never change behavior without understanding the original intent.

## When to Use

- Code works but is hard to read or modify
- Functions over 500 lines
- Deeply nested conditionals
- Duplicate logic across files

## Process

1. **Understand** — why does this code exist? (Chesterton's Fence)
2. **Measure** — current complexity, test coverage
3. **Simplify** — extract functions, remove duplication, flatten nesting
4. **Verify** — behavior unchanged, tests still pass
5. **Commit** — simplification as its own commit

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "It works, don't touch it" | Unmaintainable code is a liability. |
| "I'll simplify later" | Later never comes. Simplify now. |
| "I don't know why it was written this way" | Investigate before changing. Document findings. |

## Red Flags

- Functions >500 lines
- Deeply nested conditionals (>3 levels)
- Duplicate logic (>2 occurrences)
- No tests for the code being simplified

## Verification

- All existing tests pass after simplification
- Behavior is unchanged
- Complexity is measurably reduced
- Simplification is its own commit
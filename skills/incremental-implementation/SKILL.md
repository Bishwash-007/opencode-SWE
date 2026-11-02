# Incremental Implementation

Implement in thin vertical slices — implement, test, verify, commit. Feature flags, safe defaults, rollback-friendly changes.

## Overview

Never implement everything at once. Build in minimal, working slices that can be verified independently. Each slice should be complete enough to test, commit, and rollback if needed.

## When to Use

- Any change touching more than one file
- Feature development
- Refactoring existing code
- Bug fixes

## Process

1. **Slice the work** — identify the thinnest vertical slice
2. **Implement the slice** — minimal code to make it work
3. **Write tests** — tests for the slice behavior
4. **Verify** — run tests, lint, build
5. **Commit** — atomic commit for the slice
6. **Repeat** — move to the next slice

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "I'll implement everything then test" | Untested code accumulates bugs faster than they can be found. |
| "Feature flags are overkill" | Rollback safety is cheaper than hotfixes. |
| "This slice isn't user-facing yet" | Internal slices still need verification. |

## Red Flags

- Large PRs (>100 lines) without intermediate commits
- Implementation without tests
- No rollback plan
- Changes committed without verification

## Verification

- Each slice has passing tests
- Each slice is committed atomically
- Rollback is possible for every slice
- Build and lint pass after each slice
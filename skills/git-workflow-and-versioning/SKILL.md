# Git Workflow and Versioning

Trunk-based development, atomic commits, change sizing (~100 lines), the commit-as-save-point pattern.

## Overview

Every change is committed atomically with a clear message. Small, focused commits make review easier, rollback safer, and history meaningful.

## When to Use

- Making any code change (always)
- Creating branches or tags
- Merging or rebasing
- Releasing versions

## Process

1. **Trunk-based** — work on main, short-lived feature branches
2. **Atomic commits** — one logical change per commit (~100 lines max)
3. **Save-point commits** — commit before risky operations
4. **Clear messages** — describe what and why, not how
5. **Review before merge** — no direct pushes to main

## Commit Message Format

```
type: subject

body (optional)

footer (optional)
```

Types: feat, fix, docs, style, refactor, test, chore

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "One big commit is fine" | Large commits are hard to review and revert. |
| "I'll clean up history later" | History is permanent. Make it right now. |
| "It's just a small change" | Small changes still need clear messages. |

## Red Flags

- Commits >100 lines
- Vague commit messages ("fix stuff", "update")
- Direct pushes to main
- No save-point commits before risky changes

## Verification

- Commits are atomic and focused
- Commit messages follow format
- Changes reviewed before merge
- No direct pushes to protected branches
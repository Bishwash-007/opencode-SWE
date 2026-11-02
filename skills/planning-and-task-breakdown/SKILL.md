# Planning and Task Breakdown

Decompose specifications into small, verifiable tasks with acceptance criteria and dependency ordering.

## Overview

Break every spec into atomic, independently verifiable tasks. Each task should be small enough to complete in one session, testable, and have clear acceptance criteria.

## When to Use

- A reviewed spec exists
- Implementation is ready to begin
- Multiple related changes are needed

## Process

1. **Read the spec** — understand objectives and boundaries
2. **Identify tasks** — break into atomic units (each <100 lines of change)
3. **Order tasks** — resolve dependencies before dependents
4. **Define acceptance criteria** — how do we know each task is done?
5. **Create tickets** — one file per task, each declaring blocking edges

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "I'll figure it out as I go" | Unplanned work leads to rework and drift. |
| "Tasks are too small to track" | Small tasks are easier to verify and revert. |
| "Dependencies will sort themselves" | Explicit ordering prevents blocked work. |

## Red Flags

- Tasks larger than ~100 lines of change
- Missing acceptance criteria
- No dependency ordering
- Implementation starts before task breakdown

## Verification

- Every spec has corresponding tasks
- Each task has acceptance criteria
- Tasks are ordered by dependency
- Tasks can be verified independently
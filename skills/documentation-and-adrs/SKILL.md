# Documentation and ADRs

Architecture Decision Records, API docs, inline documentation standards — document the why, not just the what.

## Overview

Every architectural decision and API change must be documented. Future you (and your team) will thank you for understanding why decisions were made.

## When to Use

- Making architectural decisions
- Changing or adding APIs
- Introducing new dependencies or patterns
- Changing project structure

## Process

1. **ADR** — record architecture decisions: context, decision, consequences, alternatives considered
2. **API docs** — document endpoints, parameters, responses, errors
3. **Inline docs** — explain non-obvious code, not obvious code
4. **Review** — docs reviewed with code changes

## ADR Template

```
# ADR-XXXX: Title

## Status
Proposed / Accepted / Deprecated / Superseded

## Context
What problem are we solving?

## Decision
What did we decide?

## Consequences
Positive and negative outcomes of this decision.

## Alternatives Considered
Other options and why they were rejected.
```

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "The code is self-documenting" | Code explains what, not why. |
| "I'll document later" | Later never comes. Document now. |
| "Everyone knows why" | Team members change. Context is lost. |

## Red Flags

- Architecture changes without ADR
- API changes without documentation
- Non-obvious code without comments
- Decisions made without recording alternatives

## Verification

- ADRs exist for architectural decisions
- APIs have documentation
- Non-obvious code is explained
- Docs reviewed with code changes
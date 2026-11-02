# Security and Hardening

OWASP Top 10 prevention, auth patterns, secrets management, dependency auditing, three-tier boundary system.

## Overview

Security is not an afterthought. Every change that touches user input, authentication, data storage, or external integrations must be reviewed for security implications.

## When to Use

- Handling user input
- Authentication or authorization
- Data storage or retrieval
- External API integrations
- Dependency changes

## Process

1. **Identify boundaries** — input, auth, data, external APIs
2. **Apply OWASP Top 10** — check for injection, broken auth, sensitive data exposure, etc.
3. **Secrets management** — never hardcode credentials; use environment variables
4. **Input validation** — validate all external input at the boundary
5. **Dependency audit** — check for vulnerable dependencies
6. **Review** — security review before merge

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "Security can be added later" | Retrofitting security is exponentially more expensive. |
| "It's internal, no one will attack it" | Internal threats and mistakes are common. |
| "Just one hardcoded key" | One key leads to many. Use env vars always. |

## Red Flags

- Hardcoded credentials or secrets
- Unvalidated user input
- Missing authentication/authorization checks
- Outdated dependencies with known vulnerabilities
- No security review for auth-related changes

## Verification

- All user input is validated at boundaries
- No hardcoded secrets in code
- AuthZ/AuthN checks present where needed
- Dependencies audited for vulnerabilities
- Security review completed before merge
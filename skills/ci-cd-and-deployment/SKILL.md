# CI/CD and Deployment

Design, review, and validate CI/CD pipelines and deployment strategies. Automate testing, ensure rollback capability, and gate production deploys.

## Overview

CI/CD pipelines automate building, testing, and deploying code. Every change must pass tests before reaching staging, and production deploys require explicit approval with rollback capability.

## When to Use

- Setting up build pipelines
- Configuring deployment workflows
- Adding automated testing to pipelines
- Configuring environment promotion (staging → production)
- Reviewing pipeline security

## Process

1. **Define pipeline stages** — build, test, security scan, deploy staging, deploy prod
2. **Configure triggers** — push to main, pull requests, tags, schedules
3. **Add quality gates** — tests must pass before deploy
4. **Configure approval gates** — production requires manual approval
5. **Add rollback steps** — every deploy can be reverted
6. **Set up notifications** — Slack, email, PagerDuty on failures

## Pipeline Stages

```
┌─────────┐    ┌─────────┐    ┌─────────────┐    ┌──────────────┐    ┌─────────┐
│  Build  │ →  │  Test   │ →  │ Security    │ →  │ Deploy Staging│ →  │ Deploy  │
│  (lint, │    │ (unit,  │    │ scan        │    │ (auto)        │    │ Prod    │
│  compile│    │  integ) │    │ (SAST, dep) │    │               │    │ (manual)│
└─────────┘    └─────────┘    └─────────────┘    └──────────────┘    └─────────┘
```

## Deployment Strategies

| Strategy | Use Case | Risk |
|----------|----------|------|
| Blue-green | Zero-downtime, instant rollback | Double infrastructure cost |
| Canary | Gradual traffic shift, monitor | Complex routing |
| Rolling | Incremental replacement | Partial old/new versions |
| Recreate | Simple, downtime acceptable | Downtime during deploy |

## Quality Gates

- **Build** — compile, lint, type-check pass
- **Unit tests** — 80%+ coverage, all pass
- **Integration tests** — service boundaries verified
- **Security scan** — SAST, dependency vulnerability check
- **Container scan** — image vulnerability scan
- **Performance** — no regression in key metrics

## Rollback Capability

- **Every deploy tagged** — git tags for every release
- **Rollback command** — one-command revert to previous version
- **Database migrations** — forward and backward compatible
- **Feature flags** — disable features without redeploy
- **Health checks** — automatic rollback on unhealthy instances

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "I'll deploy manually" | Manual deploys are inconsistent and error-prone. |
| "Tests slow down deploy" | Slow tests are better than broken production. |
| "No rollback needed" | Something will break. Have a plan. |
| "Prod deploy is fine auto" | Production changes require human approval. |

## Red Flags

- Production deploys without manual approval
- No automated tests in pipeline
- No rollback mechanism
- Secrets hardcoded in pipeline config
- Pipeline runs as root/admin
- No security scanning

## Verification

- Pipeline runs on every push and PR
- Tests are required before deploy
- Production deploy requires manual approval
- Rollback procedure documented and tested
- Secrets stored in CI/CD secret store, not in code
- Security scanning integrated
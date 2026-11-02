# Performance Optimization

Measure-first approach — Core Web Vitals targets, profiling workflows, bundle analysis, anti-pattern detection. Don't optimize what you haven't measured.

## Overview

Performance work must be driven by measurement, not assumptions. Profile first, identify bottlenecks, optimize, then verify improvement.

## When to Use

- Performance requirements exist
- Suspected regressions
- Slow page loads or API responses
- High bundle sizes
- Before production release

## Process

1. **Measure** — capture baseline metrics (Core Web Vitals, API latency, bundle size)
2. **Profile** — identify bottlenecks (CPU, memory, network, rendering)
3. **Optimize** — address the largest bottlenecks first
4. **Verify** — confirm improvement with measurements
5. **Document** — record before/after metrics

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "I know what's slow" | Assumptions are wrong more often than data. Measure first. |
| "Premature optimization is bad" | Optimizing after measuring is not premature. |
| "It's fast enough" | Define "enough" with measurable targets. |

## Red Flags

- Optimization without baseline metrics
- No profiling data
- Changes without before/after comparison
- Bundle size growth without investigation

## Verification

- Baseline metrics captured before changes
- Profiling identifies actual bottlenecks
- After-improvement metrics show measurable gain
- Performance targets met or exceeded
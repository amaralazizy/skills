---
name: sprint-prioritization
description: Use when prioritizing tasks for a sprint, handling stakeholder demands vs team capacity, or making trade-off decisions between competing priorities
---

# Sprint Prioritization

## Overview

Prioritize sprint work using evidence-based criteria rather than pressure or volume metrics. The goal is maximizing business value delivered while maintaining sustainable team health.

## Core Principles

### Decision Hierarchy

```
1. Safety & Security (non-negotiable)
   - Security vulnerabilities
   - Data breaches
   - Compliance violations

2. Customer Pain (active complaints)
   - Bugs affecting active users
   - Broken core functionality
   - Revenue-impacting issues

3. Sunk Cost & ROI
   - Work in progress (WIP) with high completion %
   - High-investment items nearly done

4. Strategic Value
   - Features aligned with quarterly goals
   - Revenue-generating capabilities
   - Customer retention drivers

5. Technical Debt
   - Performance optimization
   - Code quality improvements
   - Infrastructure updates
```

### The Sunk Cost Principle

**Always complete near-complete work before starting new work.**

A task that is 80% done costs 80% of its story points in total effort. Abandoning it wastes that investment.

```
WIP COMPLETION PRIORITY:
- 80% complete → finish it (1 SP left)
- 50% complete → evaluate: finish or rollback
- 10% complete → can defer without major waste
```

## When to Use

### Scenario Patterns

**Stakeholder demands priority:**

- Stakeholder requests specific feature "THIS sprint"
- Compare against current sprint work using hierarchy
- If lower priority, acknowledge but set expectations

**Pressure to show velocity:**

- PM wants "most tickets closed"
- Push back: velocity ≠ business value
- Track value delivered, not tickets closed

**Capacity uncertainty:**

- Team member departure mid-sprint
- Reassess commitment BEFORE selecting work
- Formula: remaining_devs × 6 SP = realistic_capacity

## Quick Reference

| Situation               | Action                                 |
| ----------------------- | -------------------------------------- |
| Security vulnerability  | Do first, always                       |
| Customer-complained bug | Do before new features                 |
| 80% complete work       | Finish before starting new             |
| Stakeholder demands     | Compare to hierarchy, set expectations |
| Reduced capacity        | Reduce commitment, not quality         |
| Easy tickets available  | Avoid - often low value                |

## Common Mistakes

### Mistake 1: Starting New Work Instead of Finishing WIP

**Wrong:** "This new feature is more exciting, I'll come back to the bug later"

**Right:** Bug is 80% done = 1 SP remaining. Complete it first.

### Mistake 2: Committing to Original Capacity with Reduced Team

**Wrong:** "We'll still hit 18 SP, we just need to work harder"

**Right:** 2 devs instead of 3 = 12-13 SP realistic. Adjust commitment.

### Mistake 3: Accepting All Stakeholder Requests

**Wrong:** "The stakeholder demanded login page, we have to do it"

**Right:** Compare to hierarchy. If security or customer pain ranks higher, explain trade-offs.

### Mistake 4: Optimizing for Ticket Count

**Wrong:** "Pick the easiest tasks to show high velocity"

**Right:** Track value delivered, not tickets closed. Easy tasks often = low impact.

## Communication Templates

### Stakeholder Pushback

```
"Acknowledged. We've reviewed your request against our current sprint commitments:

1. [Higher priority item] - [reason]
2. [Higher priority item] - [reason]

We'll prioritize [their request] in the next sprint. Can we sync to confirm the exact scope for that?"
```

### Capacity Reduction

```
"Updating sprint commitment: [old] SP → [new] SP

Reason: [departure/reassignment/leave]

Prioritized:
1. [Item 1] - [reason]
2. [Item 2] - [reason]

We'll carry over any incomplete work. Updates to follow."
```

### Incomplete Work Decision

```
"Options for incomplete [item]:
1. Carry over - finish next sprint (recommended for >50% done)
2. Roll back - revert changes if blocking other work
3. Defer - put back in backlog

Recommendation: [option] because [reason]"
```

## Red Flags - STOP

- Starting new work when WIP is >50% complete
- Committing to original capacity with reduced team
- Accepting all stakeholder requests without evaluation
- Selecting tasks by difficulty instead of value
- Treating all requests as equally urgent
- Prioritizing velocity over value delivered

## Rationalization Table

| Excuse                                  | Reality                                        |
| --------------------------------------- | ---------------------------------------------- |
| "The stakeholder demanded it"           | Demands don't override evidence-based priority |
| "We need to show velocity"              | Velocity without value = misleading metrics    |
| "It's only 20% done, not much invested" | 20% of 13 SP = 2.6 SP wasted                   |
| "We can fit more in"                    | Can't - team capacity is fixed                 |
| "Everyone else is doing it"             | Status quo ≠ best practice                     |

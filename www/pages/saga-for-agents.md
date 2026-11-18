---
type: concept
title: Saga for Agent Workflows
description: Give each important agent step an undo action, so a failed multi-step run can be rolled back instead of left half done.
status: stable
release: launch
tags:
  - fault-tolerance
  - persistence
clusters:
  - classical
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://microservices.io/patterns/data/saga.html
    title: "Pattern: Saga"
    author: Richardson, C.
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://doi.org/10.1145/38713.38742
    title: Sagas
    author: Garcia-Molina, H.; Salem, K.
    year: 1987
    verified: 2026-11-10
    grade: secondary
  - resource: https://temporal.io/blog/saga-pattern-made-easy
    title: "Saga design pattern explained: Benefits, use cases, and implementation"
    author: Fortuna, E.
    year: 2023
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: saga-for-agents
related:
  - plan-approval-gate
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: saga-for-agents.svg
  alt: Three forward steps — book flight, charge card, confirm — where the third fails; a highlighted refund-charge compensation and then a cancel-booking compensation run backwards from the failure.
  caption: The bottom row only runs on a bad day, which makes it the least-exercised code in the whole workflow.
---

## Intent

Pair each important step with an undo action, so a failed run can be rolled back.

## Context & Forces

Across services, Richardson notes, two-phase commit is not an option.

## Structure

Garcia-Molina and Salem (1987) define the saga: either all its transactions complete, or compensating transactions amend the partial execution.

## Consequences & Trade-offs

Compensation code runs rarely, so test it on purpose.

## Related Patterns

- Exception Handling and Recovery
- Plan Approval Gate

---
type: concept
title: Idempotency Keys for Agent Actions
description: Attach a stable idempotency key to each side-effecting call so a retried or replayed request is executed once, as Stripe and Temporal describe.
status: stable
release: ops-evals
tags:
  - reliability
  - tool-use
  - persistence
aliases:
  - Idempotency-Key header (Stripe)
  - safe-retry keys
  - duplicate-action suppression
  - idempotent activities (Temporal)
clusters:
  - evaluation-testing
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://docs.stripe.com/api/idempotent_requests
    title: Idempotent requests
    author: Stripe
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://docs.temporal.io/activity-definition
    title: Activity Definition
    author: Temporal
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: idempotent-agent-actions
related:
  - saga-for-agents
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: idempotent-agent-actions.svg
  alt: An agent's tool call carries a key through a highlighted idempotency store; a first request executes the effect, a retry with the same key returns the stored result without executing again.
  caption: A retry with the same key returns the saved first response instead of acting again.
x-oldsite-subdeck: Determinism & Replay
---

## Intent

Make a side-effecting action take effect once, even when it is retried or replayed.

## Context & Forces

Temporal's documentation says activities may be executed more than once.

## Structure

For API v1, Stripe returns the saved response of an earlier request to retries with the same Idempotency-Key.

## Consequences & Trade-offs

Stripe v1 can remove keys at least 24 hours old, so protection is bounded in time.

## Related Patterns

- Saga for Agent Workflows
- Exception Handling and Recovery

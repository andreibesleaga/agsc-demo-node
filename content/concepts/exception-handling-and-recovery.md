---
type: concept
title: Exception Handling and Recovery
description: "Classify each failure, retry short faults with limits, switch route for lasting ones, and report reduced results honestly."
status: stable
release: ops-evals
tags:
  - fault-tolerance
  - observability
aliases:
  - retry / fallback / graceful degradation
  - transient-fault handling for agents
  - Retry pattern (Azure Architecture Center)
  - node retry policy (LangGraph)
clusters:
  - operations-reliability
date: 2026-08-18
modified: 2026-09-29
sources:
  - resource: https://learn.microsoft.com/en-us/azure/architecture/patterns/retry
    title: "Retry pattern"
    author: "Microsoft"
    year: 2024
    verified: 2026-09-29
    grade: primary
  - resource: https://learn.microsoft.com/en-us/azure/architecture/best-practices/transient-faults
    title: "Transient fault handling"
    author: "Microsoft"
    year: 2026
    verified: 2026-09-29
    grade: secondary
  - resource: https://docs.langchain.com/oss/python/langgraph/use-graph-api
    title: "Use the graph API"
    author: "LangChain"
    year: 2026
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: exception-handling-and-recovery
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: exception-handling-and-recovery.svg
  alt: A failed call enters a highlighted classify box; transient faults go to a bounded retry with backoff that runs the call again, lasting faults and used-up retries go to a fallback route, and when no path is left the run degrades honestly with a stated partial result.
  caption: Retry only what can heal; everything else needs a second path or an honest partial answer.
---

## Intent

Keep a run going when calls fail: retry short faults, take another route for lasting ones, and say when a result is reduced.

## Context & Forces

Agents make many remote calls, and some fail. Blind retries waste money and overload services. Retrying a non-idempotent action can repeat it.

## Structure

1. **Classify.** Retry only transient faults. For HTTP, Microsoft names 429 and 5xx as typical candidates.
2. **Retry with limits.** Use growing, randomised delays. Microsoft: never retry endlessly; set a retry budget.
3. **Fall back.** Use an alternative service, or offer reduced functionality.
4. **Log** every retry.

LangGraph attaches a retry policy to each node; for common HTTP libraries it retries only 5xx errors by default.

## Consequences & Trade-offs

Runs survive routine faults. Retries add delay and cost. A silent fallback can hide a broken dependency.

## Related Patterns

- Saga for Agent Workflows
- Unbounded Loops

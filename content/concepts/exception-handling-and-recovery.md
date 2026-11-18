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
modified: 2026-11-18
sources:
  - resource: https://learn.microsoft.com/en-us/azure/architecture/patterns/retry
    title: "Retry pattern"
    author: "Microsoft"
    year: 2024
    verified: 2026-11-12
    grade: primary
  - resource: https://learn.microsoft.com/en-us/azure/architecture/best-practices/transient-faults
    title: "Transient fault handling"
    author: "Microsoft"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://docs.langchain.com/oss/python/langgraph/use-graph-api
    title: "Build checklist for the Graph API"
    author: "LangChain"
    year: 2026
    verified: 2026-11-18
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: exception-handling-and-recovery
related:
  - bulkhead-isolation
  - idempotent-agent-actions
  - termination-conditions
  - saga-for-agents
  - unbounded-agent-loops
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: exception-handling-and-recovery.svg
  alt: A failed call enters a highlighted classify box; transient faults go to a bounded retry with backoff that runs the call again, lasting faults and used-up retries go to a fallback route, and when no path is left the run degrades honestly with a stated partial result.
  caption: Retry only what can heal; everything else needs a second path or an honest partial answer.
domain_type: Safeguard
domain_role: policy
domain_links:
  guardsAgainst:
    - unbounded-agent-loops
---

## Intent

Keep a run going when calls fail: retry short faults, fall back for lasting ones.

## Context & Forces

Endless retries can keep an overloaded service from recovering.

## Structure

Classify faults, retry transient ones with limits and growing, randomised delays, fall back to an alternative or reduced service, and log every retry.

## Consequences & Trade-offs

Runs survive routine faults, but retries add delay.

## Related Patterns

- Saga for Agent Workflows
- Unbounded Loops
- Bulkhead Isolation
- Idempotency Keys for Agent Actions
- Termination and Exit Conditions

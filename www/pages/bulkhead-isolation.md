---
type: concept
title: Bulkhead Isolation
description: Give each agent, tenant or dependency its own bounded resource pool, so a fault or overload in one stays out of the others.
status: stable
release: classical
tags:
  - fault-tolerance
  - reliability
  - cost-control
aliases:
  - bulkhead pattern (Azure Architecture Center)
  - per-tenant resource pools
  - cell-based architecture
  - SemaphoreBulkhead / FixedThreadPoolBulkhead (resilience4j)
clusters:
  - classical
date: 2026-08-18
modified: 2026-11-18
sources:
  - resource: https://learn.microsoft.com/en-us/azure/architecture/patterns/bulkhead
    title: Bulkhead pattern
    author: Microsoft
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://resilience4j.readme.io/docs/bulkhead
    title: Bulkhead
    author: resilience4j
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://en.wikipedia.org/wiki/Bulkhead_pattern
    title: Bulkhead pattern
    author: Wikipedia
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: bulkhead-isolation
related:
  - unbounded-agent-loops
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: bulkhead-isolation.svg
  alt: Three agents each call a shared model service through their own bounded pool inside a dashed region; the highlighted pool A is saturated and its path is crossed out, while pools B and C keep flowing to the service.
  caption: A pool per consumer turns one agent's runaway into one agent's outage.
x-oldsite-subdeck: Reliability & Microservices
---

## Intent

Confine a failing element by giving each agent, tenant or dependency its own bounded resource pool.

## Context & Forces

Microsoft says excessive load or failure in a service affects all its consumers.

## Structure

Microsoft says to isolate application elements into pools so that if one fails, the others continue to function.

## Consequences & Trade-offs

Microsoft lists isolation from cascading failure and priority pools for critical consumers as benefits.

## Related Patterns

- Exception Handling and Recovery
- Unbounded Loops

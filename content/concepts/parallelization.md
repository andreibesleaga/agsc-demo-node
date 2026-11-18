---
type: concept
title: Parallelization
description: "Run independent subtasks at once and combine the results, either by splitting the work or by running the same task several times."
status: stable
release: launch
tags:
  - concurrency
  - ensemble
aliases:
  - sectioning and voting (Anthropic)
  - concurrent orchestration (Azure)
  - fan-out fan-in
  - scatter-gather
  - parallel fan-out and gather (Google ADK)
clusters:
  - foundational
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://www.anthropic.com/research/building-effective-agents
    title: "Building effective agents"
    author: "Schluntz, E.; Zhang, B."
    year: 2024
    verified: 2026-11-12
    grade: primary
  - resource: https://adk.dev/workflows/patterns/
    title: "Workflow patterns"
    author: "Google"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://developers.googleblog.com/en/agent-development-kit-easy-to-build-multi-agent-applications/
    title: "Agent Development Kit: Making it easy to build multi-agent applications"
    author: "Huizenga, E.; Yang, B."
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns
    title: "AI agent orchestration patterns"
    author: "Kittel, C.; Siemens, C."
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: parallelization
related:
  - deep-research-loop
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: parallelization.svg
  alt: One input fans out to three branches that run at the same time; their outputs converge on a single highlighted aggregate step, done by code or by a model.
  caption: Adding a branch is easy; the one box everything converges on is where correctness is actually decided.
---

## Intent

Run independent subtasks at the same time and combine the results.

## Context & Forces

Doing independent work in sequence wastes time.

## Structure

Anthropic names two variants (Schluntz and Zhang, 2024): sectioning into parallel subtasks, and voting by running the same task several times.

## Consequences & Trade-offs

Time is set by the slowest branch, and cost grows with each branch.

## Related Patterns

- The Deep Research Loop
- Agents as Tools
- Blackboard

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
modified: 2026-09-29
sources:
  - resource: https://www.anthropic.com/engineering/building-effective-agents
    title: "Building effective agents"
    author: "Schluntz, E.; Zhang, B."
    year: 2024
    verified: 2026-09-29
    grade: primary
  - resource: https://adk.dev/workflows/patterns/
    title: "Workflow patterns"
    author: "Google"
    year: 2026
    verified: 2026-09-29
    grade: secondary
  - resource: https://developers.googleblog.com/en/agent-development-kit-easy-to-build-multi-agent-applications/
    title: "Agent Development Kit: Making it easy to build multi-agent applications"
    author: "Huizenga, E.; Yang, B."
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns
    title: "AI agent orchestration patterns"
    author: "Kittel, C.; Siemens, C."
    year: 2026
    verified: 2026-09-29
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

Doing independent work in sequence wastes time. Some judgments are more reliable when repeated and compared.

## Structure

Anthropic names two variants (Schluntz and Zhang, 2024):

1. **Sectioning:** split a task into independent subtasks that run in parallel.
2. **Voting:** run the same task several times to get different outputs.

Google's Agent Development Kit has a `ParallelAgent`: sub-agents run together, write to separate state keys, and a later agent gathers them. Microsoft calls it concurrent orchestration, also known as fan-out/fan-in, and suggests voting, weighted merging or a model-written summary to combine results.

## Consequences & Trade-offs

Time is set by the slowest branch. Agreement between branches is a confidence signal. Cost grows with each branch, and hidden dependencies between subtasks give wrong answers.

## Related Patterns

- The Deep Research Loop
- Agents as Tools
- Blackboard

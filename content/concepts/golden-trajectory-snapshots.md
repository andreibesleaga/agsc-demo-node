---
type: concept
title: Golden Trajectories and Snapshot Tests
description: "Store a known-good agent run as a test case and replay it on each change; Google's ADK and Anthropic describe tolerant ways to compare the results."
status: stable
release: ops-evals
tags:
  - determinism
  - reliability
  - gate
aliases:
  - golden trajectory tests
  - evalset regression (ADK)
  - recorded-session eval cases
  - conformance test (ADK)
clusters:
  - evaluation-testing
date: 2026-08-16
modified: 2026-11-12
sources:
  - resource: https://adk.dev/evaluate/
    title: "Why evaluate agents"
    author: "Google"
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://www.anthropic.com/research/demystifying-evals-for-ai-agents
    title: "Demystifying evals for AI agents"
    author: "Grace, M.; Hadfield, J.; Olivares, R.; et al."
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: golden-trajectory-snapshots
related:
  - trajectory-vs-outcome-evals
  - pass-hat-k
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: golden-trajectory-snapshots.svg
  alt: A known-good run is saved as a highlighted golden case with an expected tool path and answer; each new build replays the same input, and a comparator receives both the golden case and the replay.
  caption: A known-good run is replayed on each change, and differences in tool path or answer are flagged.
x-oldsite-subdeck: Determinism & Replay
---

## Intent

Keep a known-good agent run as a test case, replay it on each change, and flag differences in tool path or answer.

## Context & Forces

Google's Agent Development Kit (ADK) defines a test turn as a user query, an expected intermediate tool-use trajectory and an expected final response. Anthropic (2026) calls checking "a sequence of tool calls in the right order" too rigid, giving "overly brittle tests", because agents regularly find valid approaches that designers did not anticipate.

## Structure

ADK scores trajectories with `tool_trajectory_avg_score` (exact match) and responses with `response_match_score` (ROUGE-1 similarity). `adk eval` and `pytest` run cases. `adk conformance record` creates a "golden baseline", and conformance tests can run on pull requests and block merges that change expected behaviour.

## Consequences & Trade-offs

Anthropic advises turning manual development checks and user-reported failures into cases, and says it is often better to grade what the agent produced than the path it took.

## Related Patterns

- Trajectory and Outcome Evaluation
- Record–Replay for Agent Tests
- Pass^k Reliability

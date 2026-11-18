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
modified: 2026-11-18
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

Keep a known-good agent run as a test case and replay it.

## Context & Forces

Google's Agent Development Kit (ADK) defines a test turn by an expected trajectory and response.

## Structure

The command `adk conformance record` creates a golden baseline that conformance tests can enforce on pull requests.

## Consequences & Trade-offs

Anthropic (2026) says it is often better to grade what the agent produced than its path.

## Related Patterns

- Trajectory and Outcome Evaluation
- Record–Replay for Agent Tests
- Pass^k Reliability

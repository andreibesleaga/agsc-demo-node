---
type: concept
title: Pass^k Reliability
description: "Score an agent by the probability that all k repeated trials of a task succeed, rather than at least one."
status: stable
release: ops-evals
tags:
  - metrics
  - adoption
aliases:
  - pass^k
  - all-k-trials success
  - reliability over repeated trials
clusters:
  - evaluation-testing
date: 2026-08-15
modified: 2026-11-12
sources:
  - resource: https://arxiv.org/abs/2406.12045
    title: "τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains"
    author: "Yao, S.; Shinn, N.; Razavi, P.; et al."
    year: 2024
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
id: pass-hat-k
related:
  - trajectory-vs-outcome-evals
  - golden-trajectory-snapshots
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: pass-hat-k.svg
  alt: One task box feeds a dashed region of eight independent runs, six marked pass and two fail; the whole set feeds both a highlighted pass-caret-k box reading all k must pass and a pass-at-k box reading any one may pass.
  caption: Nothing about the eight runs changes between the two boxes — only which of them you are allowed to ignore.
x-oldsite-subdeck: Evaluation
---

## Intent

Measure whether an agent succeeds on every one of k trials of a task, not only on at least one.

## Context & Forces

Agent behaviour varies between runs of the same task. Anthropic (2026) defines pass@k as "the likelihood that an agent gets at least one correct solution in k attempts".

## Structure

Yao et al. (2024) propose pass^k in τ-bench to evaluate the reliability of agent behaviour over multiple trials. Anthropic defines pass^k as "the probability that all k trials succeed". The τ-bench authors report that gpt-4o with function calling succeeded on about 61% of retail tasks in a single trial (pass^1) and about 25% when it had to succeed on all of eight trials (pass^8).

## Consequences & Trade-offs

Pass^k falls as k rises, so its numbers look worse than single-trial accuracy.

## Related Patterns

- Trajectory and Outcome Evaluation
- Golden Trajectories and Snapshot Tests

---
type: concept
title: Canary and Shadow Deployment for Prompts and Models
description: "Release a changed prompt or model to a small share of live traffic, or to a copy of it, and compare it with the current version before promoting."
status: stable
release: ops-evals
tags:
  - release
  - evaluation
  - metrics
aliases:
  - canary release for prompts
  - shadow testing (Statsig)
  - prompt canary label (Langfuse)
clusters:
  - operations-reliability
date: 2026-08-16
modified: 2026-11-12
sources:
  - resource: https://sre.google/workbook/canarying-releases/
    title: "Canarying Releases"
    author: "Warner, A.; Davidovič, Š.; Hidalgo, A.; et al."
    year: 2018
    verified: 2026-11-12
    grade: primary
  - resource: https://langfuse.com/resources/engineering/prompt-cicd
    title: "Prompt CI/CD: version, gate, and roll out prompts like code"
    author: "Langfuse"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://www.statsig.com/perspectives/shadow-testing-ai-model-evaluation
    title: "Shadow Testing for AI: How to Evaluate Models Without Affecting Users"
    author: "Statsig"
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: canary-and-shadow-prompts
related:
  - golden-trajectory-snapshots
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: canary-and-shadow-prompts.svg
  alt: "Live traffic splits three ways: to the current version, to a highlighted canary version that serves users, and, as a copy, to a shadow version. Current and canary outputs reach users; shadow and canary outputs go to a compare-and-log box."
  caption: A canary exposes part of live traffic to the change; shadow testing leaves users undisturbed.
x-oldsite-subdeck: Reliability & Release
---

## Intent

Compare a changed prompt or model with the current one on real traffic before promoting it.

## Context & Forces

Google's SRE Workbook defines canarying as "a partial and time-limited deployment of a change in a service and its evaluation". The canary population receives the change; the rest acts as control, and metrics should be representative and attributable.

## Structure

Langfuse's prompt CI/CD guide (current as of July 2026) applies this to prompts. Its example labels the current prompt `production` and the candidate `canary`, and application code picks the canary when a random draw falls below 0.10. Metrics compare latency, tokens, cost and score per version. Promotion, or rollback, moves the `production` label, with no redeploy. Statsig (2025) describes shadow testing: duplicating requests to the existing and candidate models for side-by-side evaluation while users continue undisturbed.

## Consequences & Trade-offs

A canary exposes part of live traffic to the change; shadow testing does not affect users.

## Related Patterns

- Shadow-Mode Rollout
- Golden Trajectories and Snapshot Tests

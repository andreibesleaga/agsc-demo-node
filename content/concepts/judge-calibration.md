---
type: concept
title: Judge Calibration
description: "Measure an automated judge against human labels before trusting its verdicts, and audit it for position, verbosity and self-enhancement bias."
status: stable
release: ops-evals
tags:
  - metrics
  - human-oversight
aliases:
  - judge agreement with humans
  - judge alignment rate
  - position, verbosity and self-enhancement bias audit
clusters:
  - evaluation-testing
date: 2026-08-16
modified: 2026-11-12
sources:
  - resource: https://arxiv.org/abs/2306.05685
    title: "Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena"
    author: "Zheng, L.; Chiang, W.; Sheng, Y.; et al."
    year: 2023
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2410.10934
    title: "Agent-as-a-Judge: Evaluate Agents with Agents"
    author: "Zhuge, M.; Zhao, C.; Ashley, D.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: judge-calibration
related:
  - error-analysis-coding
  - trajectory-vs-outcome-evals
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: judge-calibration.svg
  alt: Agent outputs flow into both a human labels box and a model judge box; both feed a highlighted agreement box that reports the match rate and known biases; a dashed loop returns the agreement result to the judge.
  caption: Check a judge against human raters on a labelled sample before its verdicts gate anything.
x-oldsite-subdeck: Evaluation
---

## Intent

Check that an automated judge agrees with human raters on a labelled sample, and audit its known biases, before its verdicts gate anything.

## Context & Forces

A model judge scales where human raters cannot. Zheng et al. (2023) name its biases: position, verbosity and self-enhancement, plus limited reasoning ability.

## Structure

Zheng et al. compare judge verdicts with human votes. On MT-bench, GPT-4's agreement with humans, excluding ties, reached 85%, above the 81% among humans. For position bias they suggest judging twice with the answer order swapped and declaring a win only when it holds in both orders. Zhuge et al. (2024) report that on their DevAI tasks Agent-as-a-Judge agrees with the consensus of human judges 90% of the time, against 70% for an LLM-as-a-Judge.

## Consequences & Trade-offs

Calibration needs human labels. Agreement measured on one benchmark or task family may not carry over to another.

## Related Patterns

- Trajectory and Outcome Evaluation
- Error Analysis by Open and Axial Coding

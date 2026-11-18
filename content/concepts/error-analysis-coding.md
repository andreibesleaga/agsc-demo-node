---
type: concept
title: Error Analysis by Open and Axial Coding
description: "Read traces, write open notes, then group them into a failure taxonomy, so the categories come from the data."
status: stable
release: ops-evals
tags:
  - taxonomy
  - observability
  - reliability
aliases:
  - open coding
  - axial coding
  - failure taxonomy
  - trace review to saturation
clusters:
  - evaluation-testing
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://hamel.dev/blog/posts/evals-faq/
    title: "AI Evals: Everything You Need to Know"
    author: "Husain, H.; Shankar, S."
    year: 2026
    verified: 2026-11-18
    grade: primary
  - resource: https://hamel.dev/blog/posts/field-guide/
    title: "A Field Guide to Rapidly Improving AI Products"
    author: "Husain, H."
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2404.12272
    title: "Who Validates the Validators? Aligning LLM-Assisted Evaluation of LLM Outputs with Human Preferences"
    author: "Shankar, S.; Zamfirescu-Pereira, J. D.; Hartmann, B.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: error-analysis-coding
related:
  - judge-calibration
  - trajectory-vs-outcome-evals
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: error-analysis-coding.svg
  alt: A stack of trace boxes flows into an open-coding box of open notes, then into a highlighted axial-coding box that groups notes into a failure taxonomy; the taxonomy feeds a failure-mode counts box, and a dashed arrow returns to traces marked repeat until no new failure modes appear.
  caption: Failure categories emerge from reading traces, repeated until new reviews reveal no new failure modes.
x-oldsite-subdeck: Evaluation
---

## Intent

Find failures by reading traces and letting categories emerge from notes, not from a metric.

## Context & Forces

Shankar et al. (2024) observe that grading outputs helps users define their criteria.

## Structure

Husain describes open coding of traces, axial coding into a failure taxonomy, and iterating until new reviews reveal no new failure modes.

## Consequences & Trade-offs

Reading traces takes human time.

## Related Patterns

- Judge Calibration
- Trajectory and Outcome Evaluation

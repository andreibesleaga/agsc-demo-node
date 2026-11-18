---
type: concept
title: Retrieval Evaluation
description: Measure whether retrieval found the right material separately from whether the answer used it faithfully.
status: stable
release: launch
tags:
  - metrics
  - grounding
aliases:
  - RAG evaluation
  - retrieval metrics
  - grounding measurement
  - RAG triad
clusters:
  - data-retrieval
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://arxiv.org/abs/2309.15217
    title: "Ragas: Automated Evaluation of Retrieval Augmented Generation"
    author: Es, S.; James, J.; Espinosa-Anke, L.; et al.
    year: 2023
    verified: 2026-11-12
    grade: primary
  - resource: https://www.trulens.org/getting_started/core_concepts/rag_triad/
    title: RAG Triad
    author: TruLens
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2411.00640
    title: "Adding Error Bars to Evals: A Statistical Approach to Language Model Evaluations"
    author: Miller, E.
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: retrieval-evaluation
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: retrieval-evaluation.svg
  alt: A query flows through retrieve, generate and answer; a highlighted box under retrieve measures whether the right passages were found and ranked high, and a second box under generate measures whether the answer is supported by them and uses them.
  caption: Both meters sit beside the chain rather than in it — they locate the failing stage, and still cannot promise a good answer.
---

## Intent

Measure whether retrieval found the right material separately from whether the answer used it well.

## Context & Forces

One end-to-end score cannot tell retrieval failures from answer failures.

## Structure

Ragas (Es et al., 2023) checks whether retrieved passages are relevant, whether the model uses them faithfully, and answer quality, without human reference answers.

## Consequences & Trade-offs

Debugging goes to the failing stage, but labelled sets age.

## Related Patterns

- Trajectory and Outcome Evaluation
- The Deep Research Loop

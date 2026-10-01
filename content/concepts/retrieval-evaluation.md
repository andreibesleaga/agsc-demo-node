---
type: concept
title: Retrieval Evaluation
description: "Measure whether retrieval found the right material separately from whether the answer used it faithfully."
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
modified: 2026-09-29
sources:
  - resource: https://arxiv.org/abs/2309.15217
    title: "Ragas: Automated Evaluation of Retrieval Augmented Generation"
    author: "Es, S.; James, J.; Espinosa-Anke, L.; et al."
    year: 2023
    verified: 2026-09-29
    grade: primary
  - resource: https://www.trulens.org/getting_started/core_concepts/rag_triad/
    title: "RAG Triad"
    author: "TruLens"
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://arxiv.org/abs/2411.00640
    title: "Adding Error Bars to Evals: A Statistical Approach to Language Model Evaluations"
    author: "Miller, E."
    year: 2024
    verified: 2026-09-29
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

When a retrieval-based system answers badly, the retrieved text often never held the answer. One end-to-end score cannot tell the two failures apart.

## Structure

Ragas (Es et al., 2023) checks, without human reference answers, whether retrieved passages are relevant, whether the model uses them faithfully, and answer quality. TruLens calls these the RAG triad: context relevance, groundedness and answer relevance.

1. **Retrieval:** recall, precision and rank on labelled real queries.
2. **Grounding:** is the answer supported by the retrieved text?
3. **Error bars:** report uncertainty, as Miller (2024) shows for model evaluations.

## Consequences & Trade-offs

Debugging goes to the failing stage. Labelled sets age, and good scores mean little if test queries differ from real ones.

## Related Patterns

- Trajectory and Outcome Evaluation
- The Deep Research Loop

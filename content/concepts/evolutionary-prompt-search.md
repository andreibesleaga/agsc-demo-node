---
type: concept
title: Evolutionary Prompt Search
description: "Improve prompts by keeping a population, letting an LLM mutate and recombine it, scoring on a training set and keeping the fittest."
status: stable
release: cognitive
tags:
  - self-improvement
  - evaluation
aliases:
  - prompt evolution
  - Promptbreeder-style mutation
  - population-based prompt optimization
  - genetic-Pareto prompt search
clusters:
  - cognitive-behavioral
date: 2026-08-18
modified: 2026-11-12
sources:
  - resource: https://arxiv.org/abs/2309.08532
    title: "EvoPrompt: Connecting LLMs with Evolutionary Algorithms Yields Powerful Prompt Optimizers"
    author: "Guo, Q.; Wang, R.; Guo, J.; et al."
    year: 2023
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2309.16797
    title: "Promptbreeder: Self-Referential Self-Improvement Via Prompt Evolution"
    author: "Fernando, C.; Banarse, D.; Michalewski, H.; et al."
    year: 2023
    verified: 2026-11-12
    grade: secondary
  - resource: https://dspy.ai/current/api/optimizers/GEPA/overview/
    title: "GEPA: Reflective Prompt Evolution"
    author: "DSPy"
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: evolutionary-prompt-search
related:
  - canary-and-shadow-prompts
  - agent-graph-optimization
  - shadow-mode-rollout
kind: pattern
evidence: explicit
maturity: emerging
mapping: explicit
diagram:
  file: evolutionary-prompt-search.svg
  alt: A population box of prompts feeds a highlighted mutation-and-crossover box, whose offspring go to a fitness scorer on a training set; a selection box returns survivors to the population, closing the loop; a dashed mutation-prompts box feeds the operator.
  caption: The operator is the model itself; what makes it evolutionary is the population, the score and the selection that closes the loop.
x-oldsite-subdeck: Evolutionary & genetic patterns
---

## Intent

Improve prompts by search: keep a population, let a model vary it, and keep the best.

## Context & Forces

EvoPrompt (Guo et al., ICLR 2024) borrows evolutionary algorithms to optimize discrete prompts.

## Structure

EvoPrompt starts from a population of prompts and uses LLMs to generate candidates through evolutionary operators. Its authors report gains of up to 25% on BBH over existing methods.

Promptbreeder (Fernando et al., 2023) is self-referential. An LLM mutates a population of task-prompts and scores them on a training set, guided by mutation-prompts that it also improves. The authors report it beats Chain-of-Thought and Plan-and-Solve prompting on arithmetic and commonsense benchmarks.

DSPy's GEPA (Genetic-Pareto) has LLMs reflect on execution traces and propose improved instructions. It keeps candidates that top at least one evaluation instance and mutates from that set.

## Consequences & Trade-offs

These gains are the authors' own figures.

## Related Patterns

- Canary and Shadow Deployment for Prompts and Models
- Agent-Graph Optimization

---
type: concept
title: Graph of Thoughts
description: "Model LLM reasoning as a graph of thoughts and dependencies, so thoughts can be combined and refined, not only branched."
status: stable
release: topologies-foundational
tags:
  - ensemble
  - reasoning
  - prompting
aliases:
  - GoT (Besta et al.)
  - thoughts as vertices, dependencies as edges
  - graph-of-operations prompting
  - aggregating thoughts
clusters:
  - foundational
date: 2026-08-18
modified: 2026-11-12
sources:
  - resource: https://arxiv.org/abs/2308.09687
    title: "Graph of Thoughts: Solving Elaborate Problems with Large Language Models"
    author: "Besta, M.; Blach, N.; Kubicek, A.; et al."
    year: 2023
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/html/2308.09687v4
    title: "Graph of Thoughts: Solving Elaborate Problems with Large Language Models (full text, v4)"
    author: "Besta, M.; Blach, N.; Kubicek, A.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2305.10601
    title: "Tree of Thoughts: Deliberate Problem Solving with Large Language Models"
    author: "Yao, S.; Yu, D.; Zhao, J.; et al."
    year: 2023
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: graph-of-thoughts
related:
  - state-graph-agents
  - agent-graph-optimization
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: graph-of-thoughts.svg
  alt: Several thought boxes fan out from a problem, two of them merge into a highlighted aggregated-thought box, a refinement arrow loops back on it, and a controller box leads to the final answer.
  caption: A graph lets thoughts be combined and refined with feedback loops, not only branched.
x-oldsite-subdeck: Graph-Structured Control Flow
---

## Intent

Let reasoning combine and refine partial thoughts, not only branch them.

## Context & Forces

Tree of Thoughts (Yao et al., 2023) explores branching reasoning paths; in the Game of 24 it solved 74% of tasks, where GPT-4 with chain-of-thought solved 4%.

## Structure

Besta et al. (AAAI 2024) model LLM output as an arbitrary graph: thoughts are vertices, dependencies are edges. This allows combining thoughts and enhancing them with feedback loops.

A Graph of Operations is a static plan that decomposes the task; a Controller coordinates reasoning. Transformations are generation, aggregation and refining.

Evaluated tasks include sorting, set intersection, keyword counting and document merging. On sorting the authors report 62% higher quality than Tree of Thoughts at over 31% lower cost.

## Consequences & Trade-offs

The headline gains rest on sorting.

## Related Patterns

- Agent as State Graph
- Agent-Graph Optimization

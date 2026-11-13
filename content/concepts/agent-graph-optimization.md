---
type: concept
title: Agent-Graph Optimization
description: "Treat an agent workflow as a graph of nodes, edges and prompts, and search that space with an evaluator, as GPTSwarm, AFlow and MASS do."
status: stable
release: topologies-foundational
tags:
  - self-improvement
  - multi-agent
  - evaluation
aliases:
  - automated workflow search
  - language agents as optimizable graphs (GPTSwarm)
  - AFlow (MCTS over workflows)
  - Multi-Agent System Search (MASS)
clusters:
  - foundational
date: 2026-08-18
modified: 2026-11-12
sources:
  - resource: https://arxiv.org/abs/2402.16823
    title: "Language Agents as Optimizable Graphs"
    author: "Zhuge, M.; Wang, W.; Kirsch, L.; et al."
    year: 2024
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2410.10762
    title: "AFlow: Automating Agentic Workflow Generation"
    author: "Zhang, J.; Xiang, J.; Yu, Z.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2502.02533
    title: "Multi-Agent Design: Optimizing Agents with Better Prompts and Topologies"
    author: "Zhou, H.; Wan, X.; Sun, R.; et al."
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: agent-graph-optimization
related:
  - state-graph-agents
  - graph-of-thoughts
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: agent-graph-optimization.svg
  alt: A workflow-space box (nodes, prompts, edges) feeds a highlighted optimizer box that proposes a graph; an evaluator box scores it and a dashed arrow feeds the result back to the optimizer; the optimizer also points to a best-graph box.
  caption: "The workflow is the search space: prompts and edges can both be searched once an evaluator exists."
x-oldsite-subdeck: Graph-Structured Control Flow
---

## Intent

Represent an agent workflow as a graph, then search over it with an evaluator.

## Context & Forces

AFlow (Zhang et al., 2024) notes that building agentic workflows takes manual effort, which limits scalability. MASS (Zhou et al., 2025) reports that agent prompts and topology both strongly affect performance.

## Structure

GPTSwarm (Zhuge et al., ICML 2024) describes agents as computational graphs: nodes process data or query LLMs, and edges carry information. It proposes node optimization of prompts and edge optimization of connectivity.

AFlow searches code-represented workflows with Monte Carlo Tree Search and execution feedback. Its authors report about 5.7% average improvement over baselines on six benchmarks, and smaller models beating GPT-4o on specific tasks at 4.55% of its cost.

MASS optimizes in three stages: block-level prompts, workflow topology, then workflow-level prompts.

## Consequences & Trade-offs

The gains above are the authors' own figures, measured on their chosen benchmarks.

## Related Patterns

- Agent as State Graph
- Graph of Thoughts

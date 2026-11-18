---
type: concept
title: Agent as State Graph
description: Express an agent as nodes, edges and shared state run in super-steps with checkpoints, as in LangGraph and Google's Pregel model.
status: stable
release: topologies-foundational
tags:
  - persistence
  - loop
  - reliability
aliases:
  - StateGraph (LangGraph)
  - agent-as-state-graph
  - Pregel-style agent runtime
  - nodes-edges-state agent
clusters:
  - foundational
date: 2026-08-18
modified: 2026-11-18
sources:
  - resource: https://docs.langchain.com/oss/python/langgraph/graph-api
    title: Graph API overview
    author: LangChain
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://docs.langchain.com/oss/python/langgraph/persistence
    title: Persistence
    author: LangChain
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://kowshik.github.io/JPregel/pregel_paper.pdf
    title: "Pregel: a system for large-scale graph processing"
    author: Malewicz, G.; Austern, M. H.; Bik, A. J. C.; et al.
    year: 2010
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: state-graph-agents
related:
  - graph-of-thoughts
  - agent-graph-optimization
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: state-graph-agents.svg
  alt: A start box feeds a highlighted shared-state box; two node boxes read and update the state; a conditional edge box routes from the first node to the second node or to an end box; a dashed arrow from the state goes to a checkpointer box.
  caption: Nodes do the work, edges pick the next step, and a checkpointer persists the state.
x-oldsite-subdeck: Graph-Structured Control Flow
---

## Intent

Make control flow explicit: nodes that work, edges that pick the next step, shared state.

## Context & Forces

LangGraph has three parts: state, nodes and edges.

## Structure

LangGraph runs graphs with message passing in the style of Google's Pregel system, in discrete super-steps. Checkpointers persist a thread's graph state.

## Consequences & Trade-offs

LangGraph's Graph API page advises it when you want explicit shared state and a visual control flow.

## Related Patterns

- Graph of Thoughts
- Agent-Graph Optimization

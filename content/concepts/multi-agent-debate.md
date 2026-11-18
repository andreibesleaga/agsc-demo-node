---
type: concept
title: Multi-Agent Debate
description: "Several model instances propose answers, read one another's responses and revise over rounds; a judge or convergence ends the debate."
status: stable
release: topologies-foundational
tags:
  - ensemble
  - reasoning
  - coordination
aliases:
  - multiagent debate (Du et al.)
  - debate with judge (Liang et al.)
  - tit-for-tat debate
  - debate-based cooperation (Liu et al.)
clusters:
  - topologies
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://arxiv.org/abs/2305.14325
    title: "Improving Factuality and Reasoning in Language Models through Multiagent Debate"
    author: "Du, Y.; Li, S.; Torralba, A.; et al."
    year: 2023
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2305.19118
    title: "Encouraging Divergent Thinking in Large Language Models through Multi-Agent Debate"
    author: "Liang, T.; He, Z.; Jiao, W.; et al."
    year: 2023
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2405.10467
    title: "Agent Design Pattern Catalogue: A Collection of Architectural Patterns for Foundation Model based Agents"
    author: "Liu, Y.; Lo, S. K.; Lu, Q.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: multi-agent-debate
related:
  - parallelization
  - blackboard
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: multi-agent-debate.svg
  alt: Two debater agents exchange arguments across rounds through a highlighted debate round box; a judge or stop-rule box below manages the debate and leads to the final answer.
  caption: "In each round, every agent is instructed to build a new response from the others'."
x-oldsite-subdeck: Conversation Topologies
---

## Intent

Improve answers by having several model instances debate over rounds.

## Context & Forces

Du et al. (2023) have several language model instances debate and report fewer hallucinations.

## Structure

Liang et al. (2023) add affirmative and negative debaters and a judge to counter "Degeneration-of-Thought".

## Consequences & Trade-offs

Du et al. say the procedure is more computationally expensive, and that converged answers were not necessarily correct.

## Related Patterns

- Parallelization
- Blackboard

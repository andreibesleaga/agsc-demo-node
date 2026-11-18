---
type: concept
title: The Augmented LLM
description: "A language model enhanced with retrieval, tools and memory that it uses actively, described by Anthropic as the basic building block of agentic systems."
status: stable
release: topologies-foundational
tags:
  - tool-use
  - memory
  - retrieval
aliases:
  - LLM plus retrieval, tools and memory
  - basic building block (Anthropic)
  - language agent (CoALA)
clusters:
  - foundational
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://www.anthropic.com/research/building-effective-agents
    title: "Building effective agents"
    author: "Schluntz, E.; Zhang, B."
    year: 2024
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2309.02427
    title: "Cognitive Architectures for Language Agents"
    author: "Sumers, T. R.; Yao, S.; Narasimhan, K.; et al."
    year: 2023
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: augmented-llm
related:
  - retrieval-evaluation
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: augmented-llm.svg
  alt: A highlighted LLM box at the centre is wired to three augmentations, retrieval, tools and memory, and produces an output; input flows to the LLM, and the LLM connects both ways to each of retrieval, tools and memory.
  caption: The model chooses what to retrieve, which tool to call and what to remember — the augmentations only make those choices possible.
x-oldsite-subdeck: The Loop Itself
---

## Intent

Treat a language model with retrieval, tools and memory as the basic unit of agentic systems.

## Context & Forces

A bare model answers from its weights.

## Structure

Sumers et al. (2023) describe a language agent in the CoALA framework with modular memory, a structured action space and decision-making.

## Consequences & Trade-offs

Anthropic advises finding the simplest solution possible before adding complexity.

## Related Patterns

- Agents as Tools
- Retrieval Evaluation

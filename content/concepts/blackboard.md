---
type: concept
title: Blackboard
description: "Independent specialists work on one problem through a shared workspace; a control step picks who contributes next."
status: stable
release: launch
tags:
  - coordination
  - persistence
  - scheduling
aliases:
  - shared workspace
  - opportunistic problem solving
clusters:
  - topologies
date: 2026-08-06
modified: 2026-09-29
sources:
  - resource: https://mas.cs.umass.edu/Documents/Erman_Hearsay80.pdf
    title: "The Hearsay-II Speech-Understanding System: Integrating Knowledge to Resolve Uncertainty"
    author: "Erman, L. D.; Hayes-Roth, F.; Lesser, V. R.; et al."
    year: 1980
    verified: 2026-09-29
    grade: primary
  - resource: https://arxiv.org/abs/2507.01701
    title: "Exploring Advanced LLM Multi-Agent Systems Based on Blackboard Architecture"
    author: "Han, B.; Zhang, S."
    year: 2025
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: blackboard
kind: pattern
evidence: single-source
maturity: emerging
diagram:
  file: blackboard.svg
  alt: Four specialist boxes are each joined to a highlighted central blackboard by a two-way arrow and never to each other; a control box above reads the board and picks which specialist runs next.
  caption: "Every arrow ends at the blackboard, so the small control box above it decides everything: which specialist runs next, and when to stop."
---

## Intent

Independent specialists work on one problem through a shared workspace, without calling each other.

## Context & Forces

Some problems cannot be split in advance: who can help depends on what is already known. Direct messages tie every agent to all the others.

## Structure

The Hearsay-II speech system (Erman et al., 1980) has three parts:

1. **Blackboard:** a global database of hypotheses.
2. **Knowledge sources:** independent programs that communicate only through the blackboard.
3. **Control:** a focus-of-control step that picks the most promising action next.

Han and Zhang (2025) apply it to language-model agents: the agents that act are chosen from what is on the blackboard.

## Consequences & Trade-offs

Specialists can be added or removed freely, and the history sits in one place. The control step becomes the hard part. Evidence for language-model agents is still thin.

## Related Patterns

- Parallelization
- Agents as Tools

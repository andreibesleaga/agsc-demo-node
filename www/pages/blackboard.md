---
type: concept
title: Blackboard
description: Independent specialists work on one problem through a shared workspace; a control step picks who contributes next.
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
modified: 2026-11-18
sources:
  - resource: https://mas.cs.umass.edu/Documents/Erman_Hearsay80.pdf
    title: "The Hearsay-II Speech-Understanding System: Integrating Knowledge to Resolve Uncertainty"
    author: Erman, L. D.; Hayes-Roth, F.; Lesser, V. R.; et al.
    year: 1980
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2507.01701
    title: Exploring Advanced LLM Multi-Agent Systems Based on Blackboard Architecture
    author: Han, B.; Zhang, S.
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: blackboard
related:
  - agents-as-tools
  - parallelization
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

Direct messages tie every agent to all the others.

## Structure

The Hearsay-II speech system (Erman et al., 1980) has a blackboard, independent knowledge sources and a control step.

## Consequences & Trade-offs

Knowledge sources interact through the blackboard alone, so their type and number can change.

## Related Patterns

- Parallelization
- Agents as Tools

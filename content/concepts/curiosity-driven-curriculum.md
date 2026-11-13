---
type: concept
title: Curiosity-Driven Curriculum
description: "Choose an agent's next task from novelty or learning progress instead of a fixed task list, as in Voyager's automatic curriculum."
status: stable
release: cognitive
tags:
  - self-improvement
  - planning
  - autonomy
aliases:
  - intrinsic-motivation task proposal
  - automatic curriculum from novelty
  - curiosity reward for agents
  - in-context novelty search
clusters:
  - cognitive-behavioral
date: 2026-08-18
modified: 2026-11-12
sources:
  - resource: https://www.frontiersin.org/journals/neurorobotics/articles/10.3389/neuro.12.006.2007/full
    title: "What is intrinsic motivation? A typology of computational approaches"
    author: "Oudeyer, P.-Y.; Kaplan, F."
    year: 2007
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/1705.05363
    title: "Curiosity-driven Exploration by Self-supervised Prediction"
    author: "Pathak, D.; Agrawal, P.; Efros, A. A.; et al."
    year: 2017
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2305.16291
    title: "Voyager: An Open-Ended Embodied Agent with Large Language Models"
    author: "Wang, G.; Xie, Y.; Jiang, Y.; et al."
    year: 2023
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2402.19464
    title: "Curiosity-driven Red-teaming for Large Language Models"
    author: "Hong, Z.; Shenfeld, I.; Wang, T.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: curiosity-driven-curriculum
related:
  - skill-library
  - goal-setting-and-monitoring
kind: pattern
evidence: explicit
maturity: emerging
mapping: explicit
diagram:
  file: curiosity-driven-curriculum.svg
  alt: A highlighted curriculum proposer box reads an exploration-progress record and emits the next task to an agent, whose outcome flows back into the record; a dashed novelty-or-progress signal box feeds the proposer.
  caption: The proposer picks the next task from novelty and progress, with no fixed task list.
x-oldsite-subdeck: Motivation & goal systems
---

## Intent

Let the agent pick its next task from what is novel or still being learned, without a fixed task list.

## Context & Forces

Pathak et al. (2017) note that extrinsic rewards are often extremely sparse or absent, and define curiosity as the error in predicting the consequence of the agent's own actions.

## Structure

Oudeyer and Kaplan (2007) define intrinsic motivation as doing an activity for its inherent satisfaction, and sort computational approaches into knowledge-based (novelty, prediction error, learning progress), competence-based and morphological.

Voyager (Wang et al., 2023) uses an automatic curriculum that maximizes exploration. Its prompt asks for diverse discoveries and a next task that is not too hard for current resources. The authors call it an in-context form of novelty search.

Hong et al. (2024) apply novelty-optimizing curiosity to red teaming and report greater test-case coverage.

## Consequences & Trade-offs

The sources report exploration and coverage gains, not cost or drift.

## Related Patterns

- Skill-Library Compounding
- Goal Setting and Monitoring

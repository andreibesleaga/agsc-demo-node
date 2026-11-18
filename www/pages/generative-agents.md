---
type: concept
title: Generative Agents
description: A simulated character with a full memory record, reflection over it, and plans drawn from both, so it stays consistent over days.
status: stable
release: reference-architectures
tags:
  - blueprint
  - memory
  - planning
aliases:
  - Smallville agents
  - interactive simulacra of human behavior
  - believable proxies of human behavior
clusters:
  - reference-architectures
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://arxiv.org/abs/2304.03442
    title: "Generative Agents: Interactive Simulacra of Human Behavior"
    author: Park, J. S.; O'Brien, J. C.; Cai, C. J.; et al.
    year: 2023
    verified: 2026-11-12
    grade: primary
  - resource: https://hai.stanford.edu/news/computational-agents-exhibit-believable-humanlike-behavior
    title: Computational Agents Exhibit Believable Humanlike Behavior
    author: Miller, K.
    year: 2023
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: generative-agents
related:
  - metacognitive-monitoring
  - skill-library
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: generative-agents.svg
  alt: Observations of the world flow into a highlighted memory stream; reflection and planning each read from it and write back into it, and a retrieval step scores memories to drive the next action, which acts on the world again.
  caption: Keep everything, read only what scores highest now — reflection turns the stream into beliefs, planning turns it into a day.
---

## Intent

Give a simulated character memory, reflection and plans, so it behaves consistently over days.

## Context & Forces

The whole history does not fit in a prompt.

## Structure

Park et al. (2023) describe a memory stream, reflection that turns memories into higher-level thoughts, and planning from retrieved memories.

## Consequences & Trade-offs

Removing observation, planning or reflection each made behaviour less believable.

## Related Patterns

- Skill-Library Compounding
- Metacognitive Monitoring and Control

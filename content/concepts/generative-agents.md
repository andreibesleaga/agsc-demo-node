---
type: concept
title: Generative Agents
description: "A simulated character with a full memory record, reflection over it, and plans drawn from both, so it stays consistent over days."
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
modified: 2026-09-29
sources:
  - resource: https://arxiv.org/abs/2304.03442
    title: "Generative Agents: Interactive Simulacra of Human Behavior"
    author: "Park, J. S.; O'Brien, J. C.; Cai, C. J.; et al."
    year: 2023
    verified: 2026-09-29
    grade: primary
  - resource: https://hai.stanford.edu/news/computational-agents-exhibit-believable-humanlike-behavior
    title: "Computational Agents Exhibit Believable Humanlike Behavior"
    author: "Miller, K."
    year: 2023
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: generative-agents
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

A chat model has no past. The whole history does not fit in a prompt, so the agent must keep everything but use only what matters now.

## Structure

Park et al. (2023) describe three parts:

1. **Memory stream:** a complete record of experiences in natural language.
2. **Reflection:** memories are turned into higher-level thoughts.
3. **Planning:** relevant memories are retrieved to plan behaviour.

Stanford HAI sums up the loop: perceptions feed memory, retrieval supports reflection and planning, then the agent acts (Miller, 2023). The study ran 25 agents in a small simulated town.

## Consequences & Trade-offs

One suggested Valentine's Day party led agents to invite each other and arrive together. Removing observation, planning or reflection each made behaviour less believable. Agents still made odd choices, and every step calls the model.

## Related Patterns

- Skill-Library Compounding
- Metacognitive Monitoring and Control

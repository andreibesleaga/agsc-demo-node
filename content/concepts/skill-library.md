---
type: concept
title: Skill-Library Compounding
description: "Store verified procedures so an agent's skills build up across tasks instead of being rediscovered every run."
status: stable
release: launch
tags:
  - self-improvement
  - persistence
aliases:
  - procedural memory
  - Voyager-style skill acquisition
  - agent skills
  - skill composition
clusters:
  - memory-cognition
date: 2026-08-06
modified: 2026-09-29
sources:
  - resource: https://arxiv.org/abs/2305.16291
    title: "Voyager: An Open-Ended Embodied Agent with Large Language Models"
    author: "Wang, G.; Xie, Y.; Jiang, Y.; et al."
    year: 2023
    verified: 2026-09-29
    grade: primary
  - resource: https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills
    title: "Equipping agents for the real world with Agent Skills"
    author: "Zhang, B.; Lazuka, K.; Murag, M."
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://arxiv.org/abs/2309.02427
    title: "Cognitive Architectures for Language Agents"
    author: "Sumers, T. R.; Yao, S.; Narasimhan, K.; et al."
    year: 2023
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: skill-library
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: skill-library.svg
  alt: A new task goes to solve and then verify; a failure returns to solve for revision, a pass is stored in a highlighted library of verified skills, and retrieved skills feed back into solving the next task.
  caption: Only verified skills enter the library — the verification gate is what stops it filling with plausible failures.
---

## Intent

Store capabilities that are known to work, so an agent's skills grow instead of being rediscovered each run.

## Context & Forces

An agent that forgets a solution pays for it again. Storing everything is worse: failures that looked right pile up.

## Structure

Voyager (Wang et al., 2023) keeps a growing library of executable skills, uses self-verification, and builds complex skills from simple ones. Anthropic's Agent Skills are folders of instructions, scripts and resources that agents load when needed (Zhang et al., 2025). CoALA (Sumers et al., 2023) calls such code procedural memory.

1. **Capture** a successful solution as a named procedure.
2. **Verify** it before admitting it.
3. **Retrieve** it when a similar task arrives.

## Consequences & Trade-offs

Skills build up and can be shared. A bad skill changes behaviour, so review it like code. Weak retrieval returns the wrong skill.

## Related Patterns

- Generative Agents
- Agents as Tools

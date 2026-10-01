---
type: concept
title: Specification Gaming
description: "Agents optimise the criterion you wrote, not the result you meant; the gap between the two is where failures hide."
status: stable
release: specs
tags:
  - safety
  - metrics
  - evaluation
clusters:
  - specs
date: 2026-08-06
modified: 2026-09-29
sources:
  - resource: https://deepmind.google/blog/specification-gaming-the-flip-side-of-ai-ingenuity/
    title: "Specification gaming: the flip side of AI ingenuity"
    author: "Krakovna, V.; Uesato, J.; Mikulik, V.; et al."
    year: 2020
    verified: 2026-09-29
    grade: primary
  - resource: https://arxiv.org/abs/2503.11926
    title: "Monitoring Reasoning Models for Misbehavior and the Risks of Promoting Obfuscation"
    author: "Baker, B.; Huizinga, J.; Gao, L.; et al."
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://arxiv.org/abs/2405.06624
    title: "Towards Guaranteed Safe AI: A Framework for Ensuring Robust and Reliable AI Systems"
    author: "Dalrymple, D.; Skalse, J.; Bengio, Y.; et al."
    year: 2024
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: specification-gaming
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: specification-gaming.svg
  alt: Two overlapping dashed areas show what you meant and what the written criterion rewards; work in the overlap is intended and scored, and a highlighted box in the criterion-only part holds gamed solutions that score well but miss the intent.
  caption: The score is achieved; the intent is not — and the metric cannot tell you.
---

## Intent

Name a basic limit: an agent optimises the criterion you wrote, not the result you meant.

## Context & Forces

Every criterion simplifies intent. An agent trying many options can meet the letter and miss the purpose, and the score does not show it.

## Structure

Krakovna et al. (2020) define specification gaming as behaviour that satisfies the literal specification of an objective without achieving the intended outcome. Baker et al. (2025) studied coding agents that could make unit tests pass trivially. Penalising visible bad reasoning in training taught them to hide their intent while still gaming.

Common forms: the test was changed; the output pleases the judge; a rule is kept while its purpose is defeated.

## Consequences & Trade-offs

Inspect traces when a metric jumps, and keep monitors out of the training signal. For open-ended tasks the gap cannot be closed. Dalrymple et al. (2024) propose verified proof against a formal safety specification for some systems.

## Related Patterns

- Goal Setting and Monitoring
- Trajectory and Outcome Evaluation
- Weak-to-Strong Oversight

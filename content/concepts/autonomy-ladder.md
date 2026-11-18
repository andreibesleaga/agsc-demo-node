---
type: concept
title: The Autonomy Ladder
description: "A six-level scale for how much an agent may decide alone, chosen per kind of action from risk, not from model capability."
status: stable
release: launch
tags:
  - taxonomy
  - adoption
  - human-oversight
clusters:
  - product
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://cloudsecurityalliance.org/blog/2026/01/28/levels-of-autonomy
    title: "Leveling Up Autonomy in Agentic AI"
    author: "Reavis, J."
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2502.02649
    title: "Fully Autonomous AI Agents Should Not be Developed"
    author: "Mitchell, M.; Ghosh, A.; Luccioni, A. S.; et al."
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: autonomy-ladder
related:
  - plan-approval-gate
kind: taxonomy
evidence: explicit
maturity: emerging
diagram:
  file: autonomy-ladder.svg
  alt: Six stacked rungs from L0, where a human performs every action, through per-action approval, plan approval, a highlighted L3 where the agent acts alone within bounds, monitored operation with a kill switch, and L5 full autonomy.
  caption: One system can sit on several rungs at once — a different one per kind of decision, and the way down stays built.
---

## Intent

A shared scale for how much an agent may decide alone.

## The Categories

Reavis (2026), on the Cloud Security Alliance blog, proposes six levels echoing SAE J3016: No Autonomy, Assisted, Supervised, Conditional, High Autonomy and Full Autonomy.

## How to Apply It

Pick a level per kind of action, based on what a mistake would cost.

## Related Patterns

- Meaningful Human Control
- Plan Approval Gate

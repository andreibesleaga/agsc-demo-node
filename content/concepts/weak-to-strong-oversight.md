---
type: concept
title: Weak-to-Strong Oversight
description: "Open question: can weaker judges, human or model, reliably oversee agents stronger than themselves? What is known and what is not."
status: stable
release: future
tags:
  - safety
  - evaluation
  - calibration
aliases:
  - weak-to-strong generalization
  - scalable oversight
  - sandwiching experiments
  - can weaker judges oversee stronger agents
clusters:
  - future
date: 2026-08-18
modified: 2026-09-29
sources:
  - resource: https://arxiv.org/abs/2312.09390
    title: "Weak-to-Strong Generalization: Eliciting Strong Capabilities With Weak Supervision"
    author: "Burns, C.; Izmailov, P.; Kirchner, J. H.; et al."
    year: 2023
    verified: 2026-09-29
    grade: primary
  - resource: https://arxiv.org/abs/2211.03540
    title: "Measuring Progress on Scalable Oversight for Large Language Models"
    author: "Bowman, S. R.; Hyun, J.; Perez, E.; et al."
    year: 2022
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: weak-to-strong-oversight
related:
  - specification-gaming
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: weak-to-strong-oversight.svg
  alt: A weak supervisor's labels, with errors, train a highlighted strong student; on a performance scale the student lands above the weak supervisor but below the strong ceiling trained on true labels, so part of the gap is recovered and the rest is still missing.
  caption: Strong students beat their weak teachers — but recover only part of the gap; the rest is the open problem.
---

## Intent

State an open question: can a weaker supervisor reliably oversee a stronger agent?

## Context & Forces

Agent systems already rely on weaker overseers: cheap models grading strong ones, busy people approving plans they cannot fully check.

## Structure

Bowman et al. (2022) call this scalable oversight. In their tests, people chatting with an unreliable model assistant did substantially better than the model alone or they alone. Burns et al. (2023) found that strong models trained on a weak model's labels consistently beat their weak supervisors, but naive training stays far from the strong model's full ability.

1. **Known:** weak supervision can draw out more than the supervisor can do.
2. **Known:** people plus a model can beat either alone.
3. **Open:** whether this holds for safety judgments, and whether the strong model learns intent or mistakes.

## Consequences & Trade-offs

Treat a weak judge as a partial signal. Pair it with confidence signals, smaller checkable tasks, and gates that do not assume the judge is right.

## Related Patterns

- Meaningful Human Control
- Specification Gaming
- Plan Approval Gate

---
type: concept
title: Goal Setting and Monitoring
description: "Give an agent a goal with checkable criteria, then monitor its progress and decide to continue, re-plan or stop."
status: stable
release: advanced
tags:
  - loop
  - planning
  - observability
aliases:
  - MAPE-K for agents
  - autonomic control loop
  - goal-progress monitoring
  - expected_output + guardrail (CrewAI)
clusters:
  - reasoning-decision
date: 2026-08-18
modified: 2026-09-29
sources:
  - resource: https://arxiv.org/html/2407.14402v1
    title: "The Vision of Autonomic Computing: Can LLMs Make It a Reality?"
    author: "Zhang, Z.; Yang, F.; Qin, X.; et al."
    year: 2024
    verified: 2026-09-29
    grade: primary
  - resource: https://docs.crewai.com/en/concepts/tasks
    title: "Tasks"
    author: "CrewAI"
    year: 2026
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: goal-setting-and-monitoring
related:
  - metacognitive-monitoring
  - specification-gaming
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: goal-setting-and-monitoring.svg
  alt: A goal with success criteria enters a highlighted monitor, the first step of a monitor, analyze, plan and execute loop around shared knowledge; execute acts on the managed task, its progress returns to the monitor, and analyze can exit to done or escalate.
  caption: A goal without criteria cannot be monitored; monitoring without a loop back cannot correct.
---

## Intent

Give an agent a goal with checkable criteria, then watch progress and correct course.

## Context & Forces

An agent can do every step right and still miss the goal. Vague goals cannot be checked; single metrics can be gamed.

## Structure

The classic form is the MAPE-K loop: Monitor, Analyze, Plan, Execute, over shared Knowledge. Zhang et al. (2024) trace it to Kephart and Chess (2003) and apply it with language-model agents to microservice management. In CrewAI, a task has an `expected_output` describing completion and a `guardrail` that checks the output, retried three times by default.

1. Write the goal as a few observable criteria.
2. Check progress after each step, ideally outside the acting model.
3. Continue, re-plan, or stop and escalate.

## Consequences & Trade-offs

Progress becomes visible. Each check costs extra. Criteria can replace the goal, so keep them few.

## Related Patterns

- Specification Gaming
- Metacognitive Monitoring and Control
- Unbounded Loops

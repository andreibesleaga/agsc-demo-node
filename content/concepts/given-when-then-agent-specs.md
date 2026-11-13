---
type: concept
title: Given/When/Then Agent Specs
description: "Write agent requirements as Given/When/Then scenarios and run each as a repeatable evaluation."
status: stable
release: cognitive
tags:
  - evaluation
  - coding-agents
  - determinism
aliases:
  - BDD scenarios for agents
  - specification by example for evals
  - Gherkin-style eval scenarios
  - acceptance criteria as agent tests
clusters:
  - cognitive-behavioral
date: 2026-08-18
modified: 2026-11-12
sources:
  - resource: https://dannorth.net/blog/introducing-bdd/
    title: "Introducing BDD"
    author: "North, D."
    year: 2006
    verified: 2026-11-12
    grade: primary
  - resource: https://cucumber.io/docs/gherkin/reference/
    title: "Gherkin Reference"
    author: "Cucumber"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2411.13768
    title: "Evaluation-Driven Development and Operations of LLM Agents: A Process Model and Reference Architecture"
    author: "Xia, B.; Lu, Q.; Zhu, L.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
  - resource: https://www.promptfoo.dev/docs/configuration/scenarios/
    title: "Scenarios"
    author: "promptfoo"
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: given-when-then-agent-specs
related:
  - trajectory-vs-outcome-evals
  - golden-trajectory-snapshots
kind: pattern
evidence: explicit
maturity: emerging
mapping: explicit
diagram:
  file: given-when-then-agent-specs.svg
  alt: A highlighted scenario box with three rows, Given context, When event and Then outcome, feeds a runner box that runs the scenario against an agent, and a results box receives the runner's output.
  caption: The scenario is both the requirement and the test.
x-oldsite-subdeck: Behavior-driven specification
---

## Intent

State what an agent must do as Given/When/Then scenarios and run them as evaluations, so the requirement and the test are one artefact.

## Context & Forces

Xia et al. (2024) note that LLM agents pursue loosely defined goals and adapt after deployment, while Test-Driven and Behaviour-Driven Development assume stable specifications.

## Structure

North (2006) introduced behaviour-driven development: "A story's behaviour is simply its acceptance criteria", written as scenarios of the form "Given some initial context (the givens), When an event occurs, Then ensure some outcomes." Cucumber's Gherkin reference says Given steps describe the initial context of the system, When steps an event or action, and Then steps an expected outcome. Xia et al. build their evaluation process on the iterative principles of TDD and BDD. promptfoo's scenarios group a set of data with the tests to run on it.

## Consequences & Trade-offs

A requirement becomes executable and reviewable.

## Related Patterns

- Trajectory and Outcome Evaluation
- Golden Trajectories and Snapshot Tests

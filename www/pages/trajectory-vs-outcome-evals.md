---
type: concept
title: Trajectory and Outcome Evaluation
description: Grade the end state an agent produced and the path it took as two separate questions, each with a suitable grader.
status: stable
release: launch
tags:
  - metrics
  - observability
aliases:
  - trajectory evals
  - transcript grading
  - final-state grading
  - tool-trajectory match
clusters:
  - evaluation-testing
date: 2026-08-15
modified: 2026-11-18
sources:
  - resource: https://www.anthropic.com/research/demystifying-evals-for-ai-agents
    title: Demystifying evals for AI agents
    author: Grace, M.; Hadfield, J.; Olivares, R.; et al.
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://adk.dev/evaluate/
    title: Why evaluate agents
    author: Google
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://huyenchip.com/2025/01/07/agents.html
    title: Agents
    author: Huyen, C.
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: trajectory-vs-outcome-evals
related:
  - pass-hat-k
  - retrieval-evaluation
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: trajectory-vs-outcome-evals.svg
  alt: Three agent steps inside a dashed trajectory area lead to a final-state box; a highlighted trajectory grader below checks the steps for tools, order and efficiency, and a separate outcome grader checks the final state.
  caption: "Two graders, two questions: did it end in the right place, and did it get there the right way."
---

## Intent

Grade the end state an agent produced and the path it took as two separate questions.

## Context & Forces

An agent can reach the right result by a bad path.

## Structure

Anthropic's guide defines the transcript, or trajectory, as the complete record of a trial, and the outcome as the final state of the environment (Grace et al., 2026).

## Consequences & Trade-offs

Anthropic warns that exact tool-call sequences make brittle tests.

## Related Patterns

- Retrieval Evaluation
- Specification Gaming
- Pass^k Reliability

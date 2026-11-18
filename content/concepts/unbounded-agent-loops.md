---
type: concept
title: Unbounded Loops
description: "An agent loop with no step limit, no budget and no independent exit test runs until money, patience or the platform stops it."
status: stable
release: antipatterns
tags:
  - cost-control
  - safety
  - autonomy
aliases:
  - unbounded agent loop
  - no stopping condition
  - runaway agent loop
  - infinite loop
clusters:
  - antipatterns
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://www.anthropic.com/research/building-effective-agents
    title: "Building effective agents"
    author: "Schluntz, E.; Zhang, B."
    year: 2024
    verified: 2026-11-12
    grade: primary
  - resource: https://genai.owasp.org/llmrisk/llm102025-unbounded-consumption/
    title: "LLM10:2025 Unbounded Consumption"
    author: "OWASP Gen AI Security Project"
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://inkog.io/glossary/infinite-loop-ai-agent
    title: "AI Agent Infinite Loop Detection & Prevention"
    author: "Inkog"
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: unbounded-agent-loops
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: unbounded-agent-loops.svg
  alt: A think, act, observe cycle loops back on itself with no step cap, no budget and no done test; beside it, a highlighted exit gate that checks those three leads to stop or escalate, joined to the loop by a dashed arrow marked missing.
  caption: The loop is the pattern; the missing gate is the anti-pattern.
domain_type: FailureMode
---

## Intent

Name the mistake: an agent loop with no step limit, budget or goal check.

## Context & Forces

Anthropic notes that autonomy brings higher costs and compounding errors (Schluntz and Zhang, 2024).

## Structure

Signs include no step limit, no time limit, and an exit that depends on the model's output.

## Consequences & Trade-offs

An unbounded loop can run up a large bill.

## Related Patterns

- Goal Setting and Monitoring
- Exception Handling and Recovery

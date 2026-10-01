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
modified: 2026-09-29
sources:
  - resource: https://www.anthropic.com/engineering/building-effective-agents
    title: "Building effective agents"
    author: "Schluntz, E.; Zhang, B."
    year: 2024
    verified: 2026-09-29
    grade: primary
  - resource: https://genai.owasp.org/llmrisk/llm102025-unbounded-consumption/
    title: "LLM10:2025 Unbounded Consumption"
    author: "OWASP Gen AI Security Project"
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://inkog.io/glossary/infinite-loop-ai-agent
    title: "AI Agent Infinite Loop Detection & Prevention"
    author: "Inkog"
    year: 2026
    verified: 2026-09-29
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
---

## Intent

Name the mistake: an agent loop with no step limit, no budget and no independent test that the goal is met.

## Context & Forces

In an agent loop the model picks the next step, so it can repeat a tool call or claim progress that did not happen. Anthropic notes that autonomy brings higher costs and compounding errors (Schluntz and Zhang, 2024).

## Structure

Signs of it:

1. **No step limit.** Anthropic lists a maximum number of iterations as a normal stopping condition.
2. **No cost limit or timeout.** OWASP's LLM10:2025 Unbounded Consumption warns of denial of service and economic loss, and recommends rate limits, quotas and timeouts.
3. **The model decides the exit.** Inkog traces endless agent loops to missing iteration limits and exit conditions that never fire.
4. **"Done" is announced, not observed.**

## Consequences & Trade-offs

Bills surprise, sessions hang, and other systems get flooded. Set limits from measured run lengths; a cap that is too tight cuts off hard tasks.

## Related Patterns

- Goal Setting and Monitoring
- Exception Handling and Recovery

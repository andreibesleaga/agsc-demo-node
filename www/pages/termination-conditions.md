---
type: concept
title: Termination and Exit Conditions
description: Define in advance each way an agent loop ends, such as a final answer, a turn limit, or a pause for human input.
status: stable
release: topologies-foundational
tags:
  - loop
  - cost-control
  - reliability
aliases:
  - stopping conditions (Anthropic)
  - max_turns (OpenAI Agents SDK)
  - turn limits
  - exit conditions
clusters:
  - foundational
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://www.anthropic.com/research/building-effective-agents
    title: Building effective agents
    author: Anthropic
    year: 2024
    verified: 2026-11-12
    grade: primary
  - resource: https://openai.github.io/openai-agents-python/running_agents/
    title: Running agents
    author: OpenAI
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: termination-conditions
related:
  - unbounded-agent-loops
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: termination-conditions.svg
  alt: A loop iteration box feeds a highlighted exit check box listing done, turn cap and blocker; the check points to done, to a turn-limit error, and to a human, with a dashed return arrow back into the loop.
  caption: "Every way the loop can end is decided in advance: final output, turn limit, or a pause for a human."
x-oldsite-owasp-ids:
  - LLM10
x-oldsite-subdeck: The Loop Itself
---

## Intent

Decide in advance every way an agent loop can end.

## Context & Forces

Anthropic notes it is common to include stopping conditions.

## Structure

The OpenAI Agents SDK ends its runner loop on final output, or raises MaxTurnsExceeded when the run exceeds max_turns.

## Consequences & Trade-offs

A turn limit stops a run that never finishes, at the price of unfinished work.

## Related Patterns

- Unbounded Loops
- Exception Handling and Recovery

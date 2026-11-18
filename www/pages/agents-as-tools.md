---
type: concept
title: Agents as Tools
description: Wrap a specialist agent as a tool, so a calling agent can hand it one bounded task and keep control.
status: stable
release: launch
tags:
  - delegation
  - isolation
  - multi-agent
aliases:
  - tool-agents (OpenAI Agents SDK)
  - subagent (Claude Code)
  - context-isolated subagent
clusters:
  - foundational
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://openai.github.io/openai-agents-python/tools/#agents-as-tools
    title: Tools
    author: OpenAI
    year: 2025
    verified: 2026-11-12
    grade: primary
  - resource: https://openai.github.io/openai-agents-python/multi_agent/
    title: Agent orchestration
    author: OpenAI
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://code.claude.com/docs/en/sub-agents
    title: Create custom subagents
    author: Anthropic
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: agents-as-tools
related:
  - deep-research-loop
  - parallelization
  - augmented-llm
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: agents-as-tools.svg
  alt: A calling agent calls three tools; the highlighted one is an agent wrapped as a tool, which works in its own context window with its own prompt and tools, and only its final result returns to the caller, which keeps control.
  caption: Only the return box crosses that boundary — everything the specialist read, tried and discarded is already gone.
---

## Intent

Wrap a specialist agent as a tool, so the caller keeps control.

## Context & Forces

Handing over the whole conversation gives away control.

## Structure

The caller owns the loop; the specialist runs in its own context and returns a short result.

## Consequences & Trade-offs

One agent stays accountable and its context stays small, but each call costs time and tokens.

## Related Patterns

- The Deep Research Loop
- Parallelization

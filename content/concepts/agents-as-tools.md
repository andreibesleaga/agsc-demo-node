---
type: concept
title: Agents as Tools
description: "Wrap a specialist agent as a tool, so a calling agent can hand it one bounded task and keep control."
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
modified: 2026-09-29
sources:
  - resource: https://openai.github.io/openai-agents-python/tools/#agents-as-tools
    title: "Tools"
    author: "OpenAI"
    year: 2025
    verified: 2026-09-29
    grade: primary
  - resource: https://openai.github.io/openai-agents-python/multi_agent/
    title: "Agent orchestration"
    author: "OpenAI"
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://code.claude.com/docs/en/sub-agents
    title: "Create custom subagents"
    author: "Anthropic"
    year: 2026
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: agents-as-tools
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: agents-as-tools.svg
  alt: A calling agent calls three tools; the highlighted one is an agent wrapped as a tool, which works in its own context window with its own prompt and tools, and only its final result returns to the caller, which keeps control.
  caption: Only the return box crosses that boundary — everything the specialist read, tried and discarded is already gone.
---

## Intent

Wrap a specialist agent as a tool. The calling agent hands it one bounded task and keeps control.

## Context & Forces

Some subtasks, such as a search or a review, are bounded but noisy. Handing over the whole conversation gives away control.

## Structure

1. The caller owns the loop and the conversation.
2. The specialist is offered as a tool with a name, a description and an input.
3. It runs in its own context, with its own prompt, tools and permissions.
4. It returns a short result.

The OpenAI Agents SDK calls this "agents as tools": a manager agent keeps control and calls specialists. Claude Code subagents also run in their own context window and return a summary.

## Consequences & Trade-offs

One agent stays accountable and its context stays small. Each call costs time and tokens, and a short summary can drop a needed detail.

## Related Patterns

Used by The Deep Research Loop; Parallelization runs several calls at once.

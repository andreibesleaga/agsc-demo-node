---
type: concept
title: Prompt-Caching Layout
description: Put the stable prompt prefix first and variable content last so provider prompt caches can reuse it on later requests.
status: stable
release: ops-evals
tags:
  - cost-control
  - attention
aliases:
  - prefix caching
  - cache breakpoints (Anthropic)
  - static-prefix prompt layout
clusters:
  - operations-reliability
date: 2026-08-19
modified: 2026-11-18
sources:
  - resource: https://platform.claude.com/docs/en/build-with-claude/prompt-caching
    title: Prompt caching
    author: Anthropic
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-use-with-prompt-caching
    title: Tool use with prompt caching
    author: Anthropic
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://developers.openai.com/api/docs/guides/prompt-caching
    title: Prompt caching
    author: OpenAI
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://aistudio.google.com/docs/caching
    title: Context caching
    author: Google
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: prompt-caching-layout
related:
  - thinking-budget-control
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: prompt-caching-layout.svg
  alt: A stable prefix box holding tool definitions, system rules and documents sits above a highlighted cache-breakpoint line, with the volatile tail of the current turn below it; both feed the model.
  caption: Stable content goes above the breakpoint and content that changes goes below it.
x-oldsite-subdeck: Cost & Performance (FinOps)
---

## Intent

Order the prompt so unchanging content comes early and later requests reuse the cached prefix.

## Context & Forces

OpenAI says cache reuse requires the entire rendered prefix to match.

## Structure

Anthropic caches tools, then system, then messages, and a change at one level invalidates it and every later one.

## Consequences & Trade-offs

Anthropic prices cache reads at 0.1 times base input price (lower on some models).

## Related Patterns

- Thinking-Budget Control

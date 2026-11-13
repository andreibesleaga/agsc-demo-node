---
type: concept
title: Prompt-Caching Layout
description: "Put the stable prompt prefix first and variable content last so provider prompt caches can reuse it on later requests."
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
modified: 2026-11-12
sources:
  - resource: https://platform.claude.com/docs/en/build-with-claude/prompt-caching
    title: "Prompt caching"
    author: "Anthropic"
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://platform.claude.com/docs/en/agents-and-tools/tool-use/tool-use-with-prompt-caching
    title: "Tool use with prompt caching"
    author: "Anthropic"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://developers.openai.com/api/docs/guides/prompt-caching
    title: "Prompt caching"
    author: "OpenAI"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://aistudio.google.com/docs/caching
    title: "Context caching"
    author: "Google"
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

Order the prompt so unchanging content comes first and later requests can reuse the provider's cached prefix.

## Context & Forces

OpenAI says cache reuse requires the entire rendered prefix to match, and advises putting stable instructions and shared reference material first, timestamps and user-specific details last. Google enables implicit caching by default for Gemini 2.5 and newer models and advises putting large repeated content first.

## Structure

Anthropic caches in the order tools, system, then messages, up to a block marked with `cache_control`. A change at one level invalidates that level and every later one; modifying tool definitions invalidates everything. Anthropic advises putting the breakpoint on the last block that stays identical across requests, not on content such as timestamps.

## Consequences & Trade-offs

Anthropic prices cache reads at 0.1 times base input price (lower on some models) and 5-minute cache writes at 1.25 times. Prompts below a model-specific minimum length are not cached.

## Related Patterns

- Thinking-Budget Control

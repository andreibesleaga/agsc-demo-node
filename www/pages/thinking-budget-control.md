---
type: concept
title: Thinking-Budget Control
description: Set how much reasoning a model spends per task class before the call, using effort levels and thinking settings that providers document.
status: stable
release: launch
tags:
  - cost-control
  - reasoning
aliases:
  - reasoning effort
  - thinking budget
clusters:
  - operations-reliability
date: 2026-08-19
modified: 2026-11-18
sources:
  - resource: https://platform.claude.com/docs/en/build-with-claude/effort
    title: Effort
    author: Anthropic
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://platform.claude.com/docs/en/build-with-claude/extended-thinking
    title: Extended thinking
    author: Anthropic
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://developers.openai.com/api/docs/guides/reasoning
    title: Reasoning models
    author: OpenAI
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://aistudio.google.com/docs/thinking
    title: Gemini thinking
    author: Google
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2412.21187
    title: Do NOT Think That Much for 2+3=? On the Overthinking of o1-Like LLMs
    author: Chen, X.; Xu, J.; Liang, T.; et al.
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: thinking-budget-control
related:
  - prompt-caching-layout
  - termination-conditions
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: thinking-budget-control.svg
  alt: Incoming tasks pass through a highlighted budget allocator that sends simple tasks down a low-effort path with a short reasoning bar and hard tasks down a high-effort path with a long one, both reaching the answer.
  caption: Reasoning effort is chosen per task class before the call.
x-oldsite-subdeck: Cost & Performance (FinOps)
---

## Intent

Choose, per task class and before the call, how much reasoning a model spends.

## Context & Forces

Chen et al. (2024) study "overthinking" in o1-like models, which spend excessive computation on simple problems.

## Structure

OpenAI's reasoning.effort trades reasoning for speed and token usage, while Anthropic's effort is "a behavioral signal, not a strict token budget".

## Consequences & Trade-offs

Anthropic advises testing effort on your own use case.

## Related Patterns

- Prompt-Caching Layout
- Termination and Exit Conditions

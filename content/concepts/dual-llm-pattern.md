---
type: concept
title: Dual-LLM Pattern
description: "Keep the model that can act away from untrusted text: a tool-less model reads it, and plain code passes results between them."
status: stable
release: launch
tags:
  - prompt-injection
  - isolation
  - least-privilege
aliases:
  - privileged/quarantined LLM split
  - CaMeL
  - capability-based prompt-injection defense
clusters:
  - security
date: 2026-08-16
modified: 2026-09-29
sources:
  - resource: https://simonwillison.net/2023/Apr/25/dual-llm-pattern/
    title: "The Dual LLM pattern for building AI assistants that can resist prompt injection"
    author: "Willison, S."
    year: 2023
    verified: 2026-09-29
    grade: primary
  - resource: https://arxiv.org/abs/2503.18813
    title: "Defeating Prompt Injections by Design"
    author: "Debenedetti, E.; Shumailov, I.; Fan, T.; et al."
    year: 2025
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: dual-llm-pattern
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: dual-llm-pattern.svg
  alt: The user talks to a controller made of plain code, which sits between a highlighted privileged LLM that plans and receives only variable names, the tools that return untrusted content, and a quarantined LLM without tools that reads that content.
  caption: "Authority and comprehension are split: the model that acts never reads what the attacker wrote."
---

## Intent

Keep the model that can act away from untrusted text, so injected instructions cannot trigger actions.

## Context & Forces

E-mails, web pages and files can contain text that looks like a command. Filters lower the risk but do not remove it.

## Structure

Simon Willison (2023) uses three parts:

1. **Privileged model:** takes trusted input, mainly from the user, and can use tools.
2. **Quarantined model:** reads untrusted content and has no tools.
3. **Controller:** ordinary code that passes results between them as variables.

CaMeL (Debenedetti et al., 2025) builds on this. It takes the control flow from the trusted query only, and checks capabilities attached to data whenever a tool is called.

## Consequences & Trade-offs

Injected text cannot change the plan. Some usefulness is lost: CaMeL solved 77% of AgentDojo tasks with provable security, against 84% undefended. Use it when an agent reads untrusted data and holds important tools.

## Related Patterns

OWASP Top 10 for Agentic Applications (goal hijack).

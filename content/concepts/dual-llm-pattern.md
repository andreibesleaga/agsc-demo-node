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
modified: 2026-11-18
sources:
  - resource: https://simonwillison.net/2023/Apr/25/dual-llm-pattern/
    title: "The Dual LLM pattern for building AI assistants that can resist prompt injection"
    author: "Willison, S."
    year: 2023
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2503.18813
    title: "Defeating Prompt Injections by Design"
    author: "Debenedetti, E.; Shumailov, I.; Fan, T.; et al."
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: dual-llm-pattern
related:
  - owasp-agentic-top-10
  - memory-context-poisoning
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: dual-llm-pattern.svg
  alt: The user talks to a controller made of plain code, which sits between a highlighted privileged LLM that plans and receives only variable names, the tools that return untrusted content, and a quarantined LLM without tools that reads that content.
  caption: "Authority and comprehension are split: the model that acts never reads what the attacker wrote."
---

## Intent

Keep the acting model away from untrusted text, to limit what injected instructions can trigger.

## Context & Forces

E-mails and web pages can contain text that looks like a command.

## Structure

Simon Willison (2023) separates a privileged model with tools, a quarantined model reading untrusted content, and a controller.

## Consequences & Trade-offs

CaMeL (Debenedetti et al., 2025) solved 77% of AgentDojo tasks with provable security, against 84% undefended.

## Related Patterns

- OWASP Top 10 for Agentic Applications
- Memory and Context Poisoning Defense

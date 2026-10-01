---
type: concept
title: OWASP Top 10 for Agentic Applications
description: "OWASP's list of ten security risks for agents that act, a shared vocabulary for threat models and security reviews."
status: stable
release: launch
tags:
  - taxonomy
  - standards
  - governance
aliases:
  - ASI01–ASI10
  - OWASP agentic security risks
clusters:
  - security
date: 2026-08-15
modified: 2026-09-29
sources:
  - resource: https://genai.owasp.org/2025/12/09/owasp-top-10-for-agentic-applications-the-benchmark-for-agentic-security-in-the-age-of-autonomous-ai/
    title: "OWASP Top 10 for Agentic Applications – The Benchmark for Agentic Security in the Age of Autonomous AI"
    author: "Sotiropoulos, J."
    year: 2025
    verified: 2026-09-29
    grade: primary
  - resource: https://genai.owasp.org/llm-top-10/
    title: "OWASP Top 10 for LLM Applications 2025"
    author: "OWASP Gen AI Security Project"
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/
    title: "OWASP Top 10 for Agentic Applications for 2026"
    author: "OWASP Gen AI Security Project"
    year: 2025
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: owasp-agentic-top-10
kind: taxonomy
evidence: explicit
maturity: established
diagram:
  file: owasp-agentic-top-10.svg
  alt: Ten boxes in two columns of five list ASI01 to ASI10 by their full names, with the first entry, Agent Goal Hijack, highlighted and no arrows between them.
  caption: No arrows means no order and no priority — the only way to use this picture is to account for all ten.
---

## Intent

One shared list of the security risks of software that acts on its own.

## The Categories

OWASP published this list on 9 December 2025, developed with more than 100 experts:

- **ASI01** Agent Goal Hijack
- **ASI02** Tool Misuse
- **ASI03** Identity & Privilege Abuse
- **ASI04** Agentic Supply Chain Vulnerabilities
- **ASI05** Unexpected Code Execution
- **ASI06** Memory & Context Poisoning
- **ASI07** Insecure Inter-Agent Communication
- **ASI08** Cascading Failures
- **ASI09** Human-Agent Trust Exploitation
- **ASI10** Rogue Agents

It sits beside the OWASP Top 10 for LLM Applications 2025, which covers risks such as prompt injection and unbounded consumption.

## How to Apply It

Check every agent capability against the ten entries. Record a control or a decision to accept each risk, citing the ASI identifier.

## Related Patterns

- Dual-LLM Pattern
- Unbounded Loops
- Tamper-Evident Agent Audit Log

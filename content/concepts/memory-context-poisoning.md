---
type: concept
title: Memory and Context Poisoning Defense
description: "Treat writes to agent memory and retrieval stores as untrusted: validate, attribute, segment and expire entries, following OWASP ASI06."
status: stable
release: security
tags:
  - prompt-injection
  - retrieval
  - accountability
aliases:
  - memory poisoning defense
  - trusted memory writes
  - memory provenance and expiry
clusters:
  - security
date: 2026-08-16
modified: 2026-11-12
sources:
  - resource: https://genai.owasp.org/download/52117/?tmstv=1765059207
    title: "OWASP Top 10 for Agentic Applications for 2026"
    author: "OWASP Gen AI Security Project"
    year: 2025
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2407.12784
    title: "AgentPoison: Red-teaming LLM Agents via Poisoning Memory or Knowledge Bases"
    author: "Chen, Z.; Xiang, Z.; Xiao, C.; et al."
    year: 2024
    verified: 2026-11-12
    grade: secondary
  - resource: https://embracethered.com/blog/posts/2024/chatgpt-macos-app-persistent-data-exfiltration/
    title: "Spyware Injection Into Your ChatGPT's Long-Term Memory (SpAIware)"
    author: "Rehberger, J."
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: memory-context-poisoning
related:
  - skill-library
  - owasp-agentic-top-10
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: memory-context-poisoning.svg
  alt: Untrusted sources and the agent's own outputs flow to a highlighted write gate that scans entries and requires source attribution before they reach a segmented memory store, which feeds retrieval; a note says unverified entries expire.
  caption: Every write to agent memory is treated as untrusted and checked before it is committed.
x-oldsite-owasp-ids:
  - ASI06
x-oldsite-subdeck: Injection & Manipulation
---

## Intent

Treat every write to agent memory or a retrieval store as untrusted.

## Context & Forces

OWASP's ASI06, Memory & Context Poisoning, describes adversaries who corrupt or seed stored context so that future reasoning, planning or tool use becomes biased or unsafe. Rehberger (2024) showed prompt injection planting persistent spyware in ChatGPT's macOS app memory; OpenAI fixed the exfiltration vector, not the injection. AgentPoison (Chen et al., 2024) reports above 80% attack success on each of three agents at a poison rate under 0.1%.

## Structure

OWASP's mitigations:

- scan new writes before commit;
- segment memory by session and domain;
- require source attribution;
- block re-ingestion of the agent's own outputs;
- expire unverified memory;
- keep snapshots for rollback.

## Consequences & Trade-offs

The sources list defenses without measuring them.

## Related Patterns

- Tamper-Evident Agent Audit Log
- Skill-Library Compounding
- OWASP Top 10 for Agentic Applications

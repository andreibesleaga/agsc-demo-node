---
type: concept
title: Tamper-Evident Agent Audit Log
description: An append-only, hash-linked record of every important agent action, so what happened can be rebuilt and checked.
status: stable
release: launch
tags:
  - compliance
  - observability
  - persistence
aliases:
  - hash-chained audit
  - session-log provenance
  - append-only action record
clusters:
  - governance
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://doi.org/10.1007/BF00196791
    title: How to time-stamp a digital document
    author: Haber, S.; Stornetta, W. S.
    year: 1991
    verified: 2026-11-12
    grade: primary
  - resource: https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/
    title: Agentic AI – Threats and Mitigations
    author: OWASP Gen AI Security Project
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://github.blog/changelog/2026-03-20-trace-any-copilot-coding-agent-commit-to-its-session-logs/
    title: Trace any Copilot coding agent commit to its session logs
    author: GitHub
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: immutable-audit-log
related:
  - meaningful-human-control
  - plan-approval-gate
  - memory-context-poisoning
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: immutable-audit-log.svg
  alt: Three audit records in a row each hold who acted, what was done, the policy verdict and the hash of the record before it; a highlighted verifier below recomputes every link, so changing one record breaks every hash after it.
  caption: Only one box in the picture is not a record — and until somebody runs it, the chain is a claim rather than a check.
---

## Intent

Keep a checkable record of every important agent action that shows any change.

## Context & Forces

OWASP lists repudiation and untraceability as threat T8 for agentic systems.

## Structure

OWASP asks that AI-generated logs be cryptographically signed and immutable.

## Consequences & Trade-offs

Incidents can be reconstructed from the log.

## Related Patterns

- Meaningful Human Control
- Plan Approval Gate

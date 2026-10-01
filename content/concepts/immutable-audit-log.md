---
type: concept
title: Tamper-Evident Agent Audit Log
description: "An append-only, hash-linked record of every important agent action, so what happened can be rebuilt and checked."
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
modified: 2026-09-29
sources:
  - resource: https://doi.org/10.1007/BF00196791
    title: "How to time-stamp a digital document"
    author: "Haber, S.; Stornetta, W. S."
    year: 1991
    verified: 2026-09-29
    grade: primary
  - resource: https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/
    title: "Agentic AI – Threats and Mitigations"
    author: "OWASP Gen AI Security Project"
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://github.blog/changelog/2026-03-20-trace-any-copilot-coding-agent-commit-to-its-session-logs/
    title: "Trace any Copilot coding agent commit to its session logs"
    author: "GitHub"
    year: 2026
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: immutable-audit-log
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: immutable-audit-log.svg
  alt: Three audit records in a row each hold who acted, what was done, the policy verdict and the hash of the record before it; a highlighted verifier below recomputes every link, so changing one record breaks every hash after it.
  caption: Only one box in the picture is not a record — and until somebody runs it, the chain is a claim rather than a check.
---

## Intent

Keep a record of every important agent action that can be checked later and shows any change.

## Context & Forces

Accountability needs a reliable account of what happened. Ordinary logs can be edited. OWASP lists repudiation and untraceability as threat T8 for agentic systems.

## Structure

1. Write records to an append-only store.
2. Link each record to the previous one by a hash, as in Haber and Stornetta's 1991 time-stamping scheme. Changing an old record breaks every later link.
3. Record who acted, what, the inputs, the approving decision and the result.
4. Verify the chain regularly.

On GitHub, each commit by the Copilot coding agent carries an `Agent-Logs-Url` trailer linking to its session logs, with the person who gave the task as co-author.

## Consequences & Trade-offs

Incidents can be rebuilt. Sensitive data in logs is a risk, so record only what is needed. An unverified chain gives false comfort.

## Related Patterns

- Meaningful Human Control
- Plan Approval Gate

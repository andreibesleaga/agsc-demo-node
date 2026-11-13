---
type: concept
title: Agent Identity and Scoped Credentials
description: "Give each agent its own identity and short-lived, task-scoped credentials so delegation narrows authority and actions are attributable."
status: stable
release: security
tags:
  - least-privilege
  - delegation
  - accountability
aliases:
  - non-human identity per agent
  - task-scoped agent credentials
  - delegation-chain scoping
clusters:
  - security
date: 2026-08-16
modified: 2026-11-12
sources:
  - resource: https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/
    title: "OWASP Top 10 for Agentic Applications for 2026"
    author: "OWASP GenAI Security Project"
    year: 2025
    verified: 2026-11-12
    grade: primary
  - resource: https://cloudsecurityalliance.org/artifacts/agentic-ai-identity-and-access-management-a-new-approach
    title: "Agentic AI Identity and Access Management: A New Approach"
    author: "Cloud Security Alliance"
    year: 2025
    verified: 2026-11-12
    grade: primary
prov:
  origin: imported
  operator: human:andreibesleaga
id: agent-identity-scoped-credentials
related:
  - immutable-audit-log
  - owasp-agentic-top-10
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: agent-identity-scoped-credentials.svg
  alt: A human principal delegates to a parent agent, which delegates to a sub-agent; both agents connect to a highlighted identity-and-credential issuer box (per-agent ID, short-lived token), which issues a task-scoped token, a token limited to the parent's scope, and a dashed link to an audit log.
  caption: Each hop down the delegation chain gets its own narrower credential, not the parent's.
x-oldsite-owasp-ids:
  - ASI03
  - LLM06
x-oldsite-subdeck: Privilege & Identity
---

## Intent

Give each agent its own identity and short-lived, task-scoped credentials, so delegation only narrows authority.

## Context & Forces

Identity systems were built for people and long-lived services; agents start per task and delegate. A reused user session gives a confused agent everything the principal holds.

## Structure

OWASP's ASI03, Identity & Privilege Abuse, describes attackers manipulating delegation chains, role inheritance and agent context. Its mitigations include "short-lived, narrowly scoped tokens per task" with per-agent identities, and no privilege inheritance across agents unless the original intent is re-validated. The Cloud Security Alliance (2025) proposes a unique identity for each ephemeral agent, credentials "with specific permissions for limited time periods and particular tasks", and "clear chains of accountability from human principals to agents".

## Consequences & Trade-offs

Each credential covers one task. Scoping needs precise task definitions, and an issuer must be available when tasks start.

## Related Patterns

- Tamper-Evident Agent Audit Log
- OWASP Top 10 for Agentic Applications

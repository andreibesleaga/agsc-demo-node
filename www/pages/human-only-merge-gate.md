---
type: concept
title: Human-Only Merge Gate
description: An agent works on its own branch and cannot approve or merge; a named human decides what reaches the main branch.
status: stable
release: launch
tags:
  - accountability
  - coding-agents
  - governance
clusters:
  - sdlc
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://docs.github.com/en/copilot/concepts/security-governance-and-network-settings/risks-and-mitigations
    title: Risks and mitigations for GitHub Copilot cloud agent
    author: GitHub
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://arxiv.org/abs/2606.20615
    title: "Specifying AI-SDLC Processes: A Protocol Language for Human-Agent Boundaries"
    author: Prifti, Y.; De Meo, P.; Provetti, A.
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: human-only-merge-gate
related:
  - immutable-audit-log
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: human-only-merge-gate.svg
  alt: An agent's pull request (branch only) flows through its session log to a highlighted human review-and-merge box before the main branch; a direct agent-to-main path is shown crossed out.
  caption: The agent cannot approve or merge its own pull request; a human does.
x-oldsite-subdeck: Gates
---

## Intent

Keep agent-authored changes out of the main branch until a human merges them.

## Context & Forces

Prifti et al. (2026) note that self-review validates against the model that produced the output.

## Structure

GitHub's Copilot cloud agent pushes to a single branch and cannot approve or merge its pull requests; a human does.

## Consequences & Trade-offs

A human decides the merge, with the session log to review.

## Related Patterns

- Plan Approval Gate
- Tamper-Evident Agent Audit Log

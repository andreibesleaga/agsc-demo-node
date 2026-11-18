---
type: concept
title: Plan Approval Gate
description: "The agent researches and proposes a plan without editing source; a person approves, changes or rejects it before edits start."
status: stable
release: sdlc
tags:
  - human-oversight
  - coding-agents
  - governance
aliases:
  - plan mode (Anthropic, GitHub, OpenAI)
  - plan before edit
  - read-only planning phase
  - propose-approve-execute
clusters:
  - sdlc
date: 2026-08-18
modified: 2026-11-18
sources:
  - resource: https://code.claude.com/docs/en/permission-modes
    title: "Choose a permission mode"
    author: "Anthropic"
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent/
    title: "Research, plan, and code with Copilot cloud agent"
    author: "GitHub"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://github.blog/changelog/2026-01-21-github-copilot-cli-plan-before-you-build-steer-as-you-go/
    title: "GitHub Copilot CLI: Plan before you build, steer as you go"
    author: "GitHub"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://learn.chatgpt.com/guides/best-practices
    title: "Best practices"
    author: "OpenAI"
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: plan-approval-gate
related:
  - human-only-merge-gate
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: plan-approval-gate.svg
  alt: Inside a dashed read-only phase the agent explores and writes a plan; a highlighted human decision either approves it, opening an edit phase where the agent writes, or sends it back to keep planning with changes.
  caption: Approve the intent once, not every edit — the gate sits between reading and writing.
---

## Intent

The agent proposes a plan without editing source; a person approves it before edits start.

## Context & Forces

An agent that edits at once commits to an unseen approach.

## Structure

In Claude Code's plan mode, the agent explores and proposes changes without editing source until a person approves.

## Consequences & Trade-offs

Reviewers judge the approach, not a large diff.

## Related Patterns

- The Autonomy Ladder
- Tamper-Evident Agent Audit Log
- Human-Only Merge Gate

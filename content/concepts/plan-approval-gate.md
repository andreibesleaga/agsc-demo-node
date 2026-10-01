---
type: concept
title: Plan Approval Gate
description: "The agent researches and proposes a plan without editing anything; a person approves, changes or rejects it before any edit."
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
modified: 2026-09-29
sources:
  - resource: https://code.claude.com/docs/en/permission-modes
    title: "Choose a permission mode"
    author: "Anthropic"
    year: 2026
    verified: 2026-09-29
    grade: primary
  - resource: https://github.blog/changelog/2026-04-01-research-plan-and-code-with-copilot-cloud-agent/
    title: "Research, plan, and code with Copilot cloud agent"
    author: "GitHub"
    year: 2026
    verified: 2026-09-29
    grade: secondary
  - resource: https://github.blog/changelog/2026-01-21-github-copilot-cli-plan-before-you-build-steer-as-you-go/
    title: "GitHub Copilot CLI: Plan before you build, steer as you go"
    author: "GitHub"
    year: 2026
    verified: 2026-09-29
    grade: secondary
  - resource: https://learn.chatgpt.com/guides/best-practices
    title: "Best practices"
    author: "OpenAI"
    year: 2026
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: plan-approval-gate
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: plan-approval-gate.svg
  alt: Inside a dashed read-only phase the agent explores and writes a plan; a highlighted human decision either approves it, opening an edit phase where the agent writes, or sends it back to keep planning with changes.
  caption: Approve the intent once, not every edit — the gate sits between reading and writing.
---

## Intent

The agent researches and proposes a plan without changing anything; a person approves it before any edit.

## Context & Forces

An agent that edits at once commits to an approach nobody has seen. Approving each edit is slow and hides the overall shape.

## Structure

1. **Read-only phase:** the agent explores but cannot write.
2. **Plan:** a plan the person can change.
3. **Decision:** approve, give feedback, or keep planning.
4. **Switch:** approval unlocks editing.

In Claude Code's plan mode, Claude researches and proposes changes without making them; in most setups edits stay blocked until approval. GitHub Copilot lets users approve a plan or give feedback before code is written. OpenAI's Codex plan mode gathers context and asks questions first.

## Consequences & Trade-offs

Reviewers judge the approach, not a large diff. Small tasks pay an extra round trip, and habitual approval weakens the gate. The runtime, not the prompt, must block writes.

## Related Patterns

- The Autonomy Ladder
- Tamper-Evident Agent Audit Log

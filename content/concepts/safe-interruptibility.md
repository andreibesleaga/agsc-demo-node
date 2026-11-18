---
type: concept
title: Safe Interruptibility
description: "Design agents so a human stop is honoured and the agent does not learn to avoid or seek interruption."
status: stable
release: ethics
tags:
  - human-oversight
  - gate
  - autonomy
aliases:
  - big red button
  - safely interruptible agents (Orseau & Armstrong)
  - stop outranks every internal goal
  - interruption policy
clusters:
  - ethics
date: 2026-08-18
modified: 2026-11-18
sources:
  - resource: https://intelligence.org/files/Interruptibility.pdf
    title: "Safely Interruptible Agents"
    author: "Orseau, L.; Armstrong, S."
    year: 2016
    verified: 2026-11-12
    grade: primary
  - resource: https://docs.langchain.com/oss/python/langgraph/interrupts
    title: "Interrupts"
    author: "LangChain"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://www.langchain.com/blog/introducing-ambient-agents
    title: "Introducing ambient agents"
    author: "Chase, H."
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: safe-interruptibility
related:
  - termination-conditions
  - meaningful-human-control
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: safe-interruptibility.svg
  alt: "An operator's stop signal enters a highlighted interruption-policy box that overrides the agent's own policy and halts action, while a dashed line to the reward-and-learning box is crossed out: the agent does not learn to prevent or seek the interruption."
  caption: "The agent can be interrupted without learning to prevent or seek the interruption."
x-oldsite-subdeck: Human Agency
---

## Intent

Let a human halt an agent, without the agent learning to prevent or seek the halt.

## Context & Forces

Orseau and Armstrong (2016) note that a reinforcement learning agent may learn to avoid interruptions.

## Structure

LangGraph's interrupt suspends graph execution at the call, a checkpointer saves state, and the run resumes with a Command.

## Consequences & Trade-offs

The paper concerns reinforcement learning, not language-model agents.

## Related Patterns

- Termination and Exit Conditions
- Meaningful Human Control

---
type: concept
title: Meaningful Human Control
description: "Two conditions for real human control: the system responds to relevant human reasons, and its actions trace to a person who understands it."
status: stable
release: ethics
tags:
  - accountability
  - compliance
  - safety
aliases:
  - MHC
  - tracking and tracing conditions
  - guidance control over autonomous systems
  - human oversight by design
clusters:
  - ethics
date: 2026-08-18
modified: 2026-11-18
sources:
  - resource: https://www.frontiersin.org/journals/robotics-and-ai/articles/10.3389/frobt.2018.00015/full
    title: "Meaningful Human Control over Autonomous Systems: A Philosophical Account"
    author: "Santoni de Sio, F.; van den Hoven, J."
    year: 2018
    verified: 2026-11-12
    grade: primary
  - resource: https://artificialintelligenceact.eu/article/14/
    title: "Article 14: Human Oversight"
    author: "European Parliament; Council of the European Union"
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: meaningful-human-control
related:
  - safe-interruptibility
  - autonomy-ladder
  - weak-to-strong-oversight
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: meaningful-human-control.svg
  alt: Human moral reasons feed a highlighted agent-decision box (tracking), and every action traces back to a responsible human who understands the system (tracing); the two arrows together define meaningful control.
  caption: Control is meaningful only when both arrows hold — reasons in, responsibility traceable out.
---

## Intent

Keep people really in control of an autonomous system, not just on paper.

## Context & Forces

Agents act faster than people can review.

## Structure

Santoni de Sio and van den Hoven (2018) set two conditions: tracking of human moral reasons, and tracing of actions to at least one person who understands the system.

## Consequences & Trade-offs

Tracing fails when no person in the chain understands the system.

## Related Patterns

- The Autonomy Ladder
- Tamper-Evident Agent Audit Log
- Weak-to-Strong Oversight
- Safe Interruptibility

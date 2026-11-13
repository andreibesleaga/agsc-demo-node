---
type: concept
title: Resolution, Containment and Deflection Metrics
description: "Separate deflection, containment and resolution, and state how 'resolved' is verified, as Intercom, Zendesk and Sierra define it."
status: stable
release: product
tags:
  - adoption
  - evaluation
aliases:
  - resolution rate
  - automated resolution (Zendesk)
  - confirmed vs assumed resolution (Intercom)
  - deflection vs containment vs resolution
clusters:
  - product
date: 2026-08-18
modified: 2026-11-12
sources:
  - resource: https://www.intercom.com/help/en/articles/8205718-fin-ai-agent-outcomes
    title: "Fin AI Agent outcomes"
    author: "Intercom"
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://fin.ai/learn/resolution-rate-vs-deflection-rate
    title: "Resolution vs. Deflection Rate: Measure AI Agent Success"
    author: "Intercom"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://support.zendesk.com/hc/en-us/articles/5352026794010-About-the-automated-resolutions-platform-prior-to-resolution-tiers
    title: "About the automated resolutions platform (prior to resolution tiers)"
    author: "Zendesk"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://sierra.ai/blog/outcome-based-pricing-for-ai-agents
    title: "Outcome-based pricing for AI agents"
    author: "Greenwald, E."
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: resolution-rate-metrics
related:
  - outcome-based-pricing
  - trajectory-vs-outcome-evals
  - specification-gaming
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: resolution-rate-metrics.svg
  alt: "Inbound conversations enter two nested regions, labelled \"deflected: no human reached\" and \"contained: never handed off\", that hold an agent box and a highlighted \"resolved?\" check, which asks whether the customer's problem was addressed under a stated definition."
  caption: "Deflection counts queries that never reach a human, containment counts conversations without handoff, and resolution asks whether the problem was addressed."
x-oldsite-subdeck: Metrics
---

## Intent

Measure a customer-facing agent by whether it addressed the customer's problem, and define "resolved" precisely enough to count.

## Context & Forces

Intercom separates three measures. Deflection rate is the percentage of inbound queries that never reach a human agent; Intercom says it "tells you nothing about customer outcomes". Containment rate is the share of AI conversations that ended without handoff. Resolution rate attempts to measure whether the agent addressed the customer's reason.

## Structure

Intercom's Fin counts a resolution as confirmed when the customer says the answer helped, or assumed when the customer leaves without asking for more. Zendesk counts an automated resolution only without escalation and after LLM verification. Sierra bills resolved conversations.

## Consequences & Trade-offs

The definition decides the number: assumed resolutions count a departure as a resolution, and LLM verification is itself an automated judgment.

## Related Patterns

- Outcome-Based Pricing
- Trajectory and Outcome Evaluation
- Specification Gaming

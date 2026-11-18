---
type: concept
title: Outcome-Based Pricing
description: "Charge for achieved outcomes such as a resolved conversation instead of seats or usage, which requires agreeing criteria for the outcome upfront."
status: stable
release: product
tags:
  - adoption
  - metrics
  - evaluation
clusters:
  - product
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://sierra.ai/blog/outcome-based-pricing-for-ai-agents
    title: "Outcome-based pricing for AI agents"
    author: "Greenwald, E."
    year: 2024
    verified: 2026-11-12
    grade: primary
  - resource: https://support.zendesk.com/hc/en-us/articles/5352026794010-About-the-automated-resolutions-platform-prior-to-resolution-tiers
    title: "About the automated resolutions platform (prior to resolution tiers)"
    author: "Zendesk"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://www.intercom.com/help/en/articles/8205718-fin-ai-agent-outcomes
    title: "Fin AI Agent outcomes"
    author: "Intercom"
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: outcome-based-pricing
related:
  - autonomy-ladder
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: outcome-based-pricing.svg
  alt: Requests flow into an agent; only the subset marked resolved crosses a highlighted billing line, while unresolved and escalated cases exit usually unbilled.
  caption: Only cases counted as resolved are billed, and vendors define resolution differently.
x-oldsite-subdeck: Business Model
---

## Intent

Price an agent by the outcome it achieves, not by seats or usage.

## Context & Forces

Sierra (10 December 2024) ties outcome-based pricing to business results.

## Structure

Vendors define resolution differently: Zendesk, before its resolution tiers, required no escalation to a human and a model's verification; Intercom bills confirmed and assumed resolutions.

## Consequences & Trade-offs

The sources do not discuss disputes over the definition.

## Related Patterns

- Resolution, Containment and Deflection Metrics
- The Autonomy Ladder

---
type: concept
title: Outcome-Based Pricing
description: "Charge for achieved outcomes such as a resolved conversation instead of seats or usage, which requires agreeing a written definition of the outcome."
status: stable
release: product
tags:
  - adoption
  - metrics
  - evaluation
clusters:
  - product
date: 2026-08-06
modified: 2026-11-12
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

Sierra (10 December 2024) ties outcome-based pricing to tangible business results: a resolved support conversation, a saved cancellation, an upsell or a cross-sell. If a conversation is unresolved, it says, there is in most cases no charge.

## Structure

Sierra says it agrees criteria for each outcome upfront, and uses blended pricing for cases such as routing.

Vendors define resolution differently. Zendesk bills an automated resolution only when the request is resolved "without any escalation to a human agent" and a large language model verifies it. Intercom bills confirmed and assumed resolutions, and deducts one if the customer returns for more help.

## Consequences & Trade-offs

Sierra says the model aligns its incentives with the customer's. The sources do not discuss disputes over the definition.

## Related Patterns

- Resolution, Containment and Deflection Metrics
- The Autonomy Ladder

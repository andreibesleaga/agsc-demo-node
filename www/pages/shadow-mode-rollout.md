---
type: concept
title: Shadow-Mode Rollout
description: Run an agent on live work with its side effects suppressed, then compare its proposed actions with what people actually did.
status: stable
release: product
tags:
  - release
  - autonomy
  - evaluation
aliases:
  - shadow deployment
  - shadow testing (SageMaker)
  - shadow variant
  - observe-only mode
clusters:
  - product
date: 2026-08-18
modified: 2026-11-18
sources:
  - resource: https://docs.aws.amazon.com/sagemaker/latest/dg/shadow-tests.html
    title: Shadow tests
    author: Amazon Web Services
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://www.microsoft.com/en-us/dynamics-365/blog/it-professional/2026/07/09/shadow-mode-case-management-agent/
    title: "Trust before you automate: introducing Shadow Mode in Case Management Agent"
    author: Somara, M.; Bian, P.; Gupta, S.
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://learn.microsoft.com/en-us/dynamics365/release-plan/2025wave2/service/dynamics365-customer-service/assess-case-management-agent-predictions-using-shadow-mode
    title: Use shadow mode for Case Management Agent predictions
    author: Microsoft
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: shadow-mode-rollout
related:
  - canary-and-shadow-prompts
  - autonomy-ladder
  - trajectory-vs-outcome-evals
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: shadow-mode-rollout.svg
  alt: Live requests fan out to the human or incumbent path, whose actions reach the world, and to a highlighted shadow agent whose proposed actions are logged and compared but never executed.
  caption: The agent proposes actions without executing them, and its proposals are compared with what people did.
x-oldsite-subdeck: Rollout
---

## Intent

Run an agent on live work with side effects suppressed, then compare it with people.

## Context & Forces

SageMaker describes shadow testing as comparing a serving change against the deployed setup before it reaches end users.

## Structure

Microsoft applies the idea to its Dynamics 365 Case Management Agent, which in shadow mode updates no record and contacts no customer.

## Consequences & Trade-offs

Every request is processed twice.

## Related Patterns

- Canary and Shadow Deployment for Prompts and Models
- The Autonomy Ladder
- Trajectory and Outcome Evaluation

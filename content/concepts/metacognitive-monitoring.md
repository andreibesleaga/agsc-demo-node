---
type: concept
title: Metacognitive Monitoring and Control
description: "A meta level watches how sure the agent is while it works and decides to continue, retry or abstain."
status: stable
release: launch
tags:
  - calibration
  - evaluation
  - reasoning
aliases:
  - metacognitive monitoring
  - meta-level control loop
  - monitor-generate-verify (MGV)
  - know-what-you-know signalling
clusters:
  - cognitive-behavioral
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://doi.org/10.1037/0003-066X.34.10.906
    title: "Metacognition and Cognitive Monitoring: A New Area of Cognitive-Developmental Inquiry"
    author: "Flavell, J. H."
    year: 1979
    verified: 2026-11-12
    grade: primary
  - resource: https://doi.org/10.1016/S0079-7421(08)60053-5
    title: "Metamemory: A Theoretical Framework and New Findings"
    author: "Nelson, T. O.; Narens, L."
    year: 1990
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2511.04341
    title: "Monitor-Generate-Verify (MGV): Formalising Metacognitive Theory for Language Model Reasoning"
    author: "Oh, N.; Gobet, F."
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2207.05221
    title: "Language Models (Mostly) Know What They Know"
    author: "Kadavath, S.; Conerly, T.; Askell, A.; et al."
    year: 2022
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: metacognitive-monitoring
related:
  - judge-calibration
  - weak-to-strong-oversight
kind: pattern
evidence: explicit
maturity: emerging
mapping: explicit
diagram:
  file: metacognitive-monitoring.svg
  alt: A task goes to an object level that generates; a dashed confidence signal rises to a highlighted meta level, which sends control back down to continue or retry, or stops with an abstention, while generated work passes a verify step before the answer.
  caption: Monitoring is a separate reading of confidence; control is what that reading changes — a model that only generates has neither.
---

## Intent

Add a level that watches the work and decides to continue, retry or abstain.

## Context & Forces

A model that never checks itself runs to the end, right or wrong.

## Structure

Nelson and Narens (1990) split an object level that does the task from a meta level that watches it.

## Consequences & Trade-offs

"I don't know" becomes a valid output, but the signal can mislead.

## Related Patterns

- Goal Setting and Monitoring
- Weak-to-Strong Oversight
- Judge Calibration

---
type: concept
title: Sustainability Signal Plane
description: "A well-known URI where a system publishes its energy and carbon figures, and reads its peers' figures as input to its decisions."
status: stable
release: launch
tags:
  - standards
  - observability
  - accountability
clusters:
  - protocols
date: 2026-08-21
modified: 2026-11-18
sources:
  - resource: https://datatracker.ietf.org/doc/draft-besleaga-sustainability-wellknown/
    title: "The 'sustainability-data' Well-Known URI"
    author: "Andrei N. Besleaga"
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://carbontxt.org
    title: "carbon.txt"
    author: "Green Web Foundation"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://github.com/Green-Software-Foundation/real-time-cloud
    title: "Real Time Energy and Carbon Standards for Cloud Providers"
    author: "Green Software Foundation"
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://doi.org/10.5281/zenodo.22056634
    title: "The Cybernetic Sustainability Loop: Governed Agentic Systems on a Sustainability Data Plane — evaluation package"
    author: "Andrei N. Besleaga"
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: sustainability-signal-plane
related:
  - goal-setting-and-monitoring
kind: pattern
evidence: single-source
maturity: emerging
signature: true
signature_elements:
  - "the composition: an IETF well-known URI carrying runtime metrics that peer systems read as a control signal"
diagram:
  file: sustainability-signal-plane.svg
  alt: Three systems each publish their data at the well-known sustainability-data path; a highlighted consuming agent reads all three, decides from them, and publishes its own document at the same path.
  caption: Publishing and reading the same format is what makes a loop possible.
---

## Intent

Give each system one predictable address for its current energy and carbon figures.

## Context & Forces

Sustainability data is mostly written for people.

## Structure

The Internet-Draft "The 'sustainability-data' Well-Known URI" (Andrei N. Besleaga, 2026) defines /.well-known/sustainability-data, one JSON document over HTTPS.

## Consequences & Trade-offs

Figures are self-declared: the format can be checked, the truth cannot.

## Related Patterns

- Goal Setting and Monitoring

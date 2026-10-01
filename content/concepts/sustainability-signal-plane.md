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
modified: 2026-09-29
sources:
  - resource: https://datatracker.ietf.org/doc/draft-besleaga-sustainability-wellknown/
    title: "The 'sustainability-data' Well-Known URI"
    author: "Andrei N. Besleaga"
    year: 2026
    verified: 2026-09-29
    grade: primary
  - resource: https://carbontxt.org
    title: "carbon.txt"
    author: "Green Web Foundation"
    year: 2026
    verified: 2026-09-29
    grade: secondary
  - resource: https://github.com/Green-Software-Foundation/real-time-cloud
    title: "Real Time Energy and Carbon Standards for Cloud Providers"
    author: "Green Software Foundation"
    year: 2025
    verified: 2026-09-29
    grade: secondary
  - resource: https://doi.org/10.5281/zenodo.22056634
    title: "The Cybernetic Sustainability Loop: Governed Agentic Systems on a Sustainability Data Plane — evaluation package"
    author: "Andrei N. Besleaga"
    year: 2026
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: sustainability-signal-plane
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

Give each system one standard address for its current energy and carbon figures, readable by the systems that depend on it.

## Context & Forces

Sustainability data is mostly written for people. carbon.txt (Green Web Foundation) gives a domain one place for its sustainability data; the Green Software Foundation's Real Time Cloud project works on a common format for cloud providers.

## Structure

The Internet-Draft "The 'sustainability-data' Well-Known URI" (Andrei N. Besleaga, 2026) defines `/.well-known/sustainability-data`: one JSON document over HTTPS, with seven mandatory members, including a link to the method behind the figures.

1. Each system publishes its own document.
2. It reads the documents of the systems it depends on.
3. It uses those figures in its own decisions.

## Consequences & Trade-offs

Figures sit at one predictable address. They are self-declared: the format can be checked, the truth cannot. The author's evaluation package measures one public gateway. With few publishers, adoption is the main risk.

## Related Patterns

- Goal Setting and Monitoring

---
type: concept
title: The Deep Research Loop
description: "Split a question into parts, search them in parallel, combine the findings and check that every claim has a source."
status: stable
release: launch
tags:
  - planning
  - concurrency
  - grounding
clusters:
  - advanced
date: 2026-08-06
modified: 2026-11-18
sources:
  - resource: https://www.anthropic.com/research/multi-agent-research-system
    title: "How we built our multi-agent research system"
    author: "Hadfield, J.; Zhang, B.; Lien, K.; et al."
    year: 2025
    verified: 2026-11-12
    grade: primary
  - resource: https://research.google/blog/accelerating-scientific-breakthroughs-with-an-ai-co-scientist/
    title: "Accelerating scientific breakthroughs with an AI co-scientist"
    author: "Gottweis, J.; Natarajan, V."
    year: 2025
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: deep-research-loop
related:
  - retrieval-evaluation
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: deep-research-loop.svg
  alt: A lead agent plans and fans out to three subagents that search and read in parallel; their findings return to the lead, which synthesizes them and either loops back for more research or hands the report to a highlighted citation pass.
  caption: The verification pass is what separates research from confident summarization.
---

## Intent

Answer an open question by splitting it, searching in parallel, and sourcing every claim.

## Context & Forces

Open questions need many searches.

## Structure

Anthropic's Research feature (Hadfield et al., 2025) has a lead agent start parallel subagents and a citation agent locate each claim's source.

## Consequences & Trade-offs

Anthropic reports that multi-agent systems use about 15 times more tokens than chats.

## Related Patterns

- Parallelization
- Agents as Tools
- Retrieval Evaluation

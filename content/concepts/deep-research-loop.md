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
modified: 2026-09-29
sources:
  - resource: https://www.anthropic.com/engineering/multi-agent-research-system
    title: "How we built our multi-agent research system"
    author: "Hadfield, J.; Zhang, B.; Lien, K.; et al."
    year: 2025
    verified: 2026-09-29
    grade: primary
  - resource: https://research.google/blog/accelerating-scientific-breakthroughs-with-an-ai-co-scientist/
    title: "Accelerating scientific breakthroughs with an AI co-scientist"
    author: "Gottweis, J.; Natarajan, V."
    year: 2025
    verified: 2026-09-29
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: deep-research-loop
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: deep-research-loop.svg
  alt: A lead agent plans and fans out to three subagents that search and read in parallel; their findings return to the lead, which synthesizes them and either loops back for more research or hands the report to a highlighted citation pass.
  caption: The verification pass is what separates research from confident summarization.
---

## Intent

Answer an open question by splitting it, searching the parts in parallel, and checking that every claim has a source.

## Context & Forces

Open questions need many searches. One agent is slow; many agents can produce a fluent report that nobody checked.

## Structure

Anthropic describes its Research feature this way (Hadfield et al., 2025):

1. A lead agent plans and starts subagents that explore parts at the same time.
2. Each subagent gets an objective, an output format, tool guidance and clear boundaries.
3. The lead combines the findings.
4. A citation agent locates the source for each claim.

Google's AI co-scientist uses a related team of agents that generate, review, rank and improve hypotheses (Gottweis and Natarajan, 2025).

## Consequences & Trade-offs

It covers more ground. It is costly: Anthropic reports about 15 times the tokens of a chat. Vague task descriptions cause duplicated work or gaps.

## Related Patterns

- Parallelization
- Agents as Tools
- Retrieval Evaluation

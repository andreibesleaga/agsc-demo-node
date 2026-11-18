---
type: gate
title: Publish gate
status: stable
date: 2026-11-18
prov:
  origin: ai-assisted
  operator: human:andreibesleaga
  model: "Claude (Anthropic)"
  agent: "Claude Code"
clusters:
  - upkeep
level: L2
checks:
  - schema
  - links
  - provenance
  - determinism
  - review
enforce:
  - status-check
---

# Publish gate

Every change passes these checks, and a person merges it, before it is published.

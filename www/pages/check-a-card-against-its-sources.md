---
type: procedure
title: Check a card against its sources
description: Compare one card with the public sources it cites and propose the result.
status: stable
clusters:
  - upkeep
date: 2026-11-18
verifies:
  - card-format
prov:
  origin: ai-assisted
  operator: human:andreibesleaga
  model: Claude (Anthropic)
  agent: Claude Code
when: A card's sources were last checked more than six months ago
---

# Check a card against its sources

## When

A card's sources were last checked more than six months ago.

## Steps

1. Open the card and read the `sources` in its header.
2. Open each source address.
3. Compare each sentence of the card with what the source says.
4. Propose the new `verified` date when they agree, or a corrected sentence when they do not.

## Checks

`agsc lint` passes on the proposal, and the proposal changes one card.

---
type: concept
title: Record–Replay for Agent Tests
description: "Record real model responses in one test run and replay them from a cassette on later runs, so tests run offline and repeat exactly."
status: stable
release: ops-evals
tags:
  - determinism
  - cost-control
aliases:
  - VCR cassettes
  - cassette tests (LangSmith)
  - HTTP record and playback
  - record modes once/none/all
clusters:
  - evaluation-testing
date: 2026-08-16
modified: 2026-11-18
sources:
  - resource: https://vcrpy.readthedocs.io/en/latest/
    title: "VCR.py documentation"
    author: "VCR.py"
    year: 2026
    verified: 2026-11-12
    grade: primary
  - resource: https://vcrpy.readthedocs.io/en/latest/usage.html
    title: "VCR.py usage"
    author: "VCR.py"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://docs.langchain.com/langsmith/pytest
    title: "How to run evaluations with pytest"
    author: "LangChain"
    year: 2026
    verified: 2026-11-12
    grade: secondary
  - resource: https://vcrpy.readthedocs.io/en/latest/advanced.html
    title: "VCR.py advanced features"
    author: "VCR.py"
    year: 2026
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: record-replay-cassettes
related:
  - golden-trajectory-snapshots
  - idempotent-agent-actions
kind: pattern
evidence: explicit
maturity: established
diagram:
  file: record-replay-cassettes.svg
  alt: A test calls the agent; a highlighted cassette layer sits between the agent and the model API, recording responses when no cassette exists and replaying them on later runs without touching the network.
  caption: Replay tests the code around the model, not the model.
x-oldsite-subdeck: Determinism & Replay
---

## Intent

Capture real model responses once and replay them, so agent tests skip the network.

## Context & Forces

Live model calls need the network and return different responses over time.

## Structure

VCR.py records HTTP interactions in a cassette file and then returns the stored responses; LangSmith's pytest integration applies the idea to model calls.

## Consequences & Trade-offs

Replay runs the code around the model, not the model.

## Related Patterns

- Golden Trajectories and Snapshot Tests
- Idempotency Keys for Agent Actions

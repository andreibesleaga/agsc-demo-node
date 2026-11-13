---
type: concept
title: Agentic Supply Chain Integrity
description: "Sign, pin and allowlist the models, tools, protocol servers and prompts an agent loads, and keep a way to revoke any of them at once."
status: stable
release: security
tags:
  - accountability
  - standards
  - governance
aliases:
  - agentic supply chain (ASI04)
  - model and tool provenance
  - signed skills and MCP servers
  - AIBOM attestation
clusters:
  - security
date: 2026-08-16
modified: 2026-11-12
sources:
  - resource: https://genai.owasp.org/download/52117/?tmstv=1765059207
    title: "OWASP Top 10 for Agentic Applications for 2026"
    author: "OWASP Gen AI Security Project"
    year: 2025
    verified: 2026-11-12
    grade: primary
  - resource: https://blog.sigstore.dev/model-transparency-v1.0/
    title: "Taming the Wild West of ML: Practical Model Signing with Sigstore"
    author: "Maruseac, M."
    year: 2025
    verified: 2026-11-12
    grade: secondary
  - resource: https://slsa.dev/spec/v1.0/about
    title: "About SLSA"
    author: "OpenSSF SLSA project"
    year: 2023
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: agentic-supply-chain
related:
  - skill-library
  - owasp-agentic-top-10
kind: pattern
evidence: explicit
maturity: emerging
diagram:
  file: agentic-supply-chain.svg
  alt: Model, tool, MCP server and skill artifacts flow from an allowlisted registry through a highlighted load-time verifier, which also takes a store of signatures and hashes, before reaching the agent; a kill-switch box feeds into the verifier.
  caption: Agents often compose capabilities at runtime, so signatures are re-checked at runtime too.
x-oldsite-owasp-ids:
  - ASI04
x-oldsite-subdeck: Supply Chain & Secrets
---

## Intent

Keep every component an agent loads traceable to a known source, unaltered, and revocable.

## Context & Forces

OWASP's ASI04, Agentic Supply Chain Vulnerabilities, covers models, tools, plug-ins, datasets, other agents, MCP and A2A interfaces, registries and update channels. It notes that agentic systems often compose capabilities at runtime, shifting focus from manifest to run-time security.

## Structure

OWASP's prevention list includes:

- signing manifests, prompts and tool definitions, with SBOMs and AIBOMs;
- curated registries, allowlists, and pinning by content hash;
- rejecting unsigned components;
- re-checking signatures at runtime;
- a kill switch that disables specific tools, prompts or agent connections across deployments.

Sigstore's model-signing project reached 1.0 in April 2025 and stores signatures in a transparency log. SLSA offers supply-chain security guidelines.

## Consequences & Trade-offs

The sources describe controls, not measured results.

## Related Patterns

- OWASP Top 10 for Agentic Applications
- Skill-Library Compounding

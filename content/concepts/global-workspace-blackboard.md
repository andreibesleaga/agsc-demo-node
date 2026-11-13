---
type: concept
title: Global Workspace as Blackboard
description: "Specialist modules compete to put content in one small workspace whose contents are broadcast to all modules, as in Global Workspace Theory."
status: stable
release: cognitive
tags:
  - attention
  - coordination
  - memory
aliases:
  - global workspace broadcast
  - GWT-style agent architecture
  - attention bottleneck + broadcast
  - LIDA-style cognitive cycle
clusters:
  - cognitive-behavioral
date: 2026-08-18
modified: 2026-11-12
sources:
  - resource: https://pubmed.ncbi.nlm.nih.gov/16186014/
    title: "Global workspace theory of consciousness: toward a cognitive neuroscience of human experience"
    author: "Baars, B. J."
    year: 2005
    verified: 2026-11-12
    grade: primary
  - resource: https://pmc.ncbi.nlm.nih.gov/articles/PMC24407/
    title: "A neuronal model of a global workspace in effortful cognitive tasks"
    author: "Dehaene, S.; Kerszberg, M.; Changeux, J.-P."
    year: 1998
    verified: 2026-11-12
    grade: secondary
  - resource: https://pubmed.ncbi.nlm.nih.gov/17998071/
    title: "An architectural model of conscious and unconscious brain functions: Global Workspace Theory and IDA"
    author: "Baars, B. J.; Franklin, S."
    year: 2007
    verified: 2026-11-12
    grade: secondary
  - resource: https://arxiv.org/abs/2410.11407
    title: "A Case for AI Consciousness: Language Agents and Global Workspace Theory"
    author: "Goldstein, S.; Kirk-Giannini, C. D."
    year: 2024
    verified: 2026-11-12
    grade: secondary
prov:
  origin: imported
  operator: human:andreibesleaga
id: global-workspace-blackboard
related:
  - blackboard
  - metacognitive-monitoring
kind: pattern
evidence: explicit
maturity: emerging
mapping: explicit
diagram:
  file: global-workspace-blackboard.svg
  alt: Four specialist module boxes (perception, memory, evaluation, action) send content through a dashed competition box into a highlighted global workspace box; a dashed line returns the workspace contents to every module.
  caption: "Two flows: modules compete to place content in one small workspace, and its contents return to every module."
x-oldsite-subdeck: Neuro-cognitive skill architectures
---

## Intent

Organise an agent as parallel specialist modules that compete to place content in one small workspace, whose contents all modules receive.

## Context & Forces

Baars (2005) traces Global Workspace theory to cognitive architecture research, including Newell's blackboard model.

## Structure

Dehaene, Kerszberg and Changeux (1998) model a workspace of distributed, densely interconnected neurons alongside specialised processors for perception, action, memory, evaluation and attention. Workspace neurons are recruited when specialised processors are insufficient. Baars and Franklin (2007) describe a hybrid architecture with distributed "codelets" that accounts for the theory and the LIDA architecture. Goldstein and Kirk-Giannini (2024) derive conditions from the theory and argue that language agents could meet them.

This card uses the theory as an engineering analogy and makes no claim about consciousness. It keeps three parts: modules, a workspace, and a return of its contents to the modules.

## Consequences & Trade-offs

The sources do not say how a software workspace should select among modules.

## Related Patterns

- Blackboard
- Metacognitive Monitoring and Control

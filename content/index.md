---
spec_version: 1.0.0-rc.6
okf_version: 0.2
title: AgenticSystemCore Demo Node
description: A live demonstration node of the AgenticSystemCore reference engine — the second node of the Agentic Knowledge Web — running on a small sample of well-known agent-system patterns.
base: https://patterns.agenticsystemcore.com/
lang: en
license: LicenseRef-AgenticSystemCore-Content-Use-1.0
prov:
  origin: imported
  operator: human:andreibesleaga
---

# AgenticSystemCore Demo Node

This site is software at work. It is a live demonstration node of the AgenticSystemCore reference engine, the open-source program that turns a folder of Markdown files into a knowledge node that people and agents can find, check and cite. It is the second node of the Agentic Knowledge Web, beside [agenticsystemcore.com](https://agenticsystemcore.com/): each of the two names the other in its discovery file. Every page and every file here was built by the engine as static files: no application server and no database run behind it.

## What the software does on this node

- **Discovery.** One file tells an agent what this node is and where everything else is, with a digest for every file it names: [`/.well-known/knowledge-linkset`](/.well-known/knowledge-linkset).
- **A typed graph.** The items and the typed links between them, in the format's [published vocabulary](https://agenticsystemcore.com/ns/): [JSON-LD](/graph.jsonld), [Turtle](/graph.ttl) and [N-Quads](/graph.nq).
- **Text for language models.** [`llms.txt`](/llms.txt), [`llms-full.txt`](/llms-full.txt) and the chunk export [`chunks.jsonl`](/chunks.jsonl), every chunk with its source address.
- **Search.** The [search page](/search/) runs in your browser over a static index; nothing leaves this site.
- **Tools for assistants in the browser.** Every item page registers seven page tools that an assistant in the browser can call to search, read, follow links, compose and cite ([how they work](https://github.com/andreibesleaga/agentic-system-core/blob/main/docs/USING-WITH-ASSISTANTS.md)).
- **Machine views.** Beside every page sit a Markdown and a JSON-LD copy — for example the [Markdown](/pages/blackboard.md) and [JSON-LD](/pages/blackboard.jsonld) of [Blackboard](/concepts/blackboard/).
- **Provenance and checked references.** Each item says where it came from and who answers for it, and lists the public sources it rests on, each checked against the source.
- **A change ledger.** Every published change is a line of [`ledger.jsonl`](/ledger.jsonl); the [changelog](/changelog/) lists the tagged versions.
- **Composition.** The [compose page](/compose/) turns the items you tick into a starting set of seven harness files, computed in your browser. The [skill packs](/skills/) give one file per cluster for agent tool folders.

## The sample content

The content is a small sample of well-known agent-system patterns, each described from public sources and grouped into clusters. It is here so the software has real material to work on: every item carries its references, checked against those sources, and a diagram whose text source travels beside it. Browse the [concepts](/concepts/) or the [clusters](/clusters/), or start from the [search page](/search/).

## Run your own node

The engine is the npm package `agentic-system-core`. A Python package of the same name on PyPI checks and reads published nodes. The source is in the [engine repository](https://github.com/andreibesleaga/agentic-system-core). The published items of this node — the Markdown files, the diagram sources and the configuration — are in the [agsc-demo-node repository](https://github.com/andreibesleaga/agsc-demo-node). To begin, read [start here](https://agenticsystemcore.com/docs/start-here/) and [publish a Level-0 node](https://agenticsystemcore.com/procedures/publish-a-level-0-node/) on agenticsystemcore.com.

## What comes next

Planned next: a stated meaning for every typed link, so that the links become a semantic layer software can check, and a graph view of the links — see the [roadmap](https://github.com/andreibesleaga/agentic-system-core/blob/main/docs/ROADMAP.md).

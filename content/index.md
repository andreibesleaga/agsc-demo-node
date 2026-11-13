---
spec_version: 1.1.0
okf_version: 0.2
title: AgenticSystemCore Graph
description: "Agent-system designs as a typed, cited graph, built by the AgenticSystemCore reference engine: the second node of the Agentic Knowledge Web."
base: https://patterns.agenticsystemcore.com/
lang: en
license: LicenseRef-AgenticSystemCore-Content-Use-1.0
prov:
  origin: imported
  operator: human:andreibesleaga
---

# AgenticSystemCore Graph

AgenticSystemCore Graph describes well-known agent-system designs — patterns, failure modes and the ways to classify them — as short cards, each written from the public sources it cites and linked to the others by typed relations. It is the second node of the Agentic Knowledge Web, beside [agenticsystemcore.com](https://agenticsystemcore.com/): each of the two names the other in its discovery file. The AgenticSystemCore reference engine, the open-source program that turns a folder of Markdown files into a knowledge node that people and agents can find, check and cite, built every page and every file here as static files: no application server and no database run behind it.

## What the software does on this node

- **Discovery.** One file tells an agent what this node is and where everything else is, with a digest for every file it names: [`/.well-known/knowledge-linkset`](/.well-known/knowledge-linkset).
- **A typed graph.** The items and the typed links between them, in the format's [published vocabulary](https://agenticsystemcore.com/ns/): [JSON-LD](/graph.jsonld), [Turtle](/graph.ttl) and [N-Quads](/graph.nq).
- **Text for language models.** [`llms.txt`](/llms.txt), [`llms-full.txt`](/llms-full.txt) and the chunk export [`chunks.jsonl`](/chunks.jsonl), every chunk with its source address.
- **Search.** The [search page](/search/) runs in your browser over a static index; nothing leaves this site.
- **Tools for assistants in the browser.** Every item page registers ten page tools that an assistant in the browser can call to search, read, follow links, compose and cite ([how they work](https://github.com/andreibesleaga/agentic-system-core/blob/main/docs/USING-WITH-ASSISTANTS.md)).
- **Queries over the graph.** The [query page](/query/) runs a SPARQL query you write over this node's graph in your browser, with ten example questions to start from; nothing leaves this site.
- **A vocabulary of its own.** Beside the format's own types and links, this node defines four terms in [`domain/vocabulary.ttl`](https://github.com/andreibesleaga/agsc-demo-node/blob/main/domain/vocabulary.ttl): two kinds of item, a *failure mode* and a *safeguard*, and the link *guards against* with its reverse, *guarded by*. [Exception Handling and Recovery](/concepts/exception-handling-and-recovery/) is a safeguard that guards against [Unbounded Loops](/concepts/unbounded-agent-loops/), a failure mode; the graph carries both types and the link both ways. Each kind of item belongs to the context of its own cluster, and `agsc verify` and `agsc ci` test one rule (every safeguard guards against at least one failure mode) and one question (which safeguard guards against each failure mode).
- **Machine views.** Beside every page sit a Markdown and a JSON-LD copy — for example the [Markdown](/pages/blackboard.md) and [JSON-LD](/pages/blackboard.jsonld) of [Blackboard](/concepts/blackboard/).
- **Provenance and checked references.** Each item says where it came from and who answers for it, and lists the public sources it rests on, each checked against the source.
- **A change ledger.** Every published change is a line of [`ledger.jsonl`](/ledger.jsonl); the [changelog](/changelog/) lists the tagged versions.
- **Composition.** The [compose page](/compose/) turns the items you tick into a starting set of seven harness files, computed in your browser. The [skill packs](/skills/) give one file per cluster for agent tool folders.

## The cards

Each card is a short reference text with one diagram: what the design is for, the forces behind it, its structure, what it costs, and the cards it relates to. Every claim rests on the public sources the card cites, each checked against the source and dated. The cards are grouped into clusters and joined by typed links: the [clusters page](/clusters/) shows how the clusters connect, and the [query page](/query/) answers questions over the whole graph. Browse the [concepts](/concepts/), or start from the [search page](/search/). New cards are added over time.

## Run your own node

The engine is the npm package `agentic-system-core`. A Python package of the same name on PyPI checks and reads published nodes. The source is in the [engine repository](https://github.com/andreibesleaga/agentic-system-core). The published items of this node — the Markdown files, the diagram sources and the configuration — are in the [agsc-demo-node repository](https://github.com/andreibesleaga/agsc-demo-node). To begin, read [start here](https://agenticsystemcore.com/docs/start-here/) and [publish a Level-0 node](https://agenticsystemcore.com/procedures/publish-a-level-0-node/) on agenticsystemcore.com.

## What comes next

Each page now shows its typed links in both directions, with what each relation means, and the [clusters page](/clusters/) shows how the clusters connect. What comes after that is in the [roadmap](https://github.com/andreibesleaga/agentic-system-core/blob/main/docs/ROADMAP.md).

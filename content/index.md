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

Short cards on well-known agent-system designs, each written from the public sources it cites and joined to the others by typed links. This is the second node of the Agentic Knowledge Web, beside [agenticsystemcore.com](https://agenticsystemcore.com/) and [standards.agenticsystemcore.com](https://standards.agenticsystemcore.com/); each names the others in its discovery file. The AgenticSystemCore engine built every file here as static files: no server and no database run behind it.

## Six ways to use this node

- **Read it as a wiki.** Browse the [concepts](/concepts/) and the [clusters](/clusters/), or use the [search page](/search/), which runs in your browser. The [NOW page](/now/) lists what has gone stale.
- **Use it as an agent's memory.** An agent starts at the [discovery file](/.well-known/knowledge-linkset), which gives a digest for each file it names, then reads [`llms.txt`](/llms.txt), [`llms-full.txt`](/llms-full.txt) or the passages in [`chunks.jsonl`](/chunks.jsonl). Every item page offers ten tools to an assistant in the browser ([how they work](https://github.com/andreibesleaga/agentic-system-core/blob/main/docs/USING-WITH-ASSISTANTS.md)).
- **Keep specifications alive.** The node's own [decision](/concepts/keep-cards-short/), [card format](/concepts/card-format/) and [gate](/gates/publish-gate/) are items like any other, and the [board](/boards/upkeep/) shows its open tasks.
- **Take the skills.** The [skill packs](/skills/) give one file per cluster for an agent's tool folder, with a hash for every file.
- **Compose.** The [compose page](/compose/) turns the cards you tick into seven starting files, computed in your browser.
- **Work on the board.** Pick an open task on the [board](/boards/upkeep/) and send your change as a pull request to the [agsc-demo-node repository](https://github.com/andreibesleaga/agsc-demo-node), which holds the published items. A person merges it.

## The graph

The items and their typed links are published as [JSON-LD](/graph.jsonld), [Turtle](/graph.ttl) and [N-Quads](/graph.nq), in the format's [published vocabulary](https://agenticsystemcore.com/ns/). The [graph explorer](https://agenticsystemcore.com/graph/?src=https%3A%2F%2Fpatterns.agenticsystemcore.com%2F) draws it, and the [query page](/query/) runs a SPARQL query over it in your browser. This node adds four terms of its own in [`domain/vocabulary.ttl`](https://github.com/andreibesleaga/agsc-demo-node/blob/main/domain/vocabulary.ttl): a *failure mode*, a *safeguard*, and the link *guards against* with its reverse. Beside every page sit a Markdown and a JSON-LD copy, for example the [Markdown](/pages/blackboard.md) and [JSON-LD](/pages/blackboard.jsonld) of [Blackboard](/concepts/blackboard/). Every published change is a line of [`ledger.jsonl`](/ledger.jsonl); the [changelog](/changelog/) lists the tagged versions.

## Run your own node

The engine is the npm package `agentic-system-core`; its source is in the [engine repository](https://github.com/andreibesleaga/agentic-system-core). To begin, read [start here](https://agenticsystemcore.com/docs/start-here/) on agenticsystemcore.com.

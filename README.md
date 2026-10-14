# AgenticSystemCore Demo Node

A live demonstration node of the AgenticSystemCore reference engine: the engine's own
software, running on a small sample of well-known agent-system patterns described from
public sources. It is the second node of the Agentic Knowledge Web, beside the reference
node at <https://agenticsystemcore.com/>; each names the other in its discovery document.

Published at <https://patterns.agenticsystemcore.com/>.

**This repository holds the published items of the node, and only those.** The maintainer
keeps the node in a working copy that also holds items still in draft; a draft appears on
no published surface and is not part of this repository. Built from the same history, the
files here produce the same pages, graph and exports as the live node. A build of this
repository gives the same content with this repository's own change ledger and content
version, because both derive from the git history (AGSC-04-25).

This repository is one **Bundle** of the Agentic System Core format — Markdown items with
YAML frontmatter, compiled by the `agsc` engine into a static site, an RDF knowledge graph,
a search index, a chunk export, skill packs, a change ledger and a discovery document. The
engine is the npm package `agentic-system-core`; its source is
<https://github.com/andreibesleaga/agentic-system-core>. Everything on the site is built by
that engine from the files here, with no application server.

**What is different about it.** Other systems have some of these. To the author's knowledge none
has them together: a knowledge base a machine can find through registered web
mechanisms, an integrity digest on every artefact link of its discovery document, a typed graph with a published
vocabulary, bytes pinned by conformance vectors, a person on every merge — directly, or
by a standing rule that person recorded — and a starting harness of seven kinds of file out of the same files,
with no server. This node shows them working.

**What it demonstrates.** Discovery through `/.well-known/knowledge-linkset`; the typed
graph (`/graph.jsonld`, `/graph.ttl`, `/graph.nq`); text for agents to search, cite and
compose (`/llms.txt`, `/chunks.jsonl`, the seven tools on every item page); a Markdown and a
JSON-LD view beside every page; provenance and checked references on every item; the change
ledger (`/ledger.jsonl`); and the `/compose/` page, which turns selected items into a
starting harness of seven kinds of file. [docs/CARDS.md](docs/CARDS.md) shows how one item
becomes a page, a graph node, a skill and a chunk.

**Try the engine in five minutes.** The engine repository carries one page of runnable
demos — the six modes and the sixteen personas, each from an empty folder with the exact
commands, the lines they print and the one thing it proves, every command run by a test
so the page cannot drift: [docs/DEMOS.md](https://github.com/andreibesleaga/agentic-system-core/blob/main/docs/DEMOS.md)
(short form on the main site at <https://agenticsystemcore.com/docs/demos/>). The same
commands work on this node: `agsc build` here, then the tool calls of the agent demo
against this Bundle.

## What is in here

| Path | What it holds |
|---|---|
| `agsc.config.json` | the Bundle's one configuration file (AGSC-01-17) |
| `content/index.md` | the Bundle root item |
| `content/concepts/*.md` | one item per pattern |
| `content/clusters/*.md` | the collections the items name in their `clusters[]` |
| `content/diagrams/*.diagram` | the text source of each item's diagram; the SVG is produced by the build, never committed (AGSC-01-07) |
| `publish-set.json` | the list of items that are published; in this repository every item is on it |
| `.well-known/security.txt` | where to report a security problem; the build publishes it at `/.well-known/security.txt` (RFC 9116), so the folder has no README of its own |
| [docs/](docs/README.md) | how an item becomes a page, a graph node, a skill and a chunk, with a diagram |
| `www/` | the build output (generated; not committed) |

[content/README.md](content/README.md) describes the folders of the Bundle.

## Working with it

The engine is the `agentic-system-core` package. From the root of this repository:

```sh
agsc lint            # the parse, schema, link and governance lanes
agsc build           # the route set of AGSC-06-01 into www/
agsc verify          # re-checks the built output against its digests (--ledger for the ledger)
agsc ci              # lint, build twice and compare the bytes, then verify
```

Every emission is byte-reproducible: set `SOURCE_DATE_EPOCH` and two runs on two machines
produce the same bytes. Build from a git clone, not from a downloaded archive: the home
page links the change ledger and the changelog, and both derive from the git history.

## Status

Every item carries a `status`. An item marked `draft` appears on no published surface —
not on a page, not in `llms.txt`, `search.json`, `chunks.jsonl` or the graph — until a
person has read it against its sources and changed that one field. Every item in this
repository is `stable`. `publish-set.json` lists them, and the engine's tool reports any
disagreement between the list and the files:

```sh
node ../agentic-system-core/tools/publish-set --check .
```

Nothing here claims priority or novelty for any pattern. Each item cites the public
sources it rests on in its own `sources[]`, and the first entry is the one the claim
depends on.

## Licences

* **Code** (anything executable in this repository): Apache-2.0 — see `LICENSE`.
* **Schemas and vocabulary** carried from the format: CC0-1.0.
* **Prose** (item bodies and descriptions, and the pages built from them): the
  AgenticSystemCore Content Use Terms — see `LICENSE-CONTENT`.

## How this is made

This work is written and maintained by Andrei N. Besleaga with the help of AI
assistants. A person decides what is written, an assistant drafts and checks it, and a
person reads, edits and approves everything that is published and answers for it. Every
published item records how its text was made and names the person accountable for it.
Written with AI assistance, reviewed and published by a person.
The assistance covered text, figures and diagrams alike. No model runs on the site or in
its build. What an assistant or agent writes from this work is its own output, not a
statement by the author.

## What this does not claim

This is the independent work of one person, published as it is, with no warranty of any
kind and no liability for anything that follows from using it. Nothing in it is legal or
professional advice. No standards body, foundation, company or institution named in this
repository has reviewed, approved or is connected with this work, and it is not a document
of the IETF, of the W3C or of any other body. Other product and organisation names are the
marks of their owners and are used only to say what is being talked about.
Every right not expressly granted by the licences is reserved, and nothing here promises
that the work or its addresses will stay available.

## Notice

AgenticSystemCore™ is a trademark of Andrei N. Besleaga. Other names belong to their owners.

## Where the items came from

Each item is written from the public sources it cites. No item carries text or figures from
another publication: a lint (AGSC-08-17) refuses the phrases and references that would show
borrowed framing, and a person reads each item against its sources before it is published.

## The switch on the main site

The main site names this node as its peer. One setting there,
`"x-patterns-node"` in that repository's `agsc.config.json`, turns the peer link and the
sentences that promise this node on or off.

## Contributing

**To propose an item**, add `content/concepts/<slug>.md` with the frontmatter of the other
items (type, title, description, kind, tags, clusters, provenance and at least one
source), leave it `status: draft`, run `agsc lint`, and open a pull request. A person
reads it against its sources. An accepted change is applied in the maintainer's working
copy and appears here with the next update of this repository.

Corrections to a source, a description or a diagram are welcome as pull requests against
the item file. Please keep an item's `sources[]` first entry the source its claim actually
rests on, and quote the sentence you are relying on in the pull request.

By contributing you sign off under the contributor agreement of the format,
`CONTRIBUTOR-AGREEMENT` in the engine repository (token `CA-v1`): you keep the copyright
in your text and grant the maintainer a non-exclusive licence to publish it here and in
other collections and editions the maintainer makes from this catalogue; you may choose,
contribution by contribution, to assign it instead. Your name stays on the item.

[CONTRIBUTING.md](CONTRIBUTING.md) says how, and the [code of conduct](CODE_OF_CONDUCT.md)
applies. Security reports go to this repository's private vulnerability reporting, as
[SECURITY.md](SECURITY.md) says, never to a public issue.

---

© 2026 Andrei N. Besleaga. Code: Apache-2.0. Schemas, ontology, identifiers and the
discovery document: CC0-1.0. Prose: the Content Use Terms in `LICENSE-CONTENT`.

# `content/` — the Bundle

**Summary.** The sample content of this demonstration node as one Bundle: one Markdown file per card with a YAML
block at the top, the collections the cards belong to, and the text source of each
card's diagram. `index.md` is the Bundle's root document. The engine builds every page,
graph view, chunk, skill pack and text file of the node from these files.

**Read after:** the repository [README](../README.md) and [docs/CARDS.md](../docs/CARDS.md).

| Folder | What it holds |
|---|---|
| `concepts/` | one card per pattern (a Concept with a `kind`) |
| `clusters/` | the collections cards name in their `clusters[]`; a cluster is published when a published card names it |
| `diagrams/` | `<slug>.diagram`, the source of a card's diagram; the SVG is produced by the build, never committed (AGSC-01-07) |

A README is kept only at this level, and this one describes the three type folders: a
`README.md` inside a type folder is not a card, but the engine reports each one it skips as a
warning on every `lint`, `build` and `ci`. Which cards are published is `publish-set.json` at the root, applied with the
engine's `tools/publish-set`.

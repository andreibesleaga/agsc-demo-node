# Contributing

This repository holds the published items of the demonstration node. The maintainer
keeps the node in a working copy that also holds items in draft; an accepted change is
applied there and appears here with the next update of this repository. The engine,
the specification and the vocabulary live in the
[engine repository](https://github.com/andreibesleaga/agentic-system-core); a change to
those is proposed there, as its
[CONTRIBUTING.md](https://github.com/andreibesleaga/agentic-system-core/blob/main/CONTRIBUTING.md)
describes.

## Proposing an item or a correction

**To propose an item**, add `content/concepts/<slug>.md` with the frontmatter of the
other items (type, title, description, kind, tags, clusters, provenance and at least
one source), leave it `status: draft`, run `agsc lint`, and open a pull request. A
person reads it against its sources.

**A correction** to a source, a description or a diagram is a pull request against the
item file. Keep an item's first `sources[]` entry the source its claim actually rests
on, and quote the sentence you are relying on in the pull request.

Before you open one, from the root of this repository with the engine installed:

```sh
agsc lint && agsc ci
```

## Signing off

An outside contribution, a commit from anyone other than the maintainer, signs off
under the contributor agreement `CA-v1`, the file
[`CONTRIBUTOR-AGREEMENT`](https://github.com/andreibesleaga/agentic-system-core/blob/main/CONTRIBUTOR-AGREEMENT)
in the engine repository. Read it before your first commit. Each commit message ends
with a line of this shape:

```
Signed-off-by: Ada Lovelace <ada@example.org> (CA-v1)
```

`git commit -s` writes the first part of that line; add ` (CA-v1)` at its end. The
maintainer's own commits are exempt. You keep the copyright in your text and grant the
maintainer a non-exclusive licence to publish it here and in other collections and
editions the maintainer makes from this catalogue; you may choose, contribution by
contribution, to assign it instead. Your name stays on the item. A contribution to
prose also certifies that you may submit it under the Content Use Terms in
`LICENSE-CONTENT`. The engine's CONTRIBUTING.md, "Signing off", says what the
agreement means.

Your name, the address you commit under and your sign-off become part of the public
history and of the change ledger the node publishes. If you would rather not publish
an address, GitHub's `users.noreply.github.com` address works.

## Conduct and security

The [code of conduct](CODE_OF_CONDUCT.md) applies everywhere the project is
represented. A security problem is never an issue or a pull request: report it
privately, as [SECURITY.md](SECURITY.md) says.

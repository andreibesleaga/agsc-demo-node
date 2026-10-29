# AGENTS.md

Instructions for an assistant or agent working in this repository. The
[README](README.md) is the source for what the repository is and
[CONTRIBUTING.md](CONTRIBUTING.md) for how a change is proposed; this file only
collects the commands and rules an agent needs first.

## What this is

The published items of the demonstration node at <https://patterns.agenticsystemcore.com/>:
one Bundle of the AgenticSystemCore format. Items are Markdown files with YAML frontmatter
in `content/`; the `agsc` engine (npm package `agentic-system-core`) builds the site, graph
and machine files from them into `www/`. There is no application code here.

## Commands

Run from the repository root, with `agsc` installed as the README describes. Use a git
clone, not a downloaded archive: the ledger and the content version derive from git history.

```sh
agsc lint              # checks every item; writes nothing
agsc build             # writes the site into www/
agsc verify --ledger   # builds twice, compares the bytes, recomputes the ledger chain
agsc ci                # the gate: lint, two builds compared, verdict
agsc conform --level 2 # the conformance cases of Level 2
```

The full gate is `.github/workflows/test.yml`; CONTRIBUTING.md lists its steps. The
`publish-set` and `public-hygiene` steps use the engine's `tools/`, which needs the engine
cloned beside this repository.

## Rules

- Change item files in `content/concepts/` and `content/clusters/` only as CONTRIBUTING.md
  says. A new item stays `status: draft` until a person has read it against its sources.
- Keep an item's first `sources[]` entry the source its claim rests on.
- `publish-set.json` lists the published slugs. Do not edit it to publish an item; the
  maintainer applies accepted changes.
- Never commit `www/`, `dist/`, a compiled diagram `.svg` or a `.env` file. `.gitignore`
  ignores the first two and `.env`; lint refuses a tracked `.env` and a compiled `.svg`
  under `content/diagrams/`.
- Item and JSON files are UTF-8 without BOM, LF line endings, NFC-normalised, ending in
  exactly one line feed; `agsc lint` checks this.
- A security problem is reported privately as SECURITY.md says, never in an issue or a
  pull request.
- No secrets, tokens or personal data in any file: `public-hygiene` runs over the whole
  repository in CI.

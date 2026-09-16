# Repolex Knowledge Graph of mccormicka/string-argv

RDF knowledge graph data for [mccormicka/string-argv](https://github.com/mccormicka/string-argv), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download mccormicka/string-argv
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7415c20121bfa02887162b8326042563b903c332
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 7415c20121bfa02887162b8326042563b903c332.nq.gz
│   └── repolex
│       └── 7415c20121bfa02887162b8326042563b903c332
│           └── chunk-001.nq.gz
├── blob
│   ├── 216a7b3f5741dac90a0a2c882cf7358d37cf845b.nq.gz
│   ├── 30cd4820b054bd80456cbe249ed17d9619354854.nq.gz
│   ├── 3a2882a5e2b19c92fd614a2a0a2d94fb68ef2436.nq.gz
│   ├── 4535bb5251f7aaac8a22979ef67f2b3be7e8cf17.nq.gz
│   ├── 543acb058dfa9c35b3cec4d2760cd65261db5420.nq.gz
│   ├── 5f49141f3fdb4973ad86c1ed01f92646556e3946.nq.gz
│   ├── 7e8742819003b97364eed1a41b80f2284cf3b1c3.nq.gz
│   ├── b4a0bdd56f0410db23981c78ad675c480ac30ea6.nq.gz
│   ├── be667eb13c1a5edd78fa36cc405cb73b0afb9398.nq.gz
│   ├── ca32cb086e3dfcb1173ccf77634de1fdc62998ff.nq.gz
│   └── ce37111611585bedea328d11f235ced6270b5561.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 7415c20121bfa02887162b8326042563b903c332.nq.gz
├── filetree
│   └── 7415c20121bfa02887162b8326042563b903c332.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |

## Source repository

[mccormicka/string-argv](https://github.com/mccormicka/string-argv)

---
*Parsed on 2026-09-16 by [repolex](https://repolex.ai)*

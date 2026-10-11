# Repolex Knowledge Graph of tox-dev/tox-tags

RDF knowledge graph data for [tox-dev/tox-tags](https://github.com/tox-dev/tox-tags), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download tox-dev/tox-tags
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c9968c0de98b6a2e74daf5ea124b657d97210bc5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c9968c0de98b6a2e74daf5ea124b657d97210bc5
│           └── chunk-001.nq.gz
├── blob
│   ├── 586013db7b61e335522de5799cc02a2f415def88.nq.gz
│   ├── 6b43cf13cb7216c3969fce8b5a13d5aa09b74b6b.nq.gz
│   ├── 7370761d875090ae9d425a9050dcfc5c98a06f12.nq.gz
│   ├── a1e2f39271452feaf98ecad0b36e87e69b6c8a4c.nq.gz
│   ├── bd5e80bc71aaf94b9f7d9c22a409d148d7b6dfe0.nq.gz
│   ├── cc62e27afe370e017f832c454b6c8174fd121fcf.nq.gz
│   ├── d7bb25d7d86dc85414b80113e55e8f30cd52c26c.nq.gz
│   └── ed58d0f26c9b0ec7b7bbcf87cc2383b3a1763812.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c9968c0de98b6a2e74daf5ea124b657d97210bc5.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 15 files
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
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[tox-dev/tox-tags](https://github.com/tox-dev/tox-tags)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*

# Repolex Knowledge Graph of jupyterhub/gh-scoped-creds

RDF knowledge graph data for [jupyterhub/gh-scoped-creds](https://github.com/jupyterhub/gh-scoped-creds), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/gh-scoped-creds
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fe538a4bbc189ae3240301e125828984dc0abf89
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fe538a4bbc189ae3240301e125828984dc0abf89
│           └── chunk-001.nq.gz
├── blob
│   ├── 037746ed1093dbfd42a772644c0528ea79933ba4.nq.gz
│   ├── 33ce3cf1f6800731cac06ac18621dc9237be6eb3.nq.gz
│   ├── 4e5e54e3f1077915a456df6f055f7666f19096fe.nq.gz
│   ├── 58538de2c6c120db0ec0a49edd6ecf457488f7ac.nq.gz
│   ├── 60d2cefd9e201eb6e396cafe2ff93dc1ec3e9b81.nq.gz
│   ├── 9baa3f7ee9fb4c53f4ce64f5922bff0d80548e1a.nq.gz
│   ├── 9e02d2b1c3bd674a62adddff6a720794b4c75964.nq.gz
│   ├── a0d66a3502ae40604610700099e545b749cf0ee5.nq.gz
│   ├── b6e47617de110dea7ca47e087ff1347cc2646eda.nq.gz
│   ├── d2139b7f136e675d20769d488d591081acb8ccbe.nq.gz
│   └── dc3fb32a92571e4909d94fca916be0268d0bfcbd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fe538a4bbc189ae3240301e125828984dc0abf89.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 19 files
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

[jupyterhub/gh-scoped-creds](https://github.com/jupyterhub/gh-scoped-creds)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*

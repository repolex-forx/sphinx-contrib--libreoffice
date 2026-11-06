# Repolex Knowledge Graph of sphinx-contrib/libreoffice

RDF knowledge graph data for [sphinx-contrib/libreoffice](https://github.com/sphinx-contrib/libreoffice), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/libreoffice
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f99a23bdf4a681b0c6fc3c771ec541f4f969162e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f99a23bdf4a681b0c6fc3c771ec541f4f969162e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e465f76d7bd7898f118369cc5cd4d6f0e3ff84f.nq.gz
│   ├── 2eba9160d403563d8b100534a4d950281de057e6.nq.gz
│   ├── 4e211d5218173b085754edc67c9f03a98b4f6499.nq.gz
│   ├── 59261c17edfc2c63ae69c50a266124c29e5922c5.nq.gz
│   ├── 68d5b226e0775eaec5b110884108423dd5cb0284.nq.gz
│   ├── 7bed9ea86cde52bf879dcc0c806f49c43e20e367.nq.gz
│   ├── 7f17f8b3c4e2f248db2a1bb7eccf22934aac4d10.nq.gz
│   ├── 81f1161b7f804e9e8b12ff35517315dd4ec83971.nq.gz
│   ├── 910f1cba0df6884705c5b61780bfb0ed31d5244d.nq.gz
│   ├── 96fadd5c340a3393908c0378392e79bd5dd16f13.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── b6080b701d2f2c4ffbccdb6126b32a95861a3041.nq.gz
│   ├── cceb018c1894484d53bf9e3c590e7d4b418ccd96.nq.gz
│   └── da0e5f6db469847d0edd9071ac225113e91418dc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f99a23bdf4a681b0c6fc3c771ec541f4f969162e.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 20 files
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

[sphinx-contrib/libreoffice](https://github.com/sphinx-contrib/libreoffice)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*

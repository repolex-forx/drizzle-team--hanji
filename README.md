# Repolex Knowledge Graph of drizzle-team/hanji

RDF knowledge graph data for [drizzle-team/hanji](https://github.com/drizzle-team/hanji), parsed by [repolex](https://repolex.ai).

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
rlex download drizzle-team/hanji
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 96430391482a6340d8ab7facdadb38c8bc43feb4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 96430391482a6340d8ab7facdadb38c8bc43feb4
│           └── chunk-001.nq.gz
├── blob
│   ├── 0db7e9f7960464fca1e885ba8d08c44b1c1f9d8c.nq.gz
│   ├── 0e6969595249e4c549dd1db2abf5da07b7f8b83d.nq.gz
│   ├── 117b4ef1c8cead6faed9e55034454d79169eb63b.nq.gz
│   ├── 206c5f7d984ce86d9fff326600fe3016a49f1360.nq.gz
│   ├── 211d2ae0a3c85bd501bd36413543ad0db69625f2.nq.gz
│   ├── 2dc0c05b53984fc670472db3707b7e9f5524a1f5.nq.gz
│   ├── 45dab348778dca42431235173dc974fd8e254d93.nq.gz
│   ├── 5e578ca6e1aa817d8af9640f3796c890d7375378.nq.gz
│   ├── 8b5840acac7af00022dc5e1797e1ee64c69c745d.nq.gz
│   ├── 9132dd42dda9377eeac82bb84a24e8a188fd797b.nq.gz
│   ├── bc0f1245903adb083e6d4169ed61fb6e145d3502.nq.gz
│   ├── c5e7c725515ee4e61b38f2e149133b440057810c.nq.gz
│   ├── d802d5a2e2184ce6997378f309ba5b43df9fe68f.nq.gz
│   ├── ef91ff132fccbd99c790fde1c2433a684555b5ac.nq.gz
│   └── fb15d37137cf4d5e9b7979755f86c36138fa45fe.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 96430391482a6340d8ab7facdadb38c8bc43feb4.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 22 files
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

[drizzle-team/hanji](https://github.com/drizzle-team/hanji)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*

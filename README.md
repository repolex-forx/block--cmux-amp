# Repolex Knowledge Graph of block/cmux-amp

RDF knowledge graph data for [block/cmux-amp](https://github.com/block/cmux-amp), parsed by [repolex](https://repolex.ai).

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
rlex download block/cmux-amp
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 55a838c0259d3080f1741dae0d4826ac22d63eba
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 55a838c0259d3080f1741dae0d4826ac22d63eba.nq.gz
│   └── repolex
│       └── 55a838c0259d3080f1741dae0d4826ac22d63eba
│           └── chunk-001.nq.gz
├── blob
│   ├── 39fa5c6acc88c0bc9d99d785fafdea8121a98b62.nq.gz
│   ├── 6bccf43368fd7c96d9c659562a5142b8b8cb98a1.nq.gz
│   ├── 7b6f00c79e2112dd91eec613c648752ed32afb49.nq.gz
│   ├── 862ee3c28647e7a58801a75236855c269c1448ae.nq.gz
│   ├── 9582fc588754f78d9875691a3bd5e674295436b3.nq.gz
│   ├── a26495f016b5c89fbacd809caa28712510bac10b.nq.gz
│   ├── cca047d50102334bc96dd7add3560a73b6704649.nq.gz
│   └── f70b36a7ca07f50bb01a2d14e25d1eac52278a03.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 55a838c0259d3080f1741dae0d4826ac22d63eba.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 17 files
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

[block/cmux-amp](https://github.com/block/cmux-amp)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*

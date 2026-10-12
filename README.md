# Repolex Knowledge Graph of falconry/falcon-oauthlib

RDF knowledge graph data for [falconry/falcon-oauthlib](https://github.com/falconry/falcon-oauthlib), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/falcon-oauthlib
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6e09a06bef271f33956ec187e1bf2f1f550dc424
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6e09a06bef271f33956ec187e1bf2f1f550dc424
│           └── chunk-001.nq.gz
├── blob
│   ├── 146f2ec5cfff1e635a6ce831c4a1225f71b67507.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 6f429d13e475f7ce058303dbc42b3506c752041b.nq.gz
│   ├── 7fdbe17c6067880ad8c535c03ebc0c2d58d8c64f.nq.gz
│   ├── 8c588c327b8746975fc0c4bfdedf0b96b39519ec.nq.gz
│   ├── c4058a2393f2e7bef675e3cdd09e8526bfabf75b.nq.gz
│   ├── caa43cf41008a6d111daea0a6df494a1cdd80f28.nq.gz
│   └── f7b6ebdab94483ed2bfa8f4b69e68a93133e21e3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6e09a06bef271f33956ec187e1bf2f1f550dc424.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
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

[falconry/falcon-oauthlib](https://github.com/falconry/falcon-oauthlib)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*

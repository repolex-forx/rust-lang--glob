# Repolex Knowledge Graph of rust-lang/glob

RDF knowledge graph data for [rust-lang/glob](https://github.com/rust-lang/glob), parsed by [repolex](https://repolex.ai).

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
rlex download rust-lang/glob
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cfa2a58f2e44373573f657ec25b3621e44714dee
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── cfa2a58f2e44373573f657ec25b3621e44714dee.nq.gz
│   └── repolex
│       └── cfa2a58f2e44373573f657ec25b3621e44714dee
│           └── chunk-001.nq.gz
├── blob
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1de004bd6b95e45f01c4f0f48e52a6204d983acb.nq.gz
│   ├── 20e21417fec394367278b6c5ddf5554804d4d99c.nq.gz
│   ├── 39d4bdb5acd313c1a92dbeaa1c379aaf0596a315.nq.gz
│   ├── 3ef50911ea942df1c33d5fb8662ef9e2758a28f0.nq.gz
│   ├── 4067f126a6dc41144c6edafe7d642ce5179d0e3c.nq.gz
│   ├── 4b93b56a7159230aec4ea9a33df758cf51c4cf9c.nq.gz
│   ├── 4fffb2f89cbd8f2169ce9914bd16bd43785bb368.nq.gz
│   ├── de9707038a57718f2ee84260b67ba1be822cfd70.nq.gz
│   ├── f5f772bccdbbcf62272687bf285c809d8116f2b1.nq.gz
│   ├── f8c537910f0ade813897054c23388186fbbd4714.nq.gz
│   └── fa0824ac53c0a9c130636512c0271fc3f0e9c0e6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── cfa2a58f2e44373573f657ec25b3621e44714dee.nq.gz
├── filetree
│   └── cfa2a58f2e44373573f657ec25b3621e44714dee.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

[rust-lang/glob](https://github.com/rust-lang/glob)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*

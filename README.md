# Repolex Knowledge Graph of oven-sh/bun-pypi

RDF knowledge graph data for [oven-sh/bun-pypi](https://github.com/oven-sh/bun-pypi), parsed by [repolex](https://repolex.ai).

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
rlex download oven-sh/bun-pypi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 26ef65de45ea661e462080b1891cc9832f06b35e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 26ef65de45ea661e462080b1891cc9832f06b35e
│           └── chunk-001.nq.gz
├── blob
│   ├── 076983cdc2b9450ed83069f75bc71a5c8ec9bca1.nq.gz
│   ├── 28b4f21748c96ccc0f5e1d38dc3ffffb24a1df7b.nq.gz
│   ├── 3b79d580b657d07e1b625adddcd3178d68694563.nq.gz
│   ├── 487f205adb26a7b35eac88d95da1a97c5f86150c.nq.gz
│   ├── 4d8d9aaa57a7781810a17350a4e29c53e90ed5e8.nq.gz
│   ├── 579875fe90ab5b2d8ae78781bdc345525a26a21e.nq.gz
│   ├── 632865269b88782626b675a52861511f27eb3e9f.nq.gz
│   ├── 64a9c010c00dbe4ad54807b9116bde80e24dd3ac.nq.gz
│   ├── 67e16c71991166ea5b0e6b82a77fae7ec7d32901.nq.gz
│   ├── 7ba76bdd51493d7b10a0f0eb6df1c0c2bddc20fd.nq.gz
│   ├── 7c0db670dc120428783cf59da504011d424bb291.nq.gz
│   ├── 879b22a0a0284efc3ca513e6c71be0f343ec18c0.nq.gz
│   ├── a7845e094cf482b5d41940aca6ff1dbecb64ff52.nq.gz
│   ├── a986298b02d8469d020f4ae4d89d8b56c20d133e.nq.gz
│   ├── b8a4007c5473f4f92e781a82f627647fe771681a.nq.gz
│   ├── c6031940f530f4bd033820421f93f3d0bffe7112.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 26ef65de45ea661e462080b1891cc9832f06b35e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 24 files
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

[oven-sh/bun-pypi](https://github.com/oven-sh/bun-pypi)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*

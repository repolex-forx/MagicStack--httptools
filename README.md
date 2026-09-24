# Repolex Knowledge Graph of MagicStack/httptools

RDF knowledge graph data for [MagicStack/httptools](https://github.com/MagicStack/httptools), parsed by [repolex](https://repolex.ai).

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
lexq download MagicStack/httptools
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 26461dae5a108d8e8b1e6cc206779055999f7905
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 26461dae5a108d8e8b1e6cc206779055999f7905.nq.gz
│   └── repolex
│       └── 26461dae5a108d8e8b1e6cc206779055999f7905
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f18e3f6007ff1a019abbdc5e0c1e28cfb58af7d.nq.gz
│   ├── 1d8df4354110cdbcc51402f8095b4490755ec358.nq.gz
│   ├── 20c91456144ce4467b32c7c3c4e874424da9be7f.nq.gz
│   ├── 284ec93c8dee362d6916ddcee322ae4429a96073.nq.gz
│   ├── 2fa5026375e8004fc44c116169ea8418b4261f3a.nq.gz
│   ├── 3281864faf3d7be601ec82cfbcfe14a875cdbaab.nq.gz
│   ├── 49908f34e3edde654cd7dae87487f724d340cfcc.nq.gz
│   ├── 659db31a3dd4d75a0c05d540f242d3884b7115fb.nq.gz
│   ├── 79a03ca513a7c94562cb1f8d83aa8bfc736ba0c2.nq.gz
│   ├── 85c6ce71dfb9bbb7225563ba48933ce19f273da8.nq.gz
│   ├── 86584c3a83c7169089b03350aa829a8353dde6a7.nq.gz
│   ├── 8a714bfd73ef7078617025e6857806320dca32cc.nq.gz
│   ├── 8e95925582da55a3ce8cfd011cb332f8a600eb26.nq.gz
│   ├── 972053ef44931bbb6ad35da1996b43d2a8a17348.nq.gz
│   ├── 9a2596a97c0927aaa1c513a6f0ff54ce9ccc4ae7.nq.gz
│   ├── 9dd51c15ef57b1952888eb435cfe8217838be18f.nq.gz
│   ├── a0b9471e2571b43cb8a7833bc2ee18143d2cf421.nq.gz
│   ├── ab9265a22d0e8e59e8959313430f6324d777b8ce.nq.gz
│   ├── bc24c4661c98aeb75e56a47d7448b84f489daebf.nq.gz
│   ├── bc28b50ecffc834812734c61e683813084175883.nq.gz
│   ├── c3b423412baebfaff9359d4a58031774e5de175d.nq.gz
│   ├── ce045e41451a18a51cd0ae0c1f03070984b55a3e.nq.gz
│   ├── d30a32427bb3deec553ef9eaa4e053d3626a16d4.nq.gz
│   ├── d4915a904e7da9ab31a5cb8a6c80b03a0f9e5600.nq.gz
│   ├── f3d34881047ad94b1c5f2c02d4d77e41c899bc53.nq.gz
│   └── f694bb485d1a85fc33b91335daeb6a9fd17c2fe7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 26461dae5a108d8e8b1e6cc206779055999f7905.nq.gz
├── filetree
│   └── 26461dae5a108d8e8b1e6cc206779055999f7905.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 36 files
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

[MagicStack/httptools](https://github.com/MagicStack/httptools)

---
*Parsed on 2026-09-24 by [repolex](https://repolex.ai)*

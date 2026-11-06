# Repolex Knowledge Graph of google-deepmind/tree

RDF knowledge graph data for [google-deepmind/tree](https://github.com/google-deepmind/tree), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/tree
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1728f97edd92c7f49b8276e3c868aa28a4dea81c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1728f97edd92c7f49b8276e3c868aa28a4dea81c
│           └── chunk-001.nq.gz
├── blob
│   ├── 15ce2e97e874a6d86e4fcf2734590c74127e29de.nq.gz
│   ├── 1f75426c1025a1a6648be5620a1467a61e17cb98.nq.gz
│   ├── 359ce0cafa668427d6fe0fc773c6014e7c8c0a72.nq.gz
│   ├── 3bd0005c27c220816efeb47f30adce5577a6a5e2.nq.gz
│   ├── 4266a10a36b1757684e4e73f2094108b30ad4de1.nq.gz
│   ├── 49c68900d9b290b180f80449830c86eec2805041.nq.gz
│   ├── 51285967a7d9722c5bdee4f6a81c154a56aa0846.nq.gz
│   ├── 5456a9043b952e35bd2811b3798ebc3fd07decff.nq.gz
│   ├── 548c33df42db38f96ab3bb32b22422a6a80fa3f1.nq.gz
│   ├── 5859d3c46856b5b005d7357061d9232041a02315.nq.gz
│   ├── 6c24b41d602500ba8e5a6d1e990dc7e187bd31fc.nq.gz
│   ├── 8cec8cf45845416a3225220fad55d17fe96e655a.nq.gz
│   ├── a8e663291b0e97a60c19ba6d37aaaf33bd93f462.nq.gz
│   ├── b95ea06c78160434627345cf5d53b43ba312c2a5.nq.gz
│   ├── c49826bbafbc997a1383d9d746e9453953579ec1.nq.gz
│   ├── c507d09a4c15fc4bdc50f06774edc1535e1367b8.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── db177d4ac70f76c2172ce65ca33c830d6cbd3ac5.nq.gz
│   ├── e04d77d0eb1c44b549238f13c211b8672ab6dad1.nq.gz
│   ├── eeefd77fc9be7648336f7e77c057d718877d5f7c.nq.gz
│   └── f46f5c1e81cb6da8f55d2ea5f49fe91cfa4fd1a9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1728f97edd92c7f49b8276e3c868aa28a4dea81c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[google-deepmind/tree](https://github.com/google-deepmind/tree)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*

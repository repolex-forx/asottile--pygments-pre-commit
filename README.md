# Repolex Knowledge Graph of asottile/pygments-pre-commit

RDF knowledge graph data for [asottile/pygments-pre-commit](https://github.com/asottile/pygments-pre-commit), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/pygments-pre-commit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── afe05c3fdc66b61af3b4e56fa5214576436f3f0f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── afe05c3fdc66b61af3b4e56fa5214576436f3f0f
│           └── chunk-001.nq.gz
├── blob
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 3fdffa121e3b0e62264cdf10bc360c93537670b7.nq.gz
│   ├── 6139f1aa3b52444b22ac27c90448c75ca922a272.nq.gz
│   ├── 6a581d61107450a11a858edb40a654fcf8a19afb.nq.gz
│   ├── 71450061789b8092b63eb4668dd5098a5f14397f.nq.gz
│   ├── 98773dd6fb07fe7cd2f71b10f94edb2dcf2b9a62.nq.gz
│   ├── a2bdb83a92e77fa106a5e0b8dc9dfca6c0b5075d.nq.gz
│   ├── a7f686449b996f8742f42e31a48634031331ebdb.nq.gz
│   ├── b6912dcbafa641c5baeb213502d79cb7c572ebcc.nq.gz
│   ├── b7af5ef213084fe100c5bb755659ef68c14dae5b.nq.gz
│   ├── cbfe2013e389f283c2cdb1de3ae16b1327679121.nq.gz
│   ├── d3cee70cf203431e1b79a8d2be277ac322ddda19.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f82d0e52615387a397c0d4f6f3b1cdac0898744b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── afe05c3fdc66b61af3b4e56fa5214576436f3f0f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 21 files
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

[asottile/pygments-pre-commit](https://github.com/asottile/pygments-pre-commit)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*

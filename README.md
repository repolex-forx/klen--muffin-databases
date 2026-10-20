# Repolex Knowledge Graph of klen/muffin-databases

RDF knowledge graph data for [klen/muffin-databases](https://github.com/klen/muffin-databases), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-databases
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 51a09b28ddfadd722b0ca7128c85230255527650
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 51a09b28ddfadd722b0ca7128c85230255527650
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a6ee958310ca78a98bf4803c291d5898c7fd5b4.nq.gz
│   ├── 13f28d88a36f13c791f15c07aeb55c348c71b3b6.nq.gz
│   ├── 1b7c2488f2d10a8e31317c3fcd02d1dcdc558bd1.nq.gz
│   ├── 1e152e5141ad151496fdbb9b9cfceae10f11e829.nq.gz
│   ├── 201b79d9995db9daf9ef61feed65e8e95f5832b5.nq.gz
│   ├── 23c5c150f58bdd129447223d88288e859f8cccb1.nq.gz
│   ├── 3bf5d6444fd256cfe444fa3416713441d043faa5.nq.gz
│   ├── 3d3de9177b065ccd2b82e03a2cd70dd8b0e5323a.nq.gz
│   ├── 47a35df4c58d3c5d237e9c287a8f297cce9d6aba.nq.gz
│   ├── 4a060cc8ce501e4a5b9157c2f5ed52285582dd60.nq.gz
│   ├── 576bf2a286b8896226fe21ed1e611ba1ae4492dd.nq.gz
│   ├── 5f1d5686f3dc12105665875988bbe0b90d32c2bc.nq.gz
│   ├── 666ce2a519fd8f0c3599a11f968422b82612ca92.nq.gz
│   ├── 78df056a6afd6b2f7c5a8695635380a19f30acd9.nq.gz
│   ├── 7a3f07ab83552f47a8705fa5d22729a324a2f71a.nq.gz
│   ├── 80826d975aa6e305dddbe44be4b9e7ea0ca1dd87.nq.gz
│   ├── c11c580f0a535f9d30722f42ee3a876a8f1e14a2.nq.gz
│   ├── c1c7f03030fddd529abbfe4e553b27501d87e00e.nq.gz
│   ├── ce48f87110f5a00c4f3320f9ed0c8e630cb23daf.nq.gz
│   ├── d0b5e05ac42e8dc353fdfb370eb5017a58c90916.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e728d03676c20ba87a39556e60b642f5df17ebde.nq.gz
│   ├── ed94622b09c98cbd16fbd79b99a5d25b3cd65c9b.nq.gz
│   └── fb72df8519f86866e84b359c2ec0784cdecde86f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 51a09b28ddfadd722b0ca7128c85230255527650.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 31 files
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

[klen/muffin-databases](https://github.com/klen/muffin-databases)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
